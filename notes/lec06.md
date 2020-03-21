2-6-20
# Lecture 6 - Alpha-Beta Pruning and Decision Trees
absent

## Adversarial Search
When an agent is competing against another agent.

Agents are tyying to accomplish conflicting tasks
* Trying to stop other agent from reaching its goal
* Other agent trying to stop you from reaching your goal

Examples include Chess, checkers, tic-tac-toe, etc

What makes adversarial problems difficult is the need to predict the actions of the other agent.

**Pruning** allows us to ignore portions of the search tree that make no difference to the final choice.

Observation:
* A good state for you is a bad state for your opponent.
* A bad state for you is a good state for your opponent.
* Assume your opponent will always pick the worst state for you.

Strategy:
* Select action where opponent's best move lead to best state for you.
* Select action with best worst state

## Minimax Search
```
function minimax(s, d, bMaxPLayer)
    if d = 0 or goal(s)
        return h(s)
    if bMaxPlayer
        v = -infinit
        for each action a
            s' = tau(s,a)
            v = max(v, minimax(s,d-1, FALSE))
        return v
    else
        for each action a
            s' = tau(s,a)
            v = min(v, minimax(s, d-1, TRUE))
        return v
```

Basically minimax does as follows:
* Look ahead d moves
* Compute h of all leaves
* Inductively compute values for internal nodes from values of children.
    * Max Step (Agents turn): Set values to be max value of children.
    * Min Step (opponents turn): Set value to mix of children.
* Select child of root that has highest value.

## Alpha-Beta Pruning
The problem with minimax search is that the number of game states it has to examine is exponential in the depth of the tree. The trick here is to cut the exponent in half by not looking at every node in the game tree.

General Principle: Consider node *n* any where in the tree such that Player has a choice of moving to that node. If Player has a better choice *m* either at the parent node of *n*, or at any choice point further up, then *n will never be reached in actual play*, so it does not make sense to further expand any of the children of n.

Worst case this runs in O(|A|^d)<br>
Best case this runs in O(|A|^(d/2))

What impacts how long this search takes?
* The order in which youe explore the children.
* Maximizing Steps: Want to expand children with higher value first.
* Minimizing Steps: Want to expand children with lower value first.

How do you accomplish this?
* Order children based on their heuristic value.

## Decision Trees
Nodes are states
* At each state you need to make a decision specific to that state
* Edge for each choice
* Edge leads to state obtained by selecting choice

Effectively, actions are choices
* Different from other examples because actions are different for each state

### Building a Decision Tree example
