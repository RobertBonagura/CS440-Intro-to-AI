2-11-20
# Lecture 07 - Decision Trees and Inductive Learning
Absent

## Building Decision Trees: Example
### What is a good attribute?
We want to grow a simple tree
* A good attribute prefers attributes that split the data so that each successor node is as *pure* as possible.
    * i.e,  the distribution of examples in each node is so that it mostly contains examples of a single class
In other words:
* We want a measure that prefers attributes that have a high degree of "order":
    * Maximum order: all examples are of the same class
    * Minimum order: All classes are equally likely
    * **Entropy** is a measure of un-orderedness

Entropy is the amount fo information that is contained.
All examples of the same class yields no information.

### Entropy for Binary Classification
* S is a set of examples
* p_(+) is the proportion of examples in class (+)
* p_(-) = 1 - p_(-) is the proportion of exmaples in class (-)

Entropy:<br>
E(s) = -p_(+) log_2 p_(+) - p_(-) log_2 p_(-)

Entropy is the amount fo unorderedness in S

For a complex (non-binary) set, Entropy is given by:
E(S) = (The sum of x in X) -p(x) log_2 p(x)

### Average Entropy of a Split