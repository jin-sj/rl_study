# Day 3, pages 27-37

## Summary (요약)
RL uses evaluative feedback: how good the action taken is, but not whether it is the best or the worst action possible
Supervised users instructive feedback: indicates the cor- rect action to take, independently of the action actually taken

N-bandit problem: A simplified setting (non-associative) to explore RL
An n-bandit problem is:
* Repeatedly faced with n actions
* Each action yields a numerical award from a stationary distribution, depending on the action
* Need to maximized the reward, over some time period (example, 2000 steps)

Many ways to select actions:
Greedy: Choose action with highest value
Exploration: Choose an action randomly, independent of the value
e-greedy: Choose greedy, except for some probability e, where a random action is done
  * Tends to perform better than pure greedy, because it is able to update uncertain values, and may find better values
  * Depends highly on the assignment; if high variance, e-greedy > greedy. if 0 variance, e-greedy < greedy
  * Even for deterministic * stationary targets, e-greedy would be better

Math: <br>
Qt(a): Estimated value at time t <br>
qt(a): True value; mean reward when an action is selected <br>
Qt(a) = (R1 + R2 + ... Rt) / Nt(a) <br>
Where Rt is reward at step t <br>
Nt(a): Number of times action 'a' was selected <br>

Greedy: <br>
At = argmax Qt(a) <br>
where argmax represents the value of a where the expression is maximized <br>

Update rule <br>
Qk+1 = 1/k * (R1 + R2 + ... + Rk) <br>
Qk+1 = Qk + 1/k [Rk-Qk] <br>

Generally follows the form: <br>
newEstimate <- oldEstimate + stepSize[Target - oldEstimate] <br>


## Impressions (인상깊은점)
RL systems are not necessarily deterministic & stationary, which may make it hard to find the optimal policy


## Questions (의문점)
Is there a way to evaluate if a system is deterministic or stationary?
