# Problem 1

## a.

Given:<br>
P(movL | foodL) = 0.5<br>
P(movR | foodL) = 0.2<br>
P(stay | foodL) = 0.3<br>

P(movL | foodR) = 0.2<br>
P(movR | foodR) = 0.5<br>
P(stay | foodR) = 0.3<br>

P(movL | foodHere) = 0.25<br>
P(movR | foodHere) = 0.25<br>
P(stay | foodHere) = 0.5<br>

### Step 0: Ant is in cell 2
Because at this point we don't have any information about where the food might be, we have to assume that there is an equal probability among each cell to hold the location of the food.

P(cell_1 has Food) = ... = P(cell_5 has Food) = 1/5

Because we know how the ant is likely to move given where the food is, we can predict how likely each move the can make is using the probability of where the food is.

P(ant moving in direction A) =
<br> [P(food being to left) * P(moving in direction A | food is to the left)<br>+ [P(food being to right) * P(moving in direction A | food is to the right)]
<br> + [P(food is at current cell) * P(moving in direction A | food is in current cell)]

P(movL) = [P(foodL) * P(movL | foodL)] + [P(foodR) * P(movL | foodR)] + [P(foodHere) * P(movL | foodHere)]
<br>= [1/5 * 0.5] + [3/5 * 0.2] + [1/5 * 0.25]
<br>= 0.1 + 0.12 + 0.05 = 0.27

P(movR) = [P(foodL) * P(movR | foodL)] + [P(foodR) * P(movR | foodR)] + [P(foodHere) * P(movR | foodHere)]
<br>= [1/5 * 0.2] + [3/5 * 0.5] + [1/5 * 0.25]
<br>= 0.04 + 0.3 + 0.05 = 0.39

P(stay) = [P(foodL) * P(stay | foodL)] + [P(foodR) * P(stay | foodR)] + [P(foodHere) * P(stay | foodHere)]
<br>= [1/5 * 0.3] + [3/5 * 0.3] + [1/5 * 0.5]
<br>= 0.06 + 0.18 + 0.1 = 0.34

P(movL) = 0.27<br>
P(movR) = 0.39<br>
P(stay) = 0.34<br>

P(cell_1 has food) = ... = P(cell_5 has food) = 1/5
### Step 1: Ant moves right from cell 2 to cell 3

Because the ant moved from cell 2 to cell 3, the probability of the food being in each cell needs to be updated given the fact that the ant moved right.

For each cell i:<br>
P(cell_i now has food after step 1) = P(cell_i had food in previous step | ants current move)

P(cell_1 has food | movR) = P(cell_1 has food) * P(movR | cell_1 has food) / P(movR)<br>
= (1/5) * P(movR | foodL) / 0.39<br>
= (1/5) * 0.2 / 0.39<br>
= 0.1026

P(cell_2 has food | movR) = P(cell_2 has food) * P(movR | cell_2 has food) / P(movR)<br>
= (1/5) * P(movR | foodHere) / 0.39<br>
= (1/5) * 0.25 / 0.39<br>
= 0.1282

P(cell_3 has food | movR) = P(cell_4 has food | movR) = P(cell_5 has food | movR)<br>
= P(cell_3 has food) * P(movR | cell_3 has food) / P(movR)<br>
= (1/5) * P(movR | FoodR) / 0.39<br>
= (1/5) * 0.5 / 0.39<br>
= 0.2564

After Step 1:<br>
P(cell_1 has food) = 0.1026<br>
P(cell_2 has food) = 0.1282<br>
P(cell_3 has food) = 0.2564<br>
P(cell_4 has food) = 0.2564<br>
P(cell_5 has food) = 0.2564<br>

We can now calculate with what probability the ant will move next. Becuase we know the ant moves right in the next step, we only calculate the probability of the ant moving right because that is the only probability needed to determine the location of where the food might be in future steps.

P(movR after step 1) = [P(foodL) * P(movR | foodL)] + [P(foodR) * P(movR | foodR)] + [P(foodHere) * P(movR | foodHere)]
<br>= [P(cell_1 has food V cell_2 has food) * 0.2] + [P(cell_4 has food + P(cell_5 has food)) * 0.5] + [P(cell_3 has food) * 0.25]
<br>= [(0.1026 + 0.1282) * 0.2] + [(0.2564 + 0.2564) * 0.5] + [(0.2564) * 0.25]
<br>= 0.04616 + 0.2564 + 0.0641<br>
P(movR) = 0.3667


The probability that the ant moves again in step 2 is 0.3667

### Step 2: Ant moves right from cell 3 to cell 4<br>

P(cell_1 has food | movR) = P(cell_2 has food | movR)<br>
= P(cell_1 has food) * P(movR | cell_1 has food) / P(movR)<br>
= (0.1026) * P(movR | foodL) / 0.3667<br>
= (0.1026) * 0.2 / 0.3667<br>
= 0.056

P(cell_3 has food | movR)<br>
= P(cell_3 has food) * P(movR | cell_3 has food) / P(movR)<br>
= (0.2564) * P(movR | foodHere) / 0.3667<br>
= ((0.2564) * 0.25 / 0.3667<br>
= 0.1748

P(cell_4 has food | movR) = P(cell_5 has food | movR)<br>
= P(cell_4 has food) * P(movR | cell_4 has food) / P(movR)<br>
= (0.2564) * P(movR | FoodR) / 0.3667<br>
= (0.2564) * 0.5 / 0.3667<br>
= 0.3496

After Step 1:<br>
P(cell_1 has food) = 0.056<br>
P(cell_2 has food) = 0.056<br>
P(cell_3 has food) = 0.1748<br>
P(cell_4 has food) = 0.3496<br>
P(cell_5 has food) = 0.3496<br>

[note: the reasong these add up to 0.98 must be due to some rounding error.]

I can check back my results but I think this working towards the right path.