## Offline to online

##### Offline-to-Online Reinforcement Learning via Balanced Replay and Pessimistic Q-Ensemble

[link](https://arxiv.org/abs/2107.00591); SAC; In offline stage the actor-critic (with conservative q function) is trained with large offline datasets, typically around 1M transitions; during online use balanced replay for better offline to online alignment, which is mixing offline transition and online transition during online learning, and specifically choose offline transitions which are close to online samples to form the mixed replay buffer.



##### Learning Complex Dexterous Manipulation with Deep Reinforcement Learning and Demonstrations

[link](https://arxiv.org/abs/1709.10087); also known as DAPG; first BC, then Policy Optimization, but adding a BC loss term into the policy optimization loss term; small amount of offline data



##### Conservative Q-learning for offline reinforcement learning

[link](https://dl.acm.org/doi/abs/10.5555/3495724.3495824); CQL; besides ordinary bellman loss term, adding another conservative term, which penalizes the actions out-of-distribution of demo data, so that making the q function conservative



##### Robo-ValueRL: Reliable Value Estimation for Offline-to-Online Reinforcement Learning

[link](https://arxiv.org/abs/2607.09866); Offline2online learning, key designs are 1. value function takes in not only current image, but also history images; 2. to deal with suboptimal offline dataset, they uses quality-conditioned consistency policy training by using the value function to label the trajectories; 3. Online residual adaptation with gated residual correction (sometimes let residual+base control the robot but sometimes don't)