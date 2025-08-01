# Methods not relying on real data

## Representation design

##### Sim2Real Manipulation on Unknown Objects with Tactile-based Reinforcement Learning

[link](https://ieeexplore.ieee.org/abstract/document/10611113); Reinforcement Learning with only visual tactile sensing inputs on diverse objects in a physical simulator; image-based tactile sensor; it enables the policy to generalize to unseen objects; investigate three distinct representations to encode the tactile data:

- Raw tactile RGB image (w data aug)
- DIFF: (current raw tactile RGB image) - (a canonical force-free image), then convert the diff to grayscale image
- Binary: set a threshold to convert diff to a binary image



##### Learning In-Hand Translation Using Tactile Skin With Shear and Normal Force Sensing

[link](https://arxiv.org/abs/2407.07885); a sensor model for tactile skin that enables *zero-shot* sim-to-real transfer of ternary *shear* and binary normal forces; RL policy; dexterous in-hand translation; tactile sensing facilitates policy adaptation to various unseen object properties and robot hand orientations



##### General In-Hand Object Rotation with Vision and Touch

[link](https://arxiv.org/abs/2309.09979); *2023*; 



##### Robot Synesthesia: In-Hand Manipulation with Visuotactile Sensing

[link](https://arxiv.org/abs/2312.01853); *2024*; 



## Domain randomization

##### Domain Randomization for Transferring Deep Neural Networks from Simulation to the Real World

[link](https://arxiv.org/abs/1703.06907); First paper utilize domain randomization; it is possible to train a real-world object detector that is accurate to 1.5 cm and robust to distractors and partial occlusions using only data from a simulator with non-realistic random textures; they can be used to perform grasping in a cluttered environment



##### Dextrous Tactile In-Hand Manipulation Using a Modular Reinforcement Learning Architecture

[link](https://arxiv.org/abs/2303.04705); *2023*; RL learned policy for in-hand manipulation to reorient a cube to any of the 24 possible goals with hand upside-down; a deep differentiable particle filter to estimate the cube state trained on tactile data generated by running the policy; simply apply DR for sim2real transfer



##### Rotating without Seeing: Towards In-hand Dexterity through Touch

[link](https://arxiv.org/abs/2303.10880); *2023*; 



## Motor adaptation

##### RMA: Rapid Motor Adaptation for Legged Robots

[link](https://arxiv.org/abs/2107.04034); first a environmental parameter encoder which takes in environment parameters and outputs latent vector z, and a base policy which takes in the env state, previous actions, and the latent vector z are trained simultaneously with model-free RL in simulation; then an adaptation module which takes in the state-action histories and outputs latent vector z is trained with supervised learning. When deploying the policy zero-shot in real world, both the base policy and the adaptation module is rolled out.

The main focus of motor adaptation seems to enable legged robot to walk on different terrains, and adapt to tear-and-wear or other non-rigid physical dynamics.

- First, the reward function is motivated from bioenergetic constraints of minimizing work and ground impact. They found these reward functions to be critical for learning realistic gaits in simulation. Second, they train their policies on uneven terrain as a substitute for additional rewards used by for foot clearance and robustness to external push. A walking policy trained under these natural constraints transfers to simple setups in the real world (like concrete or wooden floor) without any modifications.
- The adaptation module then enables it to scale from simple setups to very challenging terrains.
