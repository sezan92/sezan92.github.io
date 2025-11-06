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


But here is an issue! What if the action taken at the next step $s_{t+1}$ does not give us the best value $Q(s_{t+1})$? Or in other words the policy is not the most optimum? For example, your policy is to give long passes always. But in the front of the goal post, will you follow your policy and shoot for long pass to another team mate? Or will you go for the goal? You should choose the action with the maximum reward right?


## Q learning!

### Intuition

Suppose in the game of the football, you have multiple choices to make. You can either go for long pass, or go for short pass or go for shoot to the Goal post! Which action to take? What about , each time you take the action based on the maximum value? How can we know the value? (That is the point of Q learning!) But suppose you know what is the value of state action pair!
### TODO : continue


### TODO 
write Q learning intuition
add a picture to show problem with SARSA.
watched  https://www.coursera.org/learn/sample-based-learning-methods/lecture/m6AWq/what-is-q-learning