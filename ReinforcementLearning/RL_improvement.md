# RL Improvement

## Modify Optimization Function

##### Going Beyond Heuristics by Imposing Policy Improvement as a Constraint

[link](https://arxiv.org/abs/2507.05328); Seems besides the original optimization funciton $J(\pi)$, they add another Heuristic objective function $H(\pi)$ to make the objective: $J(\pi) + H(\pi)$; Instead of setting heuristic rewards manually, they set heuristic objective function