# IL with RL

## Residual Policy Learning

##### Residual Policy Learning

[Link](https://arxiv.org/abs/1812.06298); RPL consistently and substantially improves on the initial controllers. RPL is more data-efficient than learning from scratch.

- The performance of RPL drops early in training before quickly recovering and surpassing the baselines.
- Initialize the residual function so that $f_{\theta}(s) = 0 for \ all \ s \in S$. Initialize the last layer of the network to be zero.



#### Touch begins where vision ends

[link](https://vitalprecise.github.io/); No simulation, collect demonstration for IL and do residual RL training in the real world

- Collect 32 trajectories for each tasks with green background, augment image input with background replacement by RoboEngine; use random initialized ResNet-18 as vision encoder, and MLP as tactile encoder. Train with ACT
- Online residual RL training with frozen base ACT policy\

In their videos, it seems they only allow for 3D position movement of the robot EEF (No rotation)