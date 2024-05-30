# Preliminary

## Subgoal in Hierarchical Reinforcement Learning

  Hierarchical RL considers decomposed sub tasks to efficiently solve long horizon tasks in divide and conquer style. Applying low level skills into decomposed task makes it even scalable to complex tasks theoretically. However, there exists problem of how to decide when to divide such states. [Numerous researches](https://dl.acm.org/doi/pdf/10.1145/3453160) were conducted for such subgoal, subtask discovery. Some might provide subgoal or skills manually. But we focus on scalable approach, seeking method to automatically acquire skills and subgoals from the fixed and limited offline dataset. 

![By selecting helpful states, it can help solving harder problems. ](Preliminary%20b09adf5576464baf816174dd98b7fccf/Untitled.png)

By selecting helpful states, it can help solving harder problems. 

## Language based robot manipulation

  Understanding language is also important for natural interaction between human and robot. Robot agents understanding language instruction can enable not only efficient communication but also task specification. We would like to apply [LISA](https://arxiv.org/abs/2203.00054) and [SkillDiffuser](https://skilldiffuser.github.io/) as an baseline such that it can generate actions from both language and observations.

## Data augmentation methods

  One of the recent notable research integrating VLMs into decision making is [CLIP](https://proceedings.mlr.press/v139/radford21a) and [DIAL](https://arxiv.org/pdf/2211.11736). CLIP can be used to extract semantic information between image and text pairs, which is pre-trained with internet-scale dataset of image and caption. CLIP served as a fundamental model that had facilitated numerous extended research approaches in vision tasks and reinforcement learning problems. DIAL is one of the extended research that used CLIP for dataset augmentation in the robotic manipulation tasks. Starting from the small amount of human annotated dataset, CLIP and GPT-3 was used to generate instructions for larger unlabeled dataset. Language conditioned policy was later trained using behavior cloning in the annotated dataset. DIAL showed significant performance compared to [RT-1](https://arxiv.org/abs/2212.06817) evaluated on unseen instructions. However, there exists limitations of generating instructions only from start and final state, which makes it unaware of skills and how instructions are accomplished. 

  [ROSIE](https://arxiv.org/pdf/2302.11550) had also applied data augmentation method for robot learning but it leveraged diffusion model for aggressive data augmentation. It can in-paint unseen objects into the scene generating new data for learning. 

[🏠 Home](../Subgoal%20generation%20with%20Vision%20Language%20Models%20for%2071dadafcdb46425d9f40acbb7b606c42.md)

[⇒ Methods](Methods%20257e2e4c83cd4fb68cbff295668c1555.md)