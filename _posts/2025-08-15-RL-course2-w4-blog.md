# Reinforcement Learning Course 2 - Week 4

## TLDR

- GPI for TD: SARSA


## SARSA: What is it?


Remember the Temporal difference method policy update equation? 

$$\begin{equation}
V(s_t) \leftarrow V(s_t) + \alpha [R_{t+1} + \gamma V(s_{t+1}) - V(s_t)]
\end{equation}$$

This equation updates the state-value function only. The value of a state is determined by the immediate reward received and the estimated value of the next state. But the reward also depends on the action taken. We are missing this part. If you are right at the front of the goal post without any defenders and the goalkeepr, if you do not shoot - in other words take action, you will not get any reward! So the action is also important. Sometimes the action is more important than the state itself (for example, in the above case).

Now what if we want to update the action-value function instead of the state-value function? We can do that by updating the state-value function into an action value function, that is by replacing $V(s)$ with $Q(s,a)$. The $Q$ is the value of a certain action $a$ taken at a certain state $s$. The update equation becomes:

$$\begin{equation}
Q(s_t, a_t) \leftarrow Q(s_t, a_t) + \alpha [R_{t} + \gamma Q(s_{t+1}, a_{t+1}) - Q(s_t, a_t)]
\end{equation}$$

This is the SARSA algorithm. The name SARSA comes from the fact that we are using the set of State, Action, Reward, State, Action to update the action-value function.

This SARSA algorithm is the Generalized Policy Improvement for TD algorithm. Just like we had discussed in [Course 1 Week 4 blog](https://sezan92.github.io/2024/07/03/RL-course1-w4-blog.html).

## TODO
SARSA intuition

Let's start with my favourite game Football.  Suppose we are learning by playing! As we should all do in any game! Anyway, At the beginning you do not have any idea what to do when?! You just get the ball and try to go forward to the goalpost! Easy right?! Nah! There will be 4 or 5 defenders! And you loose the ball!!

So action $a$ , go forward to the goal post, state $s_{t}$ you have the ball in the middle of the field, resulting state $s_{t+1}$ the other team players took the ball! Reward? you have not scored a goal so it is zero! The value of the state action $Q(s_t, a_t)$ can be updated using the Control equation

$$\begin{equation}
Q(s_t, a_t) \leftarrow Q(s_t, a_t) + \alpha [R_{t} + \gamma Q(s_{t+1}, a_{t+1}) - Q(s_t, a_t)]
\end{equation}$$

For now let's assume we know the state action value of each state of the full soccer field. That is, the value of taking shot at the penalty box $Q(s_{penalty_box}, a_{shot}$ is higher than that of taking shot from midfield obviously $Q(s_{midfield}, a_{shot})$.
## TODO refine it.
