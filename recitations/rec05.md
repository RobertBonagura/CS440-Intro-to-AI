# Probability Review
Looked at example of a joint distribution table

In example we look at in class, it
tells us probability of any combination of three events.

Be able to know:
* P(A)
* P(B)
* P(A | B) = ( P(A and B) / P(B))
* P(A | B or C) = P(A and (P(B or C)) ) / ((P(B) or P(C))

Also
* P(A | B) = [ P(B|A) * P(A) ] / P(B)

## Example 1
Bad news:

You've tested positive for a disease. The test is 99% accurate. 

Good news:

1 / 1000 people your age have the disease.

We want to find:

P(false positive) = P(_sick | test_is_positive)

P(test_is_positive | sick) = 99/100

P(test_is_neg | _sick) = 99/100

P(false positive) = P(_sick and test_is_postive) / P(test_is_positive)

= 1/100 * 9999/1000 ] / P(test_positive)

where P(positive) = P(+ | sick) P (sick) + (P(+|_sick)) P (sick)

= 1/100 * 9999/1000 ] / [ 99/100 * 1/1000 + 1/100 * 9999/1000]
= 9999 / 99+99999 = 99.02%

## Example 2
We have n coins, n-1 are normal, 1 coin is heads on both sides.

WE picked uniformly a random coin, fliped it and it landed heads,

What is the probability that is is fake after landing heads?

P(fake | lands heads) = P(fake and heads) / P(heads)

Bayes Rule:<br>
P(heads | fake) P(fake) / P(heads) = (1 * 1/n ) / [ (1 * 1/n * .5 * (n-1)/n ]
= 2 / n+1

