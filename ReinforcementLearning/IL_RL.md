# IL with RL

## Residual Policy Learning

##### Residual Policy Learning

[Link](https://arxiv.org/abs/1812.06298); RPL consistently and substantially improves on the initial controllers. RPL is more data-efficient than learning from scratch.

- The performance of RPL drops early in training before quickly recovering and surpassing the baselines.
- Initialize the residual function so that $f_{\theta}(s) = 0 for \ all \ s \in S$. Initialize the last layer of the network to be zero.