# Data Generation

## Teleoperation

##### DexMimicGen

[Link](https://dexmimicgen.github.io/); Automatically generate data for imitation learning of bimanual multi-fingered hand manipulation task.

- Divide bimanual manipulation into subtasks: parallel, coordination, and sequential. Similar to MimicGen, the author exploit the SE(3) equivariance of robot actions with respect to object poses
- Randomize initial distribution, and calculate transformation between current initial pose and source demo trajectory
