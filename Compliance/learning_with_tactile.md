# Learn with Force/Tactile Information



##### Farm

Last author: Jan Peters

[link](https://tactile-farm.github.io/); This paper enables compliant grasping of parallel jaw gripper with GelSight sensor on the gripper tip; They do it by using similar method as RDP, but while collecting human data, they use FEATS to estimate the gripping force from tactile images; the diffusion policy will learn to provide gripper width as well as gripping force; and their gripping controller has two modes: position-control mode and force-control mode, and the force control mode will be activated once contact happens and will be able to utilize the gripping force command from the diffusion policy

- They determined a -0.5N threshold for the both the gripping force command and the realtime force computed from FEATS to activate force-control mode of the gripper