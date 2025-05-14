# Dexterous Grasping

## Reinforcement Learning

## Evaluation on Different Hands

##### AnyDexGrasp

[link](https://graspnet.net/anydexgrasp/); Two stage training: 1. A universal model maps the point-cloud scene to contact-centric grasp representation, 2. each robot hand trains a unique grasping model throught trial and error utilizing the grasp representation. Grasping decision process also contains two steps (I guess this is common for grasp decision): 1. a mapping function that maps grasp representation to grasp candidate, 2. a hand-dependent grasp decision model that predicts success probability for each grasp candidate

- [x] What is grasp representation? Grasp representation is a set of object surface point and normal vector pairs (However, their 3D version of representation using uniformly distributed cross-section along z-axis to utilize polar coordinate as 2D, their normal vector is still represented in this 2D cross-section plane, which is not the true surface normal, because true surface normal is unlikely to be in the cross-section plane)
