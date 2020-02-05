2-4-20
# Lecture 5 - Minimax Search and Decision Trees
## A* Search (Review)
Order nodes by sum of path length and heuristic

Priority queue order by path(s) + h(s)

Will find optimal path if heuristic is admissible

**admissible heuristic**

### Can we apply A* to chess?
With A* you need to know what the outcome state of your action is.

**Adversarial Seach** is more difficult. In chess, you don't know the outcome of the state you choose (i.e., your opponents response to the state you choose).

**Adversarial problem** - The agent is competing another agent (whether computer or human) OR agents are trying to accomplish conflicting tasks.
* Examples: Chess, checkers, tic-tac-toe, any game where you need to predict the actions of other agent.

#### What makes these games dificult?
You need to predict the actions of another agent.

#### Observations
A good state for you is a bad state for your oponent.<br>
A bad state for you is a good state for your opponent.<br>

Assume opponent will alwasy worst state for you

Strategy:
* Select action where opponents best move will lead to best state for you
* Select action with best worst state

In class we drew a tree diagram. What is interesting to think about is that for each level of the tree, it alternates between being a state that the opponent chooses and a state that the user uses.

If its your turn, choose best action. If its their turn, choose best worst state.

## Minimax
#### Minimax search example
#### Tic-Tac-Toe example
For Tic-Tac-Toe example, look at every possible action, and what move the other agent might make.

#### How can you adapt minimax search to games with multiple adversaries?
examples: poker, chinese checkers

One thought is to use a seperate hueristic for each opponent. You could alternate every n level of a tree for the number of n agents. 

At each level you have to ask : Which players turn is it? What is their heuristic?
* Make your decisions based on the order of turns.

## Decision Trees
At each state you need to make a decision specific to that state.<br>
Edge for each choice <br>
Edge leads to state obtained by selecting choice.

Actions are choices
* Different from toher examplesbecause actions are different for eachs tates.

Example: navigating a road map
