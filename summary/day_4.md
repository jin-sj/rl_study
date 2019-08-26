# Day 4, pages 37-45

## Summary (요약)
Methods to track non-stationary problem

### Give weight to recent rewards more heavily, use a constant stepsize param, alpha

Qk+1 = Qk + alpha x (Rk-Qk), where alpha is (0, 1]
...
Qk+1 = (1-alpha)^k x Q1 + sum from i to k (alpha x (1-alpha)^(k-i) Ri) <br>
This is a weighted sum, as the coefficients to Q1 and Ri add to 1. The weight also decays exponentially by the expoenent k-i <br>

Conditions for convergence
1. Sum from k=1 to inf, alpha k(a) = inf
    * Steps are large enough to eventually overcome any initial conditions or fluctuations
2. Sum from k=1 to inf, alpha (k(a))^2 < inf
    * Guarantee that eventually the steps become small enough to assume convergence
Both conditions are met in sampling-average case, but not for constant stepsize, where the second condition fails; <br>
The latter case never converges, but continue to vary in response to recent rewards, a desired trait in non-stationary targets

### Optional optimistic values
Set initial q(a) values to say, 5, which encourages intiatial exploration of all actions before the actions become disappointing; <br>
since q(a) is a normal distribution of mean=0 and var=1, even fully greedy actions ensure the exploration of all actions. <br>
This is a cheap easy trick, but is not suited to non stationary problems as this is only done in the beginning

### Upper-confidence-bound (UCB) action selection
Select non-greedy actions, taking considerationas to how close their estimates are to being maximal and uncertainties in these estimates. <br>
At = argmax [Qt(a) + c x sqrt(ln(t) / Nt(a))] <br>
where, <br>
c = degree of exploration <br>
sqrt = measure of uncertainty or variance in the estimate's value <br>

This is however difficult to apply for more advanced settings

### Gradient Bandits
Based on learning a numerical preference, Ht(a) for each action a. But the preference has not interpretation in terms of reward

Only the relative preference is important, <br>
Pr{At=a} =  e^(Ht(a)) / sum from b=1 to n of e^(Ht(b)) = Pi t (a) = Prob of taking action a at time t <br>
Update rule: <br>
Refer to page 46, but the gist is that, <br>
the Rt serves as baseline, and the reward is compared. <br>
If reward > Rt, prob of choosing a goes up <br>
If reward < Rt, prob goes down <br>
Non-selected's prob will go up


## Impressions (인상깊은점)
There are few relatively simple algorithms to deal with non-stationary targets, and surprisingly, these are SOTA.


## Questions (의문점)
UCB, Gradient show ways of balancing exploration and exploitation. However, there's not much logic apart from favoring those <br>
that haven't been picked (or adding exploitation a little). For algorithms that don't have exploration inherently built, <br>
that is, chosen manually, are there good ways to find the balance?
