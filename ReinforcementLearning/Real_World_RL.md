# Real-World RL

## RL with intervention

##### UniIntervene

CoRL 2026, last author: Ziwei Wang, NTU

[link](https://arxiv.org/pdf/2606.12372); before online RL stage, they trained a "supervisor/world-model critic" using Qwen backbone (Qwen backbone is frozen) and V-JEPA 2 (frozen), with trainable latent future head and recovery action head. The trainable parts are trained on a 40-trajectory offline dataset which somehow contains the right and wrong trajectory and also even recovery examples to help the unintervine learn critic value, predict future action and detect potential stagnation and intiate recovery mode and execute recovery action (the UniIntervene supervisor can only do recovery motion, and cannot just finish the whole tasks). 