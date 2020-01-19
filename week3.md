# policies

 - \pi(s) is the function that determines policy a from state s.
 - \pi(a|s): stochastic policy, probability of a given s

 - mdp requires that policy depends *only on the current state*.  The action cannot depend, for example, on the previous action when that state was visited.


 - value function: the expected return from a given state, v_pi(s) = E_pi[ G_t | S_t = s], according to a specify policy

 - action value function: q_pi(s, a) = E_pi[G_t | S_t=s, A_t = a]