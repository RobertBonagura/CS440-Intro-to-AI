1-30-20
# Lecture 4 - A* Search, Minimax Search and Desiciion Trees
## Gradient Descent (review)
The gradient is found by calculating the derivatibe.

If it is 0, then it is a min, max or saddle point.

* The second dervitive test can determine which of the above three options it is, based on whether this second derivative is equal to <1, >1, or 0.

## A* Search
Orders nodes by the sum of the path length to the state and the heuristic of the state in a priority queue- guaranteed to give optimal path. (if using admissible heuristic)

### Admisible heuristics
One that never overestimates the cost from a node to the goal, such that
* h(s') <= path_length(s', s_goal)

### Proof that Admissible Heuristics will always return optimal path to goal

Write-up of proof will be provided online. Study this because there may be some variation of this proof on exam.

### Example using map of Texas:
Finding path from Brownsville to Amaraillo. Using direct Euclidean distance of city to Amarillo as heuristic value.

![map](../images/lec04_map.jpg)
![map](../images/lec04_chart.jpg)

h = direct Euclidean distance to Amarillo<br>
G value = distance(s_i, s') + h(s')

* Pop Brownseville on Queue.
* San Antonio = 300 + 445 = 745
* Pop San Antonio onto Q
* Laredo = 475 + 670 = 1095
* Austin = 380 + 500 = 885
* San Angelo = 505 + 315 = 820
* Pop San Angelo because it has shortest G value (820)
* El Paso = 905 + 440 = 1345
* Pop Austin
* Dallas = 560 + 330 = 890
* Houston = 530 + 605 = 1135
* Pop Dallas
* Wichita Falls = 700 + 220 = 920
* Pop Wichita
* Then we get Amarallo

Had we been doing Dijkstras, we wouldve had to expand out more cities.

#### How can we apply A* to problems with continuous stae spaces?
Robots in XY Plane?<br>
Problem is resolution - Think about a very high resolution. The faster the number of states exapnds the higher the computation cost. This will also scales with the number of dimensions added.

A* is bounded by the number of states so it increases in complexity with the number of states/dimensions.

One way to handle this would be to turn it into a graph problem.