# Efficient Work Distribution Methods for Parallel Best-First Search

<iframe width="560" height="315" src="https://www.youtube.com/embed/x2mjIOkLQxw?start=2552" frameborder="0" allowfullscreen></iframe>

The A* algorithm is used in many areas of AI, including planning, scheduling, and path-finding. Parallelization of A* search can yield speedups as well as a way to overcome memory limitations - **the aggregated memory available in a cluster can allow problems that can't be solved using a single machine to be solved**. Thus, designing scalable, parallel search algorithms is an important goal.

The major challenges which need to be addressed when designing parallel search algorithms are *search overhead* and *communication overhead*. Previous works in parallel best-first search only mentioned one of the two overheads, thus did not scale to large scale distributed environment.

We developed **Abstract Zobrist hashing**, a new work distribution method for paralel best-first search. Abstract Zobrist hashing reduces communication overhead while maintaining search overhead reasonably low. We evaluated parallel best-first search algorithms on sliding-tiles, grid path-finding, multiple sequence alignment, and classical planning in a **48 cores** bare-metal cluster as well as **a cloud cluster in EC2 with 128 cores**, and showed that Abstract Zobrist hashing significantly outperforms other methods.

## Code

[All codes we used for the experiments are available at my GitHub.](/software)

- A classical planner [CODE](https://github.com/jinnaiyuu/distributed-fast-downward)
- Domain-specific solvers (sliding-tile, grid-pathfinding, multiple sequence alignment) [CODE](https://github.com/jinnaiyuu/Parallel-Best-First-Searches)
- Instance generators for (15-puzzle, 24-puzzle, grid-pathfinding, traveling salesperson problem, multiple sequence alignment) [CODE](https://github.com/jinnaiyuu/combinatorial_instances)

## Open Questions

Many questions are yet unanswered including:

- Parallelizing width-based search (e.g. Iterative Width Search)
- Integrating CPU and GPU (what's the best way to make use of CPU/GPU?)
- Parallelizing non-classical planning (e.g. MDP, POMDP, etc.)
- Abstract Zobrist hashing applied to two player games (e.g. MCTS etc.)

## Publications

- Fukunaga A., Botea A, Jinnai Y., Kishimoto A. 2017. A Survey of Parallel A*. arXiv 1708.05296 [PAPER](https://arxiv.org/abs/1708.05296)
- Jinnai Y, Fukunaga A. 2017. On Hash-Based Work Distribution Methods for Parallel Best-First Search. Journal of Artificial Intelligence Research (JAIR). [PAPER](http://www.jair.org/papers/paper5225.html)
- Jinnai Y, Fukunaga A. 2017. A Graph-Partitioning Based Approach for Parallel Best-First Search. ICAPS 2017 Workshop on Heuristic and Search for Domain-Independent Planning (HSDIP). This paper summarizes work which will appear in a JAIR article. [PAPER](../pdf/papers/HSDIP-17 Jinnai-Fukunaga.pdf)
- Jinnai Y, Fukunaga A. 2016. Automated Creation of Efficient Work Distribution Functions for Parallel Best-First Search. Proc. 19th International Conference on Automated Planning and Scheduling (ICAPS-16) [PAPER](../pdf/papers/ICAPS-16 Jinnai-Fukunaga.pdf)
- Jinnai Y, Fukunaga A. 2016. Abstract Zobrist Hashing: An Efficient Work Distribution Method for Parallel Best-First Search. Proc. 30th AAAI Conference on Artificial Intelligence (AAAI-16) [PAPER](../pdf/papers/AAAI-16 Jinnai-Fukunaga.pdf)
