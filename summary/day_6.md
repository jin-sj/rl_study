# Day 6, pages 53-60

## Summary (요약)
### Mathematical representations of RL: Markov Decision Process
* Agent: Learner & decision maker
* Environment: Something that the agent intereacts with, comprising everything outside the agent
  * Anything that cannot be changed arbitrarily by the agent. Boundary is specified where there is limit on agent's absolute control, not knowledge
* Agent's policy (pi s): Mapping of states to probabilities. Specify how the policy changes as a result of experience

eg)
* States & actions can be structure representations (vectors) where rewards are single numbers
* States can be inside a robot, such as battery level
* Source of reward need to be outside of the agent

### Reward hypothesis
* Goals & purposes can be well though of the expected value of the cummulative sum of a received scalar signal (reward)
* Reward signal for what you want to acheive, not how you want it achieved

#### Objective of learning: Maximize cummulative reward
Gt = Rt+1 + Rt+2 + ... + RT where T is the final stemp
* If agent-env interaction breaks down naturally into subsequences, we call it __episodes__
* Continuing tasks: Where interaction cannot be broken down naturally, and there is no terminal state.
  * Could be a problem because Gt, the value we want to maximize, could be infinite

#### Discounted Reward: Introduce discount factor
Gt = Rt+1 + gamma Rt+2 + gamma^2 Rt+3 + ... = sum from k=0 to infinity of gamma^k x R_t+k+1
* 0 <= gamma <= 1
* if gamma = 0, agent is concerned in maximizing immediate rewards; agent chooses At as to maximize Rt+1
* if gamma close to 1, agent takes future awards more strongly


## Impressions (인상깊은점)
Any goal can be represented by a well-defined goal that aims for what you want to achieve, not how you want to achieve. <br>
Distinguishing Agent vs. environment may not always be straight forward


## Questions (의문점)
What other ways can we represent the cummulative reward to put emphasis on the future reward?
