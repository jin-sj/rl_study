# Day 8, pages 70-79

## Summary (요약)
### Value Functions
  * Functions of states (or of state-action pairs) that estimate how good it is for the agent to be in a given state
  * How good := expected return

### Policy, pi
  * Mapping from each state, s in S, a action in A, to the probability, pi(a|s), of taking action 'a' when in state 's'

### Value function: v_pi (s)
  * Value if state s under policy pi
  * Expected return when starting in s and following pi
![Value-function](https://github.com/jin-sj/rl_study/blob/master/assets/value_function.png)

### Action-value function: q_pi(s, a)
  * Value of taking action a in state s, under policy pi
![Action-value Function](https://github.com/jin-sj/rl_study/blob/master/assets/action-value_function.png)

### Monte-Carlo:
  * Estimation method through averaging over many random samples

### Bellman Equation for Value function
  * For each triple (a, s', r)
    * Compute the probability: pi(a|s)p(s',r|s,a)
    * Weight the quantity in brackets by the probability
    * Then sum over all possibilities to get an expected value
![Bellman equation for value function](https://github.com/jin-sj/rl_study/blob/master/assets/bellman_eq_for_value_function.png)

### Optimal value functions
* pi >= pi' if and only if v_pi (s) >= v_pi' (s) for all s in S
* There is at least one policy that is better than, or equal to all other policies, denotes pi_star

Optimal state-value function
* Defined as:
![Optimal state-value function](https://github.com/jin-sj/rl_study/blob/master/assets/optimal_state_value_function.png)

Optimal action-value function:
* Defined as:
![Optimal action-value function](https://github.com/jin-sj/rl_study/blob/master/assets/optimal_action_value_function.png)
* In terms of v_star:
![Optimal action-value function in terms of state-value function](https://github.com/jin-sj/rl_study/blob/master/assets/optimal_action_value_function2.png)

### Bellman Optimalilty function
* Value function
  * Any policy that is greedy w/ respect to optimal evalution function v_star is an optimal policy
  * One-step-ahead serach
![Bellman Optimality Value function](https://github.com/jin-sj/rl_study/blob/master/assets/bellman_optimal_value_function.png)

* Action-value function
  * Makes it easier for choosing optimal actions
  * Doesn't require one-step-ahead search
    * Just findaction that maximizes q_star(s,a)
  * "essentially caches the results of all one-step-ahead searches"
  * Knows optimal values w/o knowing anything about possible successor states and their values
    * "w/o having to know anything about environment's dynamics"
[Bellman Optimality action-value function][://github.com/jin-sj/rl_study/blob/master/assets/bellman_optimal_q.png]


For finite MDP's, Bellman Optimality equation has a unique solution, independent of policy
  * Is a system of equations, one for each state. If N states, than N equations
  * If dynamics of environment is known, p(s',r| s,a), than the system of equations can be solved
  * However, this is akin to exhaustive search, and the required assumptions are rearely true
    * Accurately know the dynamics of the environment
    * Have enough computation resources to compute solution
    * Markov Property

## Impressions (인상깊은점)
Greedy choices on optimal value-state or action-value functions are optimal policy/ non-policy moves

## Questions (의문점)
How does the math go from line 2 to 3?
![Bellman equation for value function](https://github.com/jin-sj/rl_study/blob/master/assets/bellman_eq_for_value_function.png)
