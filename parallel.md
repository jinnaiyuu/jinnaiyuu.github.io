# Efficient Work Distribution Methods for Parallel Best-First Search

![supercomputer](../images/KEI-supercomputer.jpg)

The A* algorithm is used in many areas of AI, including planning, scheduling, and path-finding. Parallelization of A* search can yield speedups as well as a way to overcome memory limitations - **the aggregated memory available in a cluster can allow problems that can't be solved using a single machine to be solved**. Thus, designing scalable, parallel search algorithms is an important goal.

The major challenges which need to be addressed when designing parallel search algorithms are *search overhead* and *communication overhead*. Previous works in parallel best-first search only mentioned one of the two overheads, thus did not scale to large scale distributed environment.

We developed **Abstract Zobrist hashing**, a new work distribution method for paralel best-first search. Abstract Zobrist hashing reduces communication overhead while maintaining search overhead reasonably low. We evaluated parallel best-first search algorithms on sliding-tiles, grid path-finding, multiple sequence alignment, and classical planning in a **48 cores** bare-metal cluster as well as **a cloud cluster in EC2 with 128 cores**, and showed that Abstract Zobrist hashing significantly outperforms other methods.

[The video of my presentation at ICAPS-16 is avaliable at YouTube.](https://youtu.be/x2mjIOkLQxw?t=42m57s) <!-- Embed? -->

## Code

[All codes we used for the experiments are available at my GitHub.](/software)

- A classical planner are available at my github
- Domain-specific solvers (sliding-tile, grid-pathfinding, multiple sequence alignment)
- Instance generators for (15-puzzle, 24-puzzle, grid-pathfinding, traveling salesperson problem, multiple sequence alignment)

## Open Questions

Many questions are yet unanswered including:

- Parallelizing width-based search (e.g. Iterative Width Search)
- Integrating CPU and GPU
- Parallelizing non-classical planning (MDP, POMDP, etc.)
- Abstract Zobrist hashing applied to two player games (MCTS etc.)

