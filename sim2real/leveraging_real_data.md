# Leveraging Real Data

## Small amount of real data

##### Sim-and-Real Co-Training: A Simple Recipe for Vision-Based Robotic Manipulation

[link](https://arxiv.org/abs/2503.24361);  this work presents a simple yet effective recipe for utilizing simulation data to solve vision-based robotic manipulation tasks; simulation data can enhance real-world task performance by an average of 38%, even with notable differences between the simulation and real-world data



##### Legged Robots that Keep on Learning: Fine-Tuning Locomotion Policies in the Real World

[link](https://arxiv.org/abs/2110.05457); basically utilizing off-policy RL training; first pre-training three policies: forward/backward/reset policy in simulation; then fine-tuning the three policies in real world with off-policy RL; a modest amount of real-world training can substantially improve performance during deployment



##### Reconciling Reality through Simulation: A Real-to-Sim-to-Real Approach for Robust Manipulation

[link](https://arxiv.org/abs/2403.03949); *2024*; teacher-student distillation in simulation for the final sim2real transfer (teacher has privileged information while student only has access to raw sensor observation), simultaneously co-training with previous real data

Pipeline: 

1. Transfer the real scene into sim scene by scanning with 3D reconstruction and user manually specify articulation and joint through a simple interface
2. Collect human teleoperation demonstration, train IL policy on the demonstration, and rollout the policy in simulation (collect successful trajectories)
3. RL fine-tuning with sparse rewards and demos (optional step)
4. sim2real transfer by distilling a state-based simulation policy into a policy operating from raw sensor observations available in the real world. During distillation, they also co-trained with the original real-world demonstrations to capitalize on the combined benefits of simulation-based robustification and in-domain real-world data



##### Rapidly Adapting Policies to the Real World via Simulation-Guided Fine-Tuning

[link](https://arxiv.org/abs/2502.02705); *2025*; this paper introduces the Simulation-Guided Finetuning (SGFT) framework, which demonstrates how to extract structural priors from physics simulators to substantially accelerate real-world adaptation; this approach uses a value function learned in simulation to guide real-world exploration (utilize value function trained in simulation in the real-world optimization objective function, by adding value function increasing as a reward term)



##### Lessons from Learning to Spin "Pens"

[link](https://arxiv.org/abs/2407.18902); *2024*; 

Pipeline:

- Use RL to train an oracle policy with privileged information and generate a high-fidelity trajectory dataset in simulation
- Pre-training a sensorimotor policy in simulation (likely IL on the simulation dataset), and conducting openloop trajectory replay in the real world
- Then fine-tune the sensorimotor policy using these real-world trajectories to adapt it to the real world dynamics (likely IL on the real data as well)



##### A Real-to-Sim-to-Real Approach to Robotic Manipulation with VLM-Generated Iterative Keypoint Rewards

[link](https://arxiv.org/abs/2502.08643); 



## System identification

##### ASID

[link](https://arxiv.org/abs/2404.12308); *2024*; leverage a small amount of real-world data to autonomously refine a simulation model and then plan an accurate control strategy that can be deployed in the real world; approach critically relies on utilizing an initial (possibly inaccurate) simulator to design effective exploration policies that, when deployed in the real world, collect high-quality data.

- Pipelines: 1) exploration in real to collect data with larger Fisher information; 2) refinement of simulation params using the collected real data; 3) policy training on the updated simulator
- A key insight: a policy trained in sim might not directly transfer to the real world, but strategies that explore effectively in sim often also explore effectively in real.
- Small amount of data: typically a single episode of data suffices.



##### Sampling-Based System Identification with Active Exploration for Legged Robot Sim2Real Learning

[link](https://arxiv.org/abs/2505.14266); *2025*; SPI-Active robustly identifies key physical parameters through massive parallel sampling, minimizing state prediction errors between simulated and real-world trajectories; an active exploration strategy that maximizes the Fisher Information of the collected real-world trajectories via optimizing the input commands of an exploration policy

-  Unlike prior work [ASID](#asid), direct exploration policy training for legged robots can lead to erratic behaviors. They address this by introducing a hierarchical active exploration strategy that optimizes command sequences of a pre-trained multi-behavioral RL policy—targeting informative system excitation while ensuring reliable deployment



##### Residual Physics Learning and System Identification for Sim-to-real Transfer of Policies on Buoyancy Assisted Legged Robots

[link](https://arxiv.org/abs/2303.09597); *2023*; system identification, and augment the original simulation framework using a learned residual aerodynamics policy.

- System identification: 
  - obtaining the free variables (spring parameters, motor gains, default motor angles, and default knee joint angles) of nonlinear dynamics between servo motor commands and knee joint angles
  - sample 20 actuation commands that are uniformly distributed over the range [0, 1], which corresponds to motor arm angles in the range [0, 90]
  - minimize the discrepancy of all four joint angles between simulation and hardware using L-BFGS-B algorithm
- Residual aerodynamics policy: design a framework to learn a policy that generates proper external perturbation forces that can match the simulation behavior to the ground-truth trajectory collected from the hardware
- Data collection: train several locomotion policies in the vanilla simulation and record their action trajectories. Next, they use the recorded actions as open loop control on hardware to collect multiple state trajectories. They use a motion capture system to obtain observation data.

- Introduced categorization of system identification in related work section



##### Incremental Few-Shot Adaptation for Non-Prehensile Object Manipulation using Parallelizable Physics Simulators

[link](https://www.arxiv.org/abs/2409.13228); *2025*; robot pushing object task; utilize simulator as dynamics model for MPC; collect real-world data and use CEM to optimize the simulator parameters to match the simulation and real-world dynamics.



##### Dynamics as Prompts: In-Context Learning for Sim-to-Real System Identifications

[link](https://arxiv.org/abs/2410.20357); *2025*; by leveraging past interaction histories as context, this method adapts the simulation environment dynamics to realworld dynamics without requiring gradient updates; it seems it requires simultaneous rolling out simulation trajectories and real trajectories to collect data, and the real data might require extensive labor to collect



##### ASAP

[link](https://arxiv.org/abs/2502.01143);

- Delta action dynamics model performs better than directly estimate system parameters in agile locomotion



## Train mapping from domain to domain

##### AnyRotate

[link](https://arxiv.org/abs/2405.07391); Train a dense tactile policy in simulation and present a sim-to-real method for rich tactile sensing to achieve zero-shot policy transfer. Their framework allow a unified policy to rotate unseen objects about arbitrary rotation axes.

- They highlight the benefit of capturing detailed contact information when handling objects of varying properties
-  Rich multi-fingered tactile sensing can detect unstable grasps and provide a reactive behavior that improves the robustness of the policy
- Sim2real:
  - Simulate tactile information as contact pose and contact force
  - Use tactile image in real world, and collect dataset of tactile image and contact pose/force in real world. Train a CNN to extract contact pose/force from tactile images
    - **They actually assume the real contact pose/force and sim contact pose/force are in the same domain**



##### Bi-Touch: Bimanual Tactile Manipulation with Sim-to-Real Deep Reinforcement Learning

[link](https://arxiv.org/abs/2307.06423); *2023*; a dual-arm tactile robotic system (Bi-Touch) based on the Tactile Gym 2.0 setup that integrates two affordable industrial-level robot arms with low-cost high-resolution tactile sensors (TacTips)

- RL training in simulation
- Real2sim domain adaptation training. The training dataset comprises 5000 tactile images and the validation dataset has 2000 tactile images collected both in simulation and real tactile sensors with random contacts. Use an image-to-image translation Generative Adversarial Network (GAN) to learn the real-to-sim tactile image translation.