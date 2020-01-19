# Summary, follows Ch2 from Sutton and Barto

- **k-armed bandit problem**: k slot machines each return rewards according to a different random generator function.  You have N pulls to maximize your returns: which one(s) do you pull?  Generally, you sample each a bit to estimate its mean return; then "greedily" pull the lever to maximize reward.  You may decide at som

- **key terms**
    - action, a: yields a reward.  Multiple available, question is "which action to take next?"
    - reward, R_t: result of action, generally random, dependent on a, possibly dependent on t
    - value, q\*(a) \equiv E[R_t | A_t = a]: the expected value of a reward for a given action
    - estimated value, Q_t(a): an estimate of q\*(a) based on previous samples
    - policy: a method for selecting the next action
    - exploit vs explore: gather more information about which actions might yield high reward vs trying to optimize cumulative reward based on current information

- **general estimate update equation**: Q_n+1 = Q_n + alpha\*(R_n - Q_n), where Q_n+1 is the updated reward estimate, R_n is the latest observed reward, Q_n is the current estimate, and alpha is a stepsize/increment parameter.

- Robbins-Monro: what choice of alpha_n will converge, which will not?  https://en.wikipedia.org/wiki/Stochastic_approximation#Robbins–Monro_algorithm


# k-armed bandit

Setup: there are k slot machines in front of you, each with a unique random genarating function for returns. You have N total pulls at your disposal; how can you maximize your returns?
- argmax(Q_t(a)): the action a with the greatest estimated value; used to greedily optimize.


# how do you choose which to pull?

- sample average method: Q_n+1(a) = 1/(n)\*sum_j=1->n R_j.  Note that this is equal to:
    Q_n+1 = Q_n + 1/n(R_n - Q_n).  With sample average, 1/n decreases at each step; each R_j has equal weight for estimating the next return.

- if a fixed alpha is used, the estimate Q_n+1 = Q_n + alpha\*(R_n - Q_n) will exponentially weight more recent rewards as 1/n.  This can be used for nonstationary processes when you believe more recent rewards are a better predictor for the next reward.  This is an *exponential recency-weighted average*


- **incremental update rule**:

- **optimistc**:

- **upper confidence bound action selection**: optimistically assume the value of an action is the upper bound of a confidence interval.  The upper bound can be given by e.g. Q_t(a) + c\*sqrt(ln(t)/N(a)), N(a) number of times a has been chosen.  Don't know where the log comes from...


# Contextual bandits (John Langford)

Agents are often trained in a simulator, which may be quite different than a real world environment.  Are observations different?  Are rewards different?  Often yes.  Best path is to shift priorities, e.g. from temporal credit assignment to generalization, less control of the environment, limited by statistical efficiency rather than computational, consider features rather than state, evaluation rather than learning.

Example: personalized news.  Did person read an article?

see
- https://hunch.net/~rwil
- https://github.com/VowpalWabbit/vowpal_wabbit


# Thoughts

- the difference equation for the reward estimate is approx. a diff Eq dQ(n)/dn = alpha(R(n) - Q(n)).  What is the soln?

- Conditions on alpha for guaranteed convergence: https://en.wikipedia.org/wiki/Stochastic_approximation
