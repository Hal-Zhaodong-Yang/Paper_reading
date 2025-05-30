# Learn from Human

## Learn from human video

##### Tool-as-Interface

[Link](https://tool-as-interface.github.io/); Using two cameras to generate 3D reconstruction, applying Gaussian Splatting for novel view augmentation, and also employs segmentation models to extract embodiment-agnostic observations, and leverage task-space tool-action representations to train visuomotor policies.

- Employ Grounded-SAM to mask out human hands when training and mask out robot gripper while deploying
- Policy is diffusion



## Co-Training

##### Humanoid Policy ∼ Human Policy

[link](https://human-as-robot.github.io/); Collect large-scale human egocentric video demonstration dataset, which is aligned with humanoid manipulation demonstrations. Co-train a policy with smaller-scale robot data.
