# Computational Intelligence - Lab 3: n^2-1 Puzzle

The goal of this lab is to solve efficently a generic n^2-1 puzzle 
(also known as Gem Puzzle, Boss Puzzle, Mystic Square, etc. (https://en.wikipedia.org/wiki/Magic_square)) using path-search algorithms.
The problem consists of rearranging a board with numbered tiles into a specific goal configuration by moving tiles into an empty space.

## Strategies Implemented
(Source: lecture held on date 14/11/2024)

### A*
The A* algorithm is an informed search method that combines the cost of reaching a state `(g)` with a heuristic estimate of the cost to reach the goal `(h)`. The priority function for this algorithm is defined as `priority(s) = g(s) + h(s)`.
- `g(s)`: The cumulative cost to reach state `s` (calculated from the initial state).
- `h(s)`: A heuristic estimate of the cost to reach the goal from state `s`. The heuristic used in this implementation is the misplaced tiles heuristic, which counts the number of tiles not in their goal positions, ignoring empty tiles.
This algorithm is optimal when the heuristic is admissible (never overestimates the true cost).

### Breadth-First Search
BFS is an uninformed search method that explores the state space level by level. It does not use a heuristic and treats all actions as having equal cost.
The priority is determined by the order of insertion, ensuring a FIFO behavior, this guarantees that all states at the current depth are explored before moving deeper.
It lways finds the shortest solution in terms of the number of actions, but it's computationally expensive for large puzzles.