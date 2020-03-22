# Assignment 2

## Problem 2:

### a) This is an instance of a Constraint Satisfaction Problem. What is the set of variables, and what is the domain of possible values for each? How do the constrains look like?

There are 81 variables, one for each square, n<sub>ij</sub>.

For each variable n<sub>ij</sub>, the domain is 1 - 9. The exception to this however are the variables that belong to the set of M variables that have been specified in the starting problem. For these variables, their domain is the value initially defined by the puzzle.

There are three contraints:
1. For each variable in n<sub>1j</sub> through n<sub>9j</sub>, no number in the domain can be repeated.
2. For each variable in n<sub>i1</sub> through n<sub>i9</sub>, no number in the domain can be repeated.
3. For each of the 9 different 3x3 boxes, no number in the domain can be repeated.

### b) One way to approach the problem, is through an incremental formulation approach and apply backtracking search. Formalize this problem using an incremental formulation. What are the start state, successor function, goal test, and path cost function?

Start state: All variables are unassigned, except for the M variables that are specified by the starting problem.

Successor function: Returns the Sudoku board with one newly assigned variable.

Goal test: Every variable is assigned a value within the given domain that satisfies all three contraints.

Path Cost: The number of variables that were defined by the agent.

### Which heuristic for backtracking search would you expect to work better for this problem, the degree heuristic, or the minimum remaining values heuristic and why?

We know that the degree heuristic is better when there is a tie among the MRV heuristic. This is often the case when choosing the first variable to assign in an incremental formulation. However, because the Sudoku problem has M variables already filled, we are not guaranteed to have a tie among the MRV heuristic.

Because it is unlikely that all unassigned variables have the same MRV in a given state, the degree heursitic is not best. Although the degree heuristic reduces the branching factor and can make some significant decisions early that prevent a lot of backtracking later on, it fails to see which variables are most liekly to fail soon.

I think that the MRV is likely to be a better heuristic, pruning the search tree by picking the variable that is most likely to fail soon. 

### What is the branching factor, solution depth, and maximum depth of the searchspace? What is the size of the state space? 

Branching factor: (n!) * 9<sup>n</sup>, where n is the number of nodes unassigned.

Solution depth: 81 - M

Maximum depth of searchspace: 81 - M

Size of the state space: <sub>((81 - M)! * 9<sup>81 - M</sup>)</sub> C <sub>(81 - M)</sub>

### c) What, is the difference between “easy” and “hard” Sudoku problems? [Hint: There are heuristics which for easy problems will allow to quickly walk right to the solution with almost no backtracking.]

An easy Sudoku problem is one where there is little or no backtracking.
Backtracking would occur when the MRV variable is chosen and we find a value variable with no legal values available.

Because the above chosen heuristic minimizes the number of searches by pruning, an "easy" Sudoku problem would be where the MRV heuristic continues to find variables with exactly 1 legal value available. This is the only scenario that guarantees no backtracking. 

Therefore, a "hard" Sudoku problem would be one where the MRV heuristic continues to return a variable with a high number of legal values available, thus increasing the probability of assigning the wrong value to this variable, and increasing the number of backtracks required in the problem.

### Another technique that might work well in solving the Sudoku game is local search. Please design a local search algorithm that is likely to solve Sudoku quickly, and write it in pseudocode. You may want to look at the WalkSAT algorithm for inspiration. Do you think it will work better or worse than the best incremental search algorithm on easy problems? On hard problems? Why?

