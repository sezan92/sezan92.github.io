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

Something like in Football. If you are learning in the game, you need to think about the whole trajectory of decisions before scoring a goal. That is time-consuming when you are learning! Think about it. If you have to coach a player, do you let him play the whole game of 90 minutes and then tell him what he did wrong? Or will you tell him what he did wrong in the exact moment? At that very "state" of the game?

So how does TD learning work in Football?
TODO: think about it and write down the intuition.
