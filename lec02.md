[Course Website](https://robotics.cs.rutgers.edu/cs-440-intro-to-artifical-intelligence-spring-2020/)

# Lecture 2 - Intelligent Agents & Optimization Problems: Local Search Problems

## Last class
How to define each of the following:

**Environment** - The world in which the problems takes place.<br>
**Perceptions/Observations** - Inputs the agent receives<br>
**Actions** - What the agent can do to effect its environement<br>
**Evaluation** - The feedback given to the agent on how it performs its task.<br><br>
AI Problem definition<br>
State - Data structure representing environment incorporating al relevant information.

---
## Transition Function
**Transition** - how do actions effect state. <br>
Transition function (uses tau)<br>
Represented by s' = tau(s,a).<br>
Basically takes in a state and an action and outputs a new state.
(only for the deterministic case)

## How would we formulate Sudoku as an AI problem:
The environment is the board iteself.<br>
The state is a 9x9 array of integers.<br>
The action is inserting a number into the table.<br>
The observation is the state of the board<br>
The transition is adding number to state.<br>
The evalutation is to check that each row and column contains no duplicates, and are all filled in.<br>
Positive evaluation score for this
Negative evaluation for an invalid state

### Reviewing Evironments and Properties.
Sudoku is fully obeservable because we can view the complete state of the environment.

## Deterministic, Fully Observable Problem
Given
* A fully observable environment
* Observations are state of environment
* A set of possible actions, A
* An evaluator (e.g. a set of goal states)
* For every s,a tao(s,a) --> s'

### ex: a robot in a 3x3 grid world
* State: 3x3 array with position of robot marked.
* Observation: cell robot is located in
* A set of possible acctions : U, D, L, R
* The evaluator : Goal cells with scores of each cell.
How to select an action?
    * Select the action that gets you to the state with the highest reward.
    * Defining this decision is more complicated.

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

Can we combine greedy search with heuristics? <br> Yes. an example is the Hill Climbing problem<br>

Applying hill climibing to continuous state spaces.<br>
2D Euclidean space
Gradient ascent/ descent - move in direction of gradient.
 - relative min and max can throw off this algorithm

## Look Ahead Search
How can we represent a look ahead search computationally?<br>
- Have an initial state, then a set of potential actions which each lead
to a different state.
- Represent this as a tree
    - Nodes represent states
    - Edges represernt actions
    - Root is current state
    - Children - states you get by taking each action 

Depth First Search algorithm - push to stack <br>
Breadth First Search algorithm - push to queue <br>
    
### Avantages and drawbacks of DFS and BFS
advantage - guaranteed to find goal if it exists<br>
drawback - maybe visiting more nodes than you have to.

BFS will return optimum solution, and depends less on luck.<br>
A BF-like search can be prioritized with heuristics.

---
## Some review/clarification of topics covered last class.

Goal-based agent vs Utility-based agent
* Goal agent considers just the goal (trees covered today are goal-based).
* Utility has a utility or a heuristic function, and looks to the
evaluation of the state.
