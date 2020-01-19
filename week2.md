# Terms

- **expected return**: expected, discounted sum of *future* rewards: G_t -> R_t+1 + gamma R_t+2 + gamma^2 R_t+3 + ...
- **goal**: maximize expected return
- **episode**: independent chunks of MDP transitions that begin with initialization and end in a terminal state.
- **discounting**: 0 <= gamma < 1, multiplier, where G_t = R_t+1 + gamma R_t+2 + gamma^2 R_t+3 + ... to ensure that G_t remains finite


# Markov Decision Processes

- MDP is a graph based formalization of an agent interacting with an environment, performing actions, seeking reward.  In contrast to k-armed bandit, the action generally will change the state of the environment (e.g., think of autonoma moving to capture objects of value; they are in a different position on the board).  Agents actions have long-term consequences, influencing future available states (and thus future available rewards).

- *remember*: in contrast to backward looking reward estimates of the k-armed bandit, we express the goal here from state S_t as maximizing the total future (possibly discounted) reward

- agent is in state S_t from set \script S
- agent selects action a from set \script A(S_t)
- action results in some reward, and transition to new state S_t+1 from \script S
...
- agent reaches a terminal state, with total accumulated reward


# Episodic vs Continuing tasks

- episodic tasks end in a terminal state, continuing tasks do not terminate (thermostat)


# Reward Hypothesis (Michael Littman)

- "All goals can be described by the maximization of expected cumulative rewards" or:
- "Intelligent behavior arises from the actions of an individual seeking to maximize its recieved reward signals in a complex changing world"


# Things to look up

- what is definition of MDP?
- rewatch Michael Littman's video, he had a lot of interesting thoughts on behaviors, rewards, etc.
- inverse reinforcement learning
- evolutionary optimization
- meta-reinforcement learning


