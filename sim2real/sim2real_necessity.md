# Sim2real Capability of simulator

##### Rethinking Sim2real

[link](https://arxiv.org/abs/2207.10821); 2022; Keypoint: training in a simulator with lower fidelity might result in better sim2real transfer performance; Task: **quadruped robot pointgoal navigation**

- How they define "fidelity" in their experiment (two kinds of physics fidelity):
  - kinematic: "teleport" the robot to the next state using Euler integration, no actual dynamics
  - dynamics: consisting of rigid-body mechanics and simulates contact dynamics
  - The above two fidelity both commands robot COM linear and angular velocities, but dynamics utilize a low-level controller to convert the command to joint-torque level
- a kinematically trained policy outperforms dynamic policies, even when evaluated using dynamic simulation and control
- the trained kinematic policy can be transferred to a real Spot robot, which ships with manufacturer-provided ‘black-box’ low-level controllers that cannot be accurately simulated
- Two reason they concluded for these results:
  - Policies tend to overfit into the high fidelity simulators
  - lower-fidelity simulators allows collection of larger amount of data under a fixed wall-clock budget
