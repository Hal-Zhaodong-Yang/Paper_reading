# Learn with Force/Tactile Information



##### Farm

Last author: Jan Peters

[link](https://tactile-farm.github.io/); This paper enables compliant grasping of parallel jaw gripper with GelSight sensor on the gripper tip; They do it by using similar method as RDP, but while collecting human data, they use FEATS to estimate the gripping force from tactile images; the diffusion policy will learn to provide gripper width as well as gripping force; and their gripping controller has two modes: position-control mode and force-control mode, and the force control mode will be activated once contact happens and will be able to utilize the gripping force command from the diffusion policy

- They determined a -0.5N threshold for the both the gripping force command and the realtime force computed from FEATS to activate force-control mode of the gripper



##### Forge

Last author: Iretiayo Akinola

[link](https://arxiv.org/abs/2408.04587); This paper focus on insertion, assemble, nut-threading tasks; by leveraging a auto-tuned force threshold as input to the policy, and penalize larger force than the force threshold, to enable the policy to avoid exert larger force than the input force threshold; they also utilize a lot of domain randomization to bridge the sim2real gap. 

- "To tune the force threshold, we leverage success prediction. Conservatively, we start with a low threshold of 7.5N, which helps avoid slip and damage. If policy execution reaches a timeout before success is predicted, we increase the threshold and try again."