# Day 7, pages 61-69

## Summary (요약)
State representation, S_t is a short hand for S_t,i and for other variables (A_t,i , R_t,i , etc.) <br>
Unify discrete & continuous states by using 'absorbing state': A state that transitions to itself & reward = 0 <br>
Gt = sum fromk=0 to T-t-1 of gamma^k R_(t+k+1)  <br>
works for T=infinity or gamma = 1, but not both

### Markov Property
State: information avaiable to the agent
  * May be:
    * Immediate senses
    * Preprocessed info of original senses
    * Complex structures built over time
    * Should not expect to contain all info

Markov Property:
  * A state signal that summarizes past senses compactly, yet in a way that all relevant info is retained
  * Normally requires more than immediate senses, but never more than complete history of all past sensations

Formal definition: <br>
p(s', r | s, a) = Pr {R_(t+1) , s_(t+1)=s' | S_t, A_t} --- (a) <br>

### Markove Decision Process
  * RL's that satisfy the markov property
  * Finite MDP: Finite state and action space

Using the formal definition, (a), we can also define:
  * Expected rewards for state-action pair
  * State-transiiton Probability
  * Expected rewards for state-action-next action triplet

Transition Graphs are useful in summarizing the dynamics of a finite MDP
  * State node: Each possible state, big open circle
  * action node: Each possible action, small black circle
    * Transition properties leaving an action node always sums to 1.

![Transition Graph](https://github.com/jin-sj/rl_study/blob/master/assets/transition_graph.png)


## Impressions (인상깊은점)
A Markov state emcompasses all relevant information of a system about the complete sequence of positions that led to it.


## Questions (의문점)
Can non-Markovian states be reformulated such that they become close approximation of a MDP?
