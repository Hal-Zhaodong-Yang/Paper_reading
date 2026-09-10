# IL with RL

## Residual Policy Learning

##### Residual Policy Learning

[Link](https://arxiv.org/abs/1812.06298); RPL consistently and substantially improves on the initial controllers. RPL is more data-efficient than learning from scratch.

- The performance of RPL drops early in training before quickly recovering and surpassing the baselines.
- Initialize the residual function so that $f_{\theta}(s) = 0 for \ all \ s \in S$. Initialize the last layer of the network to be zero.



##### Touch begins where vision ends

[link](https://vitalprecise.github.io/); No simulation, collect demonstration for IL and do residual RL training in the real world

- Collect 32 trajectories for each tasks with green background, augment image input with background replacement by RoboEngine; use random initialized ResNet-18 as vision encoder, and MLP as tactile encoder. Train with ACT
- Online residual RL training with frozen base ACT policy\

In their videos, it seems they only allow for 3D position movement of the robot EEF (No rotation)



##### From Imitation to Refinement – Residual RL for Precise Assembly

Pulkit Agrawal, ICRA 2025

[link](https://arxiv.org/abs/2407.16677); Simply diffusion policy or act + residual policy; sim2real by teacher-student-distillation; train residual policy with RL in sim



##### Policy Decorator: Model-Agnostic Online Refinement for Large Policy Model

Hao Su, ICLR 2025

[link](https://proceedings.iclr.cc/paper_files/paper/2025/hash/45c361d4117d598d4bb6568b407e9ac9-Abstract-Conference.html); an already-trained base policy + training residual policy; utilize some designing tricks like residual action bound, and progressive exploration schedule which mimics e-greedy strategy in DQN, using base and base+residual action alternatively, with a probability distribution of (1 - e, e), with e gradually increasing.

- Pure simulation experiment