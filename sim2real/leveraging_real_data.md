# Leveraging Real Data

## Small amount of real data

##### ASID

[link](https://arxiv.org/abs/2404.12308); leverage a small amount of real-world data to autonomously refine a simulation model and then plan an accurate control strategy that can be deployed in the real world; approach critically relies on utilizing an initial (possibly inaccurate) simulator to design effective exploration policies that, when deployed in the real world, collect high-quality data.

- Pipelines: 1) exploration in real to collect data with larger Fisher information; 2) refinement of simulation params using the collected real data; 3) policy training on the updated simulator
- A key insight: a policy trained in sim might not directly transfer to the real world, but strategies that explore effectively in sim often also explore effectively in real.
- Small amount of data: typically a single episode of data suffices.