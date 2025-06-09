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

Let me give an example from Football game again! Suppose I am trying to train a striker (number 9) to score a goal no matter from where , no matter which time as long as he has the ball in the D-box, he must shoot and score!! The best way to teach him is to give him the ball in different parts of the D-box and practice! (Sampling!). What about the midfielder? His only job is to give pass to the forward so the forward can score! How can we teach him which position is the best? One way is to play a full game until the forward scores a goal!!

Or! 
We can let him know which pass is the best! We do not need to wait till the forward scores a goal! His job is only to go to best position for the next time step!! 

The first scenario can be said as Dynamic programming. You wait until each full game (or Episode). The other can be said TD-error learning!
# build up the imagination and tie it to the midfielder passing to the forward.
# monte-carlo? how to differentiate with monte-carlo? 

TODO: think about difference with monte-carlo: done

Update i have got intution idea from Gemini
TODO: update the intuitive idea from Gemini. 
TODO: unsure share the prompt?
