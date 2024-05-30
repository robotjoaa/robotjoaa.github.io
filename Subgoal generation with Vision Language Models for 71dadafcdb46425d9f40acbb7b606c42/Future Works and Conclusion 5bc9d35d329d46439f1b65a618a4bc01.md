# Future Works and Conclusion

## Future Works

1. Plan always changes
    1. When unexpected outcome occurs (obstacles in the way, no matching object found, etc)
        
        It needs to deal with such uncertainty from the environment: 
        
        [Inner Monologue: Embodied Reasoning through Planning with Language Models](https://arxiv.org/pdf/2207.05608)
        
    2. Language based feedback during execution
        
        If we can promptly infer from the language feedback from the environment, it would be   helpful for recovering from sudden failure and quickly adapting to sudden changes. 
        
2. Find scalable methods for general environments
    1. Current method for determining the sub-goal is unscalable. Domain specific knowledge of the environment were used (subgoal from bot’s stack). 
    2. Determining when an instruction is done, not environment specific hyper-parameter.
    3. It could be instruction tuning method as our project (but with more diverse, large amount of dataset) or providing environment program into VLMs. Later method can be similar to [EUREKA](https://arxiv.org/pdf/2310.12931), but instead of reward function it extracts valuable sub-goals.
3. Improving inference time of diffusion model for real-time application.
4. Incorporating BabyAI text environment and visual observation using VLMs.
5. Generating sub-goal might not be the right choice. Planning and grounding skills to the plans might be a better idea.
    1. [SayCan](https://say-can.github.io/) : LLMs knows the underlying dynamics but does not ground to the current environment. Applied to real world experiment with PaLM. 
    2. [ProgPrompt](https://progprompt.github.io/) : Generating situated robot task plans using large language models. LLM generated plans are executed in the form of script (program).

## Conclusion

- We researched two method LISA, SkillDiffuser as a baseline model for sub-goal annotated dataset generated from VLMs.
- Such dataset were hard to create, and it was non-trivial to apply such dataset to LISA and SkillDiffuser. Baseline performances were also poor.
- Future researches on how to apply VLMs into the high level planning of robotic manipulation tasks will be necessary.
- In conclusion, there were too many technical difficulties during the project. Problems includes dataset generating method, insufficient computation resources, slow inference time, low performance.

  We wanted to show that whether sub-goal can be generated in the offline learning setup, with the power of VLMs. Sub-goal generation requires fundamental understanding of environment and physical dynamics, which can be hard to obtained just from fixed offline datasets. However, by data augmentation leveraging VLMs, we thought it can both help VLMs for general understanding of the environment and acquiring low level skills. From the results, we observed that fine-tuning VLMs requires diverse, large amount of dataset to cover underlying dynamics of the environment.     

  Furthermore, considerations on scalable dataset augmentation without manual engineering and methods to apply VLMs result into language conditioned hierarchical imitation learning architecture can be meaningful. 

[🏠 Home](../Subgoal%20generation%20with%20Vision%20Language%20Models%20for%2071dadafcdb46425d9f40acbb7b606c42.md)