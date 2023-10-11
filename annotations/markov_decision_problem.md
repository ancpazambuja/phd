# Markov Decision Problem (MDP)
Famework for sequential decision making of a single agent.

We can formally define an MDP with following elements:
- discrete time $t = 0, 1, 2, …$
- discrete set of states $s \in \mathcal{S}$
- discrete set of actions $a \in \mathcal{A}$
- stochastic transition model $P(s'|s,a)$
  - the world transitions stochastically to state $s’$ when the agent takes action $a$ at state $s$
  - "stochastically" means "past independency" 
- reward function $R: \mathcal{S} \times \mathcal{A} \rightarrow \mathbb{R}$
- an agent receives a reward $R(s,a)$ when it takes action $a$ at state $s$
- discount rate $\gamma$


## Markovian Transition Model
- $P(s'|s,a)$
- Must be fully observable
- Planning horizon can be infinite

## Discounted Future Reward Function
The main of the agent is maximize the discounted future reward function:

$$R(s_0,a_0)$$
