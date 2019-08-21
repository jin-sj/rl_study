# Day 1, pages 1-15

## Summary
Outlines the basic characteristics, formulation and challenges in RL.
Main characteristics are that:
1. RL is a closed-loop system (system involving feedback); system's actions influence later inputs
2. No direct instructions on actions
3. Consequences of actions are played out over time

Formulation:
A system where you can define:
1. Sensation: Sensing of the environment agent is acting upon
2. Action: Actions the agent can perform that can affect the state
3. Goal: Overall goal of an agent (winning the game, etc.) relating to the state of the environment

Challenges:
1. Exploration vs. exploitation
  * Exploration: Must explore to find new states of the environment
  * Exploitation: Use a learned policy to choose the optmized action (max reward/value)
2. Whole problem vs. subproblems

Four elements of RL:
1. Policy: Agent's way of behaving at a given time
2. Reward signal: Goal in a reinforcement learning problem. Usually given by environment, as an immediate feedback (pain vs. pleasure)
3. Value function: What's good in the long run
  * RL agent should be maxmizing the value, not reward
  * Values are estimated and re-evaluated; hard to estimate
4. Model of environment: Mimic the behavior of the environment, or more generally, something that allows inferences to be made about how the environment will behave
  *  Models are used for planning; decide on the course of actions by considering possible future situations

Temporal-difference learning: Earlier state is updated after taking a greedy step \
V(s) <- V(s) + alpha [V(s') - V(s)]


* s: state _before_ greedy move
* s': state _after_ greedy move
* alpha: small positive fraction; step-size parameter that influences the rate of learning
* V(s): Value of state s

In words: Value of earlier state is updated by adding a multiple of the difference of value of new state and value of old state

## Impressions
* RL is another category in machine learning, it is not categorized within supervised or unsupervised learning
* RL actively uses the information in its state/environment, where evolutionary/genetic algorithsm do not
* RL tries to mimic the way people learn; people act to achieve a goal, which solves subproblems on the way (goal: Prep breakfast vs. pour milk, cereal, etc.)


## Questions
Can RL be used in common DL problems, such as computer vision? How would a CV problem be formulated in RL?
* Agent?
* Sensation?
* Action?
* Goal?
* How to exploit vs explore in computer vision problem?
