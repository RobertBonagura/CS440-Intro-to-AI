1-28-20
# Lecture 3 - Search & Genetic Algorithms

## Hill Climbing
Always select action tht leads to state with best heuristic

Let s = current state
* For all a e A
    * s' = tau(s,a)
    * h_a = h(s')
* Select a with larges reward h_a

Can be applied to Gradient ascent/descent<br>
Move in direction of highest increaser or decrease in heuristic.

### How does gradient descent algorithm know if it reaches minimum or maximum?
When the derivative is equal to 0.
### What are some methods for escaping local minimums?
Introduce some amount of randomness.
### What are some methods for approximating a gradient descent?
Randomly select nearby states and select the state that has the highest heuristic.

## Genetic Algorithms
A randomized local search strategy.

Genetic Algorithm:
```
population = init
while (!Solved){
    population = random_variation(population)
    select best n from population
}
```
Basic idea: Simulate natural selection, where the popultion is composed of *an evolving population of candidate solutions*.

The focus is on evolving a population from which strong and diverse candidates can emrge via:
* survival of the fittest
* crossover (mating)
* mutation

### Simple example: alternating string
Lets try to evolve a length 4 alternating string.
* Fitness function - number of consecutive occurences
* Evolve by flippung 1 bit

Initial population: C1 = 0011

We roll the dice and end up creating C1' = 1011 and C2' = 0001
* C1' = 1011 => score of -1
* C2' = 0001 => score of -2
* Keep C1'

Roll the dice again and end up creating C1'' = 1001 and C2'' = 1010.
* We run our solution test on each
* C2'' is a solution, so we return and are done.

### Genetic algorithm example: Robot path planning
Defining evolution function as the path that has the shortest distance passing through an obstacle.

A potential bottleneck could be an obstacle that is in the shape of an hourglass, where the path will get trapped inside a local minimum and never converge.

For this reason, we may want to have a stopping condition.

### What are some possible variations of a genetic algorithm?
Taking parts of one genetic algorithm and part of another.

This is what is called **crossover**.<br>
Look at *Alternating string with crossover*. [Note: There is a typo (or two) says he will fix before uploading slides.]

### What are some limitations of genetic algorithms?
Could get stuck in a local minimum.<br>
Need to have a scoring function and ....

Genetic algorithms are good when you can lock in the possible states needed in order to get to a solution.

## Search Trees
Represent this as a tree:
* Nodes represent states
* Edges represernt actions
* Root is current state
* Children - states you get by taking each action

BFS will find state, but is computationally expensive.

### Weighted Actions
* Each action has a cost associated with it
* c(a) - Cost of performing action a in state s

Use Shortes Path First (SPF) aka Djikstra's.<br>
Uses a priority queue ordered by path length.

#### SPF example
Map of driving routes in Texas
* Find shortest path first algorithm 

#### Problems with this algorithm
May be computationally expensive as you may have to look at every path to get answer

### Incorporating heuristics into Search Trees
Always select open state with best heuristic value
* Similar to choosing shortest path, though shortest path is defined on edge.
* Heuristic value is defined on node.
* Use priority queue that is defined by the value of the heuristic.
    * Exploring based on heuristic does not guarantee that we will find best path to the goal -- especially if we have a really bad heuristic, such as if our heursitic doesnt go a good job at preventing us from exploring a long branch of high valued heursitics when our solution is down a short path of poor heuristic values.
    * BFS does however, which is why we would like a BFS with herusitic values taken into consideration.

### A* Search
Order nodes by sum of path length and heuristic.<br>
Priority queue order by path(s) + h(s)<br>
Will find optimal path if using admissible heruistic

Basically using both weighted paths and weighted nodes.

#### Admissable Heuristics
Never overestimates cost to goal (always less than optimal path)

What can we say about A* search with admissable heuristic?
* You are going to guarantee to explore the tree in an order that will bring you the optimal path.

