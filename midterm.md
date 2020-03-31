Robert Bonagura
# Midterm
## Question 1
#### 1. Define a State space, Action space, transition function and reward function for this problem.

The initial state *S<sub>i</sub>* of this problem consists of an n by m grid, that is represented with rows *R<sub>1</sub>* through *R<sub>n</sub>* and columns *C<sub>1</sub>* through *C<sub>m</sub>*. For every state *S<sub>k</sub>*, there are *n* x *m* cells, each denoted as *X<sub>R, C</sub>*. In the initial state, every cell in the grid is initally undefined, though contains a potential domain of *R* or *Y*. The **state space** consists of this initial state, as well as the set of actions and the corresponding transition function.

The **Action space** is the set of actions available at each state, where at any given state an agent can select between columns *C<sub>1</sub>* through *C<sub>n</sub>* (such that each column is not full). For each column *C<sub>k</sub>*, Action *A<sub>k</sub>* is defined as the agent dropping their token into *C<sub>k</sub>*, thus marking *X<sub>min, k</sub>* where *X<sub>min, k</sub>* is the lowest row cell in *C<sub>k</sub>* undefined.

Because the State space state consists of *n* x *m* cells, the **transition function** *R()* can be defined as *R(S, A<sub>k</sub>*) , where action *A<sub>k</sub>* is performed on state *S<sub>k</sub>*, thus returning state *S<sub>k+1</sub>*.

The **reward function** will be defined as the number of consecutive cells in a horizontal, vertical or diagonal line a player has marked their corresponding color, *R* or *Y*.

#### 2. What would be a good heuristic to use for this game and why? (note that this heuristic does not have to b aadmissible).

Outside of placing a fourth consecutive token and winning the game, I think the most important decision a player can make is to stop the opposing player from placing their fourth consecutive token into a cell. For this reason, I will define *h(x)* as the number of consecutive cells the player will have that includes cell *X*. If however, a cell *X* would give the opponent a fourth consecutive cell, *h(x)* would be defined as 3.5 . This would ensure that the heuristic value of a cell is consistent with the strategy described above, prioritizing winning the game first, preventing the opponent from winning second, and then thirdly maximizing the number of consecutive cells.

#### 3. Given the board state shown in Figure 2, use the minimax algorithm to determine the sequence of moves that 2 optimal players will make. You should show all work, the tree produced by the minimax algorithm and and indication of which child will be selected by the player at each internal node.

I have created a tree to show how two optimal players would continue the game of connect 4 based on the Board state from Figure 2. Each player will choose the action that returns the cell with the highest value returned by the heursitc function I defined. 

I have only expanded the nodes that would be explored in the minimax algorithm.

Square nodes represent a turn for *Red* and triangle nodes represent a turn for *Yellow*.

[insert picture here]

---
## Question 2
#### 1. What is the minimum number of cells that the shortest path first algorithm needs to expand in the grid shown in Figure 3 before finding a path to the goal (and why)?

We can find the minium number of cells needed to expand by counting each cell at every frontier untill we reach the first frontier where the goal cell is a neighbor.

![](./Question2-1.jpg)
<br>
<br>
<br>
So including the start and goal state, shortest path first would visit at a minimum 16 cells.

#### 2. Define an admissible heuristic for this problem. Show that this heuristic is admissible.

An admissible heuristic for a given cell *c* would be defined by looking at all of it's neighbors cells. If one of it's neighbors is the goal cell, *h(c)* is 1. If none of its neighbors are the goal cell, then *h(c)* is 2.

This heuristic is admissible because it never overestimates the cost of reaching the goal. 
* We only set *h(c)* to 1 if we know that we are 1 cell away from the goal.
* If none of cell *c*'s neighbors are the goal cell, then we can not guarantee how far we are. Therefore, a heuristic of 2 is admissible becauase if the goal were 1 cell away, then it would be a neighbor of *c*.

#### 3. What is the minimum number of cells A* wtih your heuristic needs to expand the grid shown in Figure 3 before finding a path to the goal.

The minimum number of cells visited by A*, based on my heuristic, is going to the same as the minimum number of cells visited by shortest path first, 16. What makes A* better is that the minimum number of cells expanded by A* will be the same as the maximum number of cells. This is because on the final frontier it will always expand the node that is adjascent to the goal fist.

For shortest path first on the other hand, the maximum number of cells expanded on on the final frontier is not guaranteed to be the same as the minimum number of cells expanded on the final frontier. For instance, if a heuristic was not involved, the shortest path first could potentially visit this many cells worst case scenario.

![](./Question2-3.jpg)
<br>
<br>

---
## Question 3
#### 1. If you divided these characters based on the weapons what would be the information gain.

#### 2. Construct a classification tree that uses the attributes provided (Weapon, Height, Armor and Age) to classify the characters.

---
## Question 4
