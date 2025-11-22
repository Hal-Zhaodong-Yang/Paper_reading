# Data Generation

##### DexMimicGen

[link](https://arxiv.org/abs/2410.24185); leverage a small set of human demonstrations and use demonstration transformation and replay in physical simulation;  DexMimicGen incorporates a flexible per-arm subtask segmentation strategy; a synchronization strategy to ensure precise alignment of actions during coordination subtasks; an ordering constraint mechanism to enforce the correct order of actions during sequential subtasks

- They utilize relative pose in the assumption of their problem: the manipulation in each subtask Si(oi) is relative to a single object’s coordinate frame
-  The subtask segmentation can be done with human annotation or using heuristics
- By transforming object pose in current subtask to a source demo subtask trajectory, they generate new trajectories
- Categorize subtasks into 3 types: parallel, coordination, and sequential 



##### MimicGen

[link](https://arxiv.org/abs/2310.17596); a similar pipeline for the single-arm with parallel-jaw gripper setting like DexMimicGen; MimicGen relies on decomposing each task into a sequence of subtasks, to generate trajectories for each subtask separately and then stitch them together