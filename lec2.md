[Course Website](https://robotics.cs.rutgers.edu/cs-440-intro-to-artifical-intelligence-spring-2020/)

# Lecture 2 <br> Intelligent Agents & Optimization Problems

## Last class
How to define each of the following:

Environment<br>
Perceptions/Observations - inputs the agent receives<br>
Actions - what the agent can do to effect its environement<br>
Evaluation - feedback given to the agent on how it performs its task
AI Problem definition<br>
State definitions, Examples, Conventions and Challenges

---
## Transition
Transition - how do actions effect state
transition function tau, and its examples.
Basically takes in a state and an action and outputs a new staet
    only for the deterministic case.

## Sudoku example:
The environment is the board iteself.<br>
The state is a 9x9 array of integers.<br>
The action is inserting a number into the table.<br>
The observation is the state of the board<br>
The transition is adding number to state.<br>
The evalutation is to check that each row and column contains no duplicates, and are all filled in.<br>
Positive evaluation score for this
Negative evaluation for an invalid state

## Reviewing Evironments and Properties.
Sudoku is fully obeservable because we can view the complete state of the
environment. (dont turn a fully observable or deterministic into partially
or stochastic if you dont have to)

An example of Deterministic, Fully Observable Problem<br>
Given
* A fully observable environment
* Observations are state of environment<br>
* A set of possible actions, A <br>
* An evaluator (e.g. a set of goal states) <br>
* For every s,a tao(s,a) --> s'

ex: a robot in a 3x3 grid world
* State: 3x3 array with position of robot marked.
* Observation: cell robot is located in
* A set of possible acctions : U, D, L, R
* The evaluator : Goal cells with scores of each cell.
How to select an action?
    Select the action that gets you to the state with the highest reward.
    Defining this decision is more complicated. (ehat if too cells away
is the highest reward?)

## Heuristic
Estimate of utility of state. <br>
Real value indicating utility of state. <br>
Must be defined for all states in S. <br>
    
Convention: h(s) <br>
Examples:
* Chess: Value of pieces captured/lost
* Robotics: Euclidian distance from goal

What would be a good heuristic for Sudoku?<br>
- Higher number of rows or columns filled in

Can we combine greedy search with heuristics? <br>
Hill Climbing problem<Br>
Always select the action that leads to the state with best heuristic.

Applying hill climibing to continuous state spaces.
2D Euclidean space
Gradient ascent/ descent - move in direction of gradient.
 - relative min and max can throw off this algorithm

## Look Ahead Search
How can we represent a look ahead search computationally?<br>
- Have an initial state, then a set of potential actions which each lead
to a different state. We can create a tree (Think depth first search)
- Represent as a tree
    - Nodes represent states
    - Edges represernt actions
    - Root is current state
    - Children - states you get by taking each action 

Depth First Search algorithm - push to stack <br>
Breadth First Search algorithm - push to queue <br>
    
### Avantages and drawbacks of DFS and BFS
advantage - guaranteed to find goal if it exists<br>
drawback - maybe visiting more nodes than you have to.

BFS will return optimum solution, and depends less on luck.
A BF-like search can be prioritized with heuristics.

---
## Some review/clarification of topics covered last class.

Goal-based agent vs Utility-based agent
    Goal agent considers just the goal (trees covered today are goal-based).
    Utility has a utility or a heuristic function, and looks to the
    evaluation of the state.
