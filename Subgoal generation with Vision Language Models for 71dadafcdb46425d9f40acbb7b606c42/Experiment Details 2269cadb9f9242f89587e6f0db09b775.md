# Experiment Details

## LISA

We consider results after 1.5k episodes for fair comparison. 

1. Result for same default hyperparameter (1k demos)
    
    ![Reported results were 59.4 / 46.3 / 49.1 for GoToSeq / SynthSeq / BossLevel](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/Untitled.png)
    
    Reported results were 59.4 / 46.3 / 49.1 for GoToSeq / SynthSeq / BossLevel
    

Our results were 59 / 37/ 40 where for harder cases, it did not showed enough performance. 

GoToSeq

![Evaluation success rate : 0.59](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/WB_Chart_2024._5._30._%25EC%2598%25A4%25EC%25A0%2584_5_36_05.png)

Evaluation success rate : 0.59

SynthSeq

![Evaluation success rate : 0.37](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/WB_Chart_2024._5._30._%25EC%2598%25A4%25EC%25A0%2584_5_13_55_(1).png)

Evaluation success rate : 0.37

BossLevel

![Evaluation success rate : 0.4](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/WB_Chart_2024._5._30._%25EC%2598%25A4%25EC%25A0%2584_5_05_41.png)

Evaluation success rate : 0.4

![Evaluation average length : 309](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/WB_Chart_2024._5._30._%25EC%2598%25A4%25EC%25A0%2584_5_35_49.png)

Evaluation average length : 309

![Evaluation length mean : 425](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/WB_Chart_2024._5._30._%25EC%2598%25A4%25EC%25A0%2584_5_14_54_(1).png)

Evaluation length mean : 425

![Evaluation average length : 547](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/WB_Chart_2024._5._30._%25EC%2598%25A4%25EC%25A0%2584_5_08_04.png)

Evaluation average length : 547

![Evaluation length std : 188](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/WB_Chart_2024._5._30._%25EC%2598%25A4%25EC%25A0%2584_5_33_09.png)

Evaluation length std : 188

![Evaluation length std : 226](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/WB_Chart_2024._5._30._%25EC%2598%25A4%25EC%25A0%2584_5_15_42_(1).png)

Evaluation length std : 226

![Evaluation length std : 295](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/WB_Chart_2024._5._30._%25EC%2598%25A4%25EC%25A0%2584_5_22_19.png)

Evaluation length std : 295

As difficulty increases, required length increases. But there exists some simple environment generated, the standard deviation is large. 

1. Effect of hyperparameter H.

We tested in the GoToSeq task among different H = 5, 10, 15, 20, default H=10 did best overall (0.65) and H = 5 at worst (0.55). As it is suggested in the paper, we found out that it is rather robust to the parameter changes. (We applied option number as 10)

![From [Section F.1 of original paper](https://arxiv.org/pdf/2203.00054) LISA](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/Untitled%201.png)

From [Section F.1 of original paper](https://arxiv.org/pdf/2203.00054) LISA

1. Effect of number of trajectory demos

We compared in the GoToSeq task with 1000k demo and 1k demo. There were no huge difference in the success rate (0.67 / 0.59) and difference in average length were not significant. (347 / 334)

![W&B Chart 2024. 5. 30. 오전 5_35_49 (1).png](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/WB_Chart_2024._5._30._%25EC%2598%25A4%25EC%25A0%2584_5_35_49_(1).png)

1. Option generated 

![option frequency in GoToSeq task](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/Untitled%202.png)

option frequency in GoToSeq task

![correlation between words and options](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/Untitled%203.png)

correlation between words and options

![W&B Chart 2024. 5. 30. 오전 5_36_05 (1).png](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/WB_Chart_2024._5._30._%25EC%2598%25A4%25EC%25A0%2584_5_36_05_(1).png)

![W&B Chart 2024. 5. 30. 오전 5_36_05 (2).png](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/WB_Chart_2024._5._30._%25EC%2598%25A4%25EC%25A0%2584_5_36_05_(2).png)

![W&B Chart 2024. 5. 30. 오전 5_33_09 (1).png](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/WB_Chart_2024._5._30._%25EC%2598%25A4%25EC%25A0%2584_5_33_09_(1).png)

![word frequency in GoToSeq task for each options](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/Untitled%204.png)

word frequency in GoToSeq task for each options

Since vocabularies are small, we can’t completely distinguish tokens from the instructions.

## SkillDiffuser

1. Result on individual tasks
    
    ![Untitled](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/Untitled%205.png)
    

Evaluation performance on individual tasks also changes significantly between 20 episodes. Despite of evaluating 5 times for each instruction, still they are lower than the reported result. Below results are from the best performing cases in each seeds, all lower than 60%. 

![Untitled](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/Untitled%206.png)

![Untitled](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/Untitled%207.png)

![Untitled](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/Untitled%208.png)

1. Result on composition tasks

![Untitled](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/Untitled%209.png)

![Best performing 0.21 / 0.1967 / 0.2 ⇒ 20% ](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/WB_Chart_2024._5._30._%25EC%2598%25A4%25EC%25A0%2584_5_59_25.png)

Best performing 0.21 / 0.1967 / 0.2 ⇒ 20% 

![W&B Chart 2024. 5. 30. 오전 6_00_40.png](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/WB_Chart_2024._5._30._%25EC%2598%25A4%25EC%25A0%2584_6_00_40.png)

As it stops early when tasks are quickly finished, average length and success rate are negatively correlated. (maximum length is 40)

We have observed poor results compared to what is reported in the paper especially for the SkillDiffuser. Reported results in SkillDiffuser had applied R3M as an image encoder to extract embedding from image based observation for other baselines including LISA for fair comparison. However the image encoder in the code was different from R3M. 

![W&B Chart 2024. 5. 30. 오전 6_06_27.png](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/WB_Chart_2024._5._30._%25EC%2598%25A4%25EC%25A0%2584_6_06_27.png)

Also, diffusion loss merely improves as it can see from the scale. For a qualitative evaluation, solving entire composed task were rarely observed. Due to these results, and long training time (1~2days), we have to consider only for the LISA. 

1. Option generated

![Option frequencies](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/Untitled%2010.png)

Option frequencies

![ Word frequency between options](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/Untitled%2011.png)

 Word frequency between options

![Word correlation between options](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/Untitled%2012.png)

Word correlation between options

Because each tasks use apparently different words, we can see a very sparse heatmap with clear correlations.

## What has changed

Our original plan was to compare performance of LISA on the BabyAI trained with sub-goal annotated dataset. **We decided to exclude SkillDiffuser because of poor training result, heavy computational burden and time constraints as shown above.**  We considered that adding sub-goals to the initial instruction will provide similar effect as decreasing horizon H steps, period for skill sampling. So we also had results with LISA on different H = 5, 15 (default 10).  

**However, due to problems of LISA and BabyAI environment discussed in the [next section](Discussion%20d1e7965234ea4da8a61503f456cd0bdc.md)**, we decided to focus on testing potential applicability of a fine-tuned LLaVA. We first start with the simple BabyAI GoToSeq task to get dataset used for fine-tuning.

## Dataset generation method for fine-tuning LLaVA

  One of the main reason we chose BabyAI is the Bot feature of the environment. The BabyAI environment introduces itself as ‘human in the loop’ where BabyAI Bot can have same effect as a human oracle planning in the environment. All 19 levels including GoToSeq, SynthSeq, and BossLevel for our interest can be solved with the Bot. This implementation was possible because BabyAI levels are generated from a small structured BabyAI grammar. With visibility masking and sub-goal stack for planning, the bot can effectively mock reasoning process of human as an oracle. 

  We thought that this intriguing feature will make us easy to formulate sub-goal as an ground truth label and can be used for generating dataset for fine-tuning. We first randomly created BabyAI environments, and ran Bots for retrieving trajectory and visual observation during the execution. We inspected the stack to get when the sub-goal is added and resolved. When these new sub-goal are generated or resolved, altogether with the given instruction, we can make the following question.

> **Question**. [Prefix], [Initial instruction]. [Finished instruction (if exist)] [Suffix]
**Prefix** :  In this 2D maze, you have to control red arrow to finish following tasks, (Pre-defined)
**Initial instruction** : go to a key and go to a box, then go to the green key and go to a purple ball. (This is initially given)
**Finished instruction** : I already finished 'go to a key and go to a box'. (Inferred from the stack)
**Suffix** : Where should the red arrow go next? (Pre-defined)
> 

 The finished instruction can exist or not during the trajectory. But this part is important when there exists causality between sub-goals. In more complex cases, there might exist locked door which needs same colored key, blocking boxes which needs picking obstacles to make the way, and tasks to drop which also requires to pick an object beforehand.

Prefix Variances : 

> Assume you are the red arrow in this maze to complete mission of ~ 
In this 2D maze, you have to control red arrow to finish following tasks ~
You need to move the red arrow through this maze to finish these tasks ~
You are controlling red arrow in this image to accomplish mission of ~
You are controlling red arrow in this image to accomplish mission of ~
> 

Suffix Variances : 

> Where should the red arrow go next? 
What can be your next decision?
What will you do next?
What should the red arrow do next?
What is your next move?
> 

  To prevent VLM learning same question format, we intentionally added some variations to the prefix and suffix. We did it manually, but we believe there will be more efficient ways to use various vocabularies for making dataset more diverse. However, generalization to instructions with unseen vocabularies were also a novelty focused in the LOReL paper. Studying effect of fixing vocabularies in the instruction can be another interesting future work.

**Answer** : Go to the purple door on your left (Bot added this to the stack)

**Image** : Entire observation masked with the visibility mask of the Bot. (Examples are shown below)

![Untitled](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/Untitled%2013.png)

![Untitled](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/Untitled%2014.png)

![Untitled](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/Untitled%2015.png)

Strictly, only partial observation of gray area should be given. But without context, there will be no much to infer from it. So we assume that it can remember all visited states, where it can be found from the visibility mask of the Bot. Compared to [this](Motivation%206175634f7f9f4a99b6d822783bf94cd9.md) in the motivation section, where we provided entire map, we can focus on partial observations not so sparsely. 

Finally, we change these queries to the visual instruction tuning format and apply LoRA finetuning. 

![Corresponding image for below.](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/Untitled%2016.png)

Corresponding image for below.

![Example of query in visual instruction tuning format](Experiment%20Details%202269cadb9f9242f89587e6f0db09b775/Untitled%2017.png)

Example of query in visual instruction tuning format

[🏠 Home](../Subgoal%20generation%20with%20Vision%20Language%20Models%20for%2071dadafcdb46425d9f40acbb7b606c42.md)

[⇒ Discussion](Discussion%20d1e7965234ea4da8a61503f456cd0bdc.md)