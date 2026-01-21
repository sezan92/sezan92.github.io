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

Suppose in the game of the football, you have multiple choices to make. You can either go for long pass, or go for short pass or go for shoot to the Goal post! Which action to take? What about , each time you take the action based on the maximum value? How can we know the value? (That is the point of Q learning!) For now, lets assume we know what is the value of state action pair in the game.

If you are at the front of a D-box, what will you do? Shoot or Pass? 

Lets assume you have the following option


$Q(s_t=Dbox, a=shoot) = 0.1 $
$Q(s_t=Dbox, a=pass) = 0.5 $

and the player who is in front of the Goal post

$Q(s_t=goal_post, a=shoot) = 0.9$
$Q(s_t=goal_post, a=pass) = 0.6$ 

The best set of actions (or policy) is to take the action with the maximum value at each state. So at D-box you will "pass", and expect the player in front of the goalpost to "shoot". How can you know that the player will "shoot" when you "pass" ? You cannot be sure about it! But you can "expect" him to "shoot" based on your experience. So you should train yourself to "pass" in that position "expecting" the player will "shoot". Not that he will "pass" again! This is the intuition behind Q learning.

### Q learning update equation
The Q learning update equation is as follows:


$$Q(s, a) \leftarrow Q(s, a) + \alpha [R + \gamma \underbrace{\max_{a'} Q(s', a')}_{\text{Best possible action}} - Q(s, a)]$$

That is we are updating the action-value function of the current state-action pair expecting that the next action taken will be the one with the maximum value. This differs from SARSA where we take the next action based on the current policy. 

$$Q(s, a) \leftarrow Q(s, a) + \alpha [R + \gamma \underbrace{Q(s', a')}_{\text{Actual next action}} - Q(s, a)]$$

![Intuition](/images/RL_2_W4_blog/shot_pass_diagram_gemini.png)

### How is Q-learning off-policy?

Summary, because it chooses action based on behaviour policy,

### TODO 
Confirm why Q-learning is off-policy and why it does not need importance sampling.
https://www.coursera.org/learn/sample-based-learning-methods/lecture/1OikH/how-is-q-learning-off-policy
start from 3:06