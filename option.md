# Skill Discovery with Well-Defined Objectives

While many skill discovery methods have been proposed to accelerate learning and planning, most are heuristic methods without a clear relationship to the agent’s objective. The conditions under which the algorithms are effective is therefore often unclear. We claim that we should pursue skill discovery algorithms with explicit relationships to the objective of the agent to understand in what scenarios skill discovery methods are useful. 

To this end, we analyzed two scenarios, planning and reinforcement learning by Jinnai et al. (2019), and showed how to identify skill discovery criteria that directly address the relevant objectives.  For planning, we showed that finding a set of options that minimizes planning time is NP-hard, and gave polynomial-time algorithms that are approximately optimal under certain conditions. For reinforcement learning, we showed that under certain conditions, the difficulty of discovering a distant rewarding state in an MDP is bounded by the expected cover time of a random walk over the graph induced by the MDP’s transition dynamics. We proposed covering options, a method to automaticall generate skills that optimize the cover time so as to minimize the learning time.

While covering options is useful for tabular setting, it is not directly applicable to deep reinforcement learning setting where the state-space is huge. To this end, we proposed deep covering options, a method to generate skills similarily to covering options but instead of enumerating the state-space it guesses the state dynamics by a neural network.

<img src="../images/papers/ICLR-20.png" alt="iclr-20" width="550" />


## Code

- Covering options [CODE](https://github.com/jinnaiyuu/Optimal-Options-ICML-2019)  
- Options that minimize planning time [CODE](https://github.com/jinnaiyuu/Optimal-Options-ICML-2019)

## Publications

- **Y. Jinnai**, J. Park, M.C. Machado, and G.D. Konidaris. Exploration in Reinforcement Learning with Deep Covering Options. Accepted, Proceedings of the Eighth International Conference on Learning Representations. (ICLR-20) [PAPER](../pdf/papers/ICLR-20.pdf)  
- **Jinnai Y**. Park JW, Abel D, Konidaris G. 2019. Discovering Options for Exploration by Minimizing Cover Time. Proc. 36th International Conference on Machine Learning. [PAPER](../pdf/papers/ICML-19-rl.pdf)  
- **Jinnai Y**, Abel D, Hershkowitz E, Littman M, Konidaris G. 2019. Finding Options that Minimize Planning Time. Proc. 36th International Conference on Machine Learning. [PAPER](../pdf/papers/ICML-19-plan.pdf)  
- **Jinnai Y**, Abel D, Park JW, Hershkowitz E, Littman M, Konidaris G. 2019. Skill Discovery with Well-Defined Objectives. ICLR Worshop on Structure and Priors in Reinforcement Learning. [PAPER](../pdf/papers/SPiRL-19.pdf)  