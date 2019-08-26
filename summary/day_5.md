# Day 5, pages 46-52

## Summary (요약)
Hard to define which algorithm (e-greedy, gradient bandit, UCB, greedy with optimisit init) is the best.
However, for the 10-bandit problem, we can see that UCB tends to perform best.

When evaluating an algorithm, must look at the sensitivity to params, as well as performance.
All algorithms are relatively insensitive; they perform generally the same across a range of values.
However, they perform best with intermediate values for the parameters.

There are algorithms that could try to solve the balancing of exploration and exploitation
1. Gittins Indcies
    * Requires tat the prior distributino of possible problems is known
    * Theory & computational tractibility fails to generalize for the full RL problem
2. Another algorithm for computing the Bayes optimal way of balancing
    * Computationally intractable; yields a tree of 2^2000 leaves for a 2-bandit problem at 1000 steps
    * Might have an efficient algorithm to approximate

## Impressions (인상깊은점)
Feels like the RL field still lacks a lot of the theoretical foundations, and still has a lot of areas for research


## Questions (의문점)
What does it mean by a full RL problem?
