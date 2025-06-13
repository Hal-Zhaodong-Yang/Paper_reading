# Leveraging Real Data

## Small amount of real data

##### ASID

[link](https://arxiv.org/abs/2404.12308); leverage a small amount of real-world data to autonomously refine a simulation model and then plan an accurate control strategy that can be deployed in the real world; approach critically relies on utilizing an initial (possibly inaccurate) simulator to design effective exploration policies that, when deployed in the real world, collect high-quality data.

- Pipelines: 1) exploration in real to collect data with larger Fisher information; 2) refinement of simulation params using the collected real data; 3) policy training on the updated simulator
- A key insight: a policy trained in sim might not directly transfer to the real world, but strategies that explore effectively in sim often also explore effectively in real.
- Small amount of data: typically a single episode of data suffices.





## Train mapping from domain to domain

##### AnyRotate

[link](https://arxiv.org/abs/2405.07391); Train a dense tactile policy in simulation and present a sim-to-real method for rich tactile sensing to achieve zero-shot policy transfer. Their framework allow a unified policy to rotate unseen objects about arbitrary rotation axes.

- They highlight the benefit of capturing detailed contact information when handling objects of varying properties
-  Rich multi-fingered tactile sensing can detect unstable grasps and provide a reactive behavior that improves the robustness of the policy
- Sim2real:
  - Simulate tactile information as contact pose and contact force
  - Use tactile image in real world, and collect dataset of tactile image and contact pose/force in real world. Train a CNN to extract contact pose/force from tactile images
    - **They actually assume the real contact pose/force and sim contact pose/force are in the same domain**