# Methods not relying on real data

## Representation design

##### Sim2Real Manipulation on Unknown Objects with Tactile-based Reinforcement Learning

[link](https://ieeexplore.ieee.org/abstract/document/10611113); Reinforcement Learning with only visual tactile sensing inputs on diverse objects in a physical simulator; image-based tactile sensor; it enables the policy to generalize to unseen objects; investigate three distinct representations to encode the tactile data:

- Raw tactile RGB image (w data aug)
- DIFF: (current raw tactile RGB image) - (a canonical force-free image), then convert the diff to grayscale image
- Binary: set a threshold to convert diff to a binary image
