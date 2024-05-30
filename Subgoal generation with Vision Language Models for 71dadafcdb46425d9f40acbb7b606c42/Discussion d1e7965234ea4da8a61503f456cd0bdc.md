# Discussion

## Limitations : Things that we didn’t anticipated

### Problem with Baselines and Benchmarks

We originally aimed to compare performance of LISA and SkillDiffuser on the dataset annotated by the LLaVA. During reproduction, we faced with the following dilemma. Where we neither can fine-tune the LLaVA to generate sub-goal to use the annotated dataset nor modifying baseline architecture to be conditioned from VLM outputs. 

1. When we fine-tune LLaVA to generate sub-goal to use the annotated dataset, 
    1. Problem with Benchmarks : current method that relies on Bot sub-goal heavily depends on human environment engineering. Bots are considered to remember everything they saw earlier. In the [paper](https://arxiv.org/abs/1810.08272) it said bot **‘keeps track of the grid cells of the environment which it has and has not seen. only use information which it could realistically have access’**. This can be tremendously difficult when unstructured partial visual observations are given. Compared to the LOReL which includes observation that can almost see all details even with single camera, 7x7 grid rendered to an image is less intuitive than getting 7x7x3(status of each grid) + 4(agent direction) = 151 state representations. **(Observation is so sparse and there’s not much to plan in the beginning.)** 
    
    During research on BabyAI benchmark, I found that there exists implementation of text based BabyAI (BabyAI-text). There were already [LLM based “online” approach](https://arxiv.org/abs/2302.02662) in this environment which suggests the future direction that fine-tuning VLMs to convert observations in structured state representations. **(Current BabyAI environment with visual observation is not suitable for our concern. If the agent can solve the problem, it would be due to efficient exploration and memorization not planning.)**
    
    These suggests that sub-goal generations are suitable for LOReL environment where observation provides much information with less obstructed dynamics. And planning can be made generally without deviating by the future observations. Also, we can apply dataset augmentation(modification) methods such as changing colors, clipping, rotation, background which are often used for supervised learning to the LOReL but not for BabyAI where color matters.
    
    As it was mentioned in the experiment details section, SkillDiffuser is not directly applicable to discrete BabyAI environment, where it requires diffusion and inverse dynamics for getting actions for state. Diffusion methods for discrete state should be applied but we thought modified version will be no longer SkillDiffuser and that is yet another big problem to be implemented.
    
    1. Problem with Baseline : current LISA, SkillDiffuser method can only utilize original instructions at the beginning of the inference. Which makes no space for iterative input of generated sub-goals. This is inefficient where there could be language based feedback during execution. Thus we have to provide sub-goals with the instructions initially. **(Since sub-goal can be changed during execution, initially provided sub-goal might be irrelevant)**
2. Then, how about iterative inference of sub-goal during execution?
    1. This needs architecture modification of applying VLM results to decision transformer of LISA and SkillDiffuser. And this might not be easy as it sounds. SkillDiffuser requires high amount of computation power. It would be hard to run both LLaVA and SkillDiffuser in the same machine. If we use LLaVA inference result from the server, it cannot be applicable real time. **(We don’t have much time)**
    2. Iterative inference can also provide intuitive planning by deciding when to terminate low-level skills. Current LISA and SkillDiffuser can only change to other skill every H steps, which is also environment dependent hyper-parameter. This makes suggested method to be different from the original framework of option in terms of termination function.

## Problems during LLaVA finetuning.

We experienced over-fitting during LLaVA fine-tuning and it might be due to poor dataset. 

We inspected dataset distribution of the validation, training dataset split. 

| Dataset Split | Total | Explore
(w/o cond.) | Explore
(with cond) | Door
(w/o cond) | Door
(with cond.) | Explore /
Door (%) |
| --- | --- | --- | --- | --- | --- | --- |
| Training | 11K | 5732 (52.1%) | 2048 (18.6%) | 2177 (19.8%) | 1043 
(9.5%) | 7780 (70.7%)/ 
3220 (29.3%) |
| Validation | 1K | 513
(51.3%) | 202
(20.2%) | 206
(20.6%) | 79
(7.9%) | 715 (71.5%)/
285 (28.5%) |

Condition (cond.) means when there exists part of the instruction that is already satisfied, given in the instruction as ‘I already finished ~’. We also considered this, since it can potentially effect the sub-goal generation. 

  Since half of the output labels are ‘Explore’ and the label is not so diverse, we can consider that the dataset is biased. Our approach lacks, diversity in the dataset which didn’t yet considered other SynthSeq, BossLevel in the BabyAI environment, which makes sub-goal suggestions limited. Those levels require more various sub-goals (such as close, open, pick, drop), adding more candidates for the sub-goal can enhance the diversity of the dataset, less prone to over-fitting. Other queries, not just considering generating sub-goals but requiring overall understanding of the environment, should have been included. For instance, including trivial cases when instructions are all achieved, thus agent should decide to terminate on its own. Lack of evaluation metric is also a limitation.

  **We want to emphasize that the reason for us to choose only considering GoToSeq task was to evaluate fine-tuned LLaVA’s performance in minimum setting as possible. But it turns out to hamper entire fine-tuning process with less diverse dataset.**

## Final Regards : When will hierarchical method beat this?

![[Baseline imitation learning results for all BabyAI levels](https://arxiv.org/pdf/1810.08272)](Discussion%20d1e7965234ea4da8a61503f456cd0bdc/Untitled.png)

[Baseline imitation learning results for all BabyAI levels](https://arxiv.org/pdf/1810.08272)

This is the reported result of imitation learning from BabyAI Bot’s 1M demonstration. Since the Bot is implemented to be optimal in this setting near human, their imitation results are also near perfect. Our reproduced results performs much lower with inefficient moves. I believe that current baseline we used will not reach this level of performance easily. Focusing on other aspects such as robust generalization with sub-optimal trajectories might be better future work direction. 

[🏠 Home](../Subgoal%20generation%20with%20Vision%20Language%20Models%20for%2071dadafcdb46425d9f40acbb7b606c42.md)

[⇒ Future Works and Conclusion](Future%20Works%20and%20Conclusion%205bc9d35d329d46439f1b65a618a4bc01.md)