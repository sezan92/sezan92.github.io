# Reinforcement Learning Course 2 Week 2

> Notes for Reinforcement Learning Course 2 Week 2.

## TLDR

- TD Learning!

# write down draft from the video.


## TD Learning method.

- TD learning is a combination of Monte Carlo and Dynamic Programming.
- It uses the current estimate of the value function to update the value function.
- It is a model-free method.
- It is an off-policy method.
- It is a bootstrapping method.
- It is a temporal-difference method.
- It is a prediction method.
- It is a control method.

### Write Intuition from a real life scenario for TD learning method

For monte-carlo policy evaluation, the value function update equation is 
$
\begin{equation}
V(s_t) \leftarrow V(s_t) + \alpha [G_t - V(s_t)]
\end{equation}
$

That means we need to take samples of the full trajectory to measure the value $G_t$ and then update the value function.

Let me give an example from Football game again! Suppose I am trying to train a forward to score a goal no matter from where , no matter in which time As long as he has the ball in the D-box, he must shoot and he must score!! 
# build up the imagination and tie it to the midfielder passing to the forward.

So how does TD learning work in Football?
TODO: think about it and write down the intuition.
