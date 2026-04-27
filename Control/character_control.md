# Character Control

## Control Policy Architecture Innovation

##### PFNN

[link](https://dl.acm.org/doi/10.1145/3072959.3073663); The entire network is trained end-to-end on a large dataset of locomotion data that has been fitted into virtual environments; a phase function outputs weights for the control policy (a MLP); the phase function is actually 4 control points, each point contains a set of MLP weights and biases, they just use Cubic Spline to interpolate between the 4 points to get weights and biases using a phase parameter p which is like "time parameter" for the spline.