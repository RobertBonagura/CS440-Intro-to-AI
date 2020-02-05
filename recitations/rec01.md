2-5-20
# Recitation 1
Zach Langley: zach.langley@rutgers.edu

Office Hours: Wednesday 5:00pm - 6:00pm CoRE 246

## BFS and DFS search algorithms
### DFS - Depth First Search
DFS will find goal state eventually, however may visit far more nodes than neccessary.

Uses stack.

### BFS - Breadth First Search
Uses queue instead of stack, and guarantees to find optimal solution.

Note it may not find the optimal path in the optimal amount of time, but it will find the optimal path.

### A* Search
As long as heuristic is admissible (meaning it always underestimates true distance), it will also find the optimal path. 

A heuristic needs to be less than the number of moves to the solution in order to be admisible.

By using an admissible heuristic, it can run more efficiently than BFS.

#### Possible heurisitic of 8 puzzle

* A heuristic of 0 is basically BFS, it tells you nothing

* For 8 tile puzzle, an admissible heurisitic is the number of misplaced tiles. This is because you have at most a heuristic of 8, which will take at least 8 moves because you can only fix at most 1 misplaced tiles for each tile.

* A better heuristic is to sum up each tile's manhattan distance to its proper position. This is valid because you can only move at most one tile, at most one unit of distance.

The A* Search uses a priority queue like BFS

The priority in the queue is based on *g(s)* + *h(s)*, such that *g(s)* is the distance from the initial_state to *s*. 

#### Challenges
Keeping track of visiited states can become expensice in terms of memory.
