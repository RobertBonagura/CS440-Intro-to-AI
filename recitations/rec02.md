2-12-20
# Recitation 2 - Minimax
## Minimax
Minimmax alternates between Min and Max players, each agent having control of alternating levels of tree.

To use Minimax in practice, there has to be some type of cutoff in terms of depth, or else computation becomes very expensive.
* Can create the optimal tic-tac-toe player.

```
minimax(state, player)
    <base-case-here> // could be reached goal state or cutoff d
    if player = MAX
        return max(minimmax(sucessor-states, MIN))
    else 
        return min(minimax(successor-states, MAX))
```
Minimax relies heavily upon recursion.

## Alpha Beta Pruning
Augmenting minimax to add some alpha beta values.
```
mm(state, player, a [-infinit], b [infinit])
    if player == MIN
        for succ in children(state)
            value = mm(state, MAX, a ,b)
            b = min(val, b)
            if a >= value
                return value
    else player == MAX
        for succ in children(state)
            value = mm(state, MIN, a, b)
            if b <= value
                return value
            a = max(a, value)

```
If you know your opponent wants to minimize your score, and you can see that your option A will guaranteee some value, and your option B will allow your opponent to choose a value lower than the return of A, you are using pruning to avoid considering all of the other possible options your opponent can make if you choose B.