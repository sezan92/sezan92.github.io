# Reinforcement Learning Course 2 Week 2

> Notes for Reinforcement Learning Course 2 Week 2.

## TLDR

- TD Learning!


## What is TD Learning?

TD learning method can be said a combination of Monte Carlo and Dynamic Programming. Let's look at the update equation for TD learning:
$$\begin{equation}
V(s_t) \leftarrow V(s_t) + \alpha [R_{t+1} + \gamma V(s_{t+1}) - V(s_t)]
\end{equation}$$

That means the value of a state is determined by the immediate reward received and the estimated value of the next state.

In the case of monte-carlo policy evaluation, the value function update equation is
$$\begin{equation}
V(s_t) \leftarrow V(s_t) + \alpha [G_t - V(s_t)]
\end{equation}$$
That means we need to take samples of the full trajectory to measure the value $G_t$ and then update the value function.


### Intuition for TD learning method vs Monte Carlo

Let's build an intuition from the most beautiful game in the world: football (or soccer, if you are in the USA).

Suppose you are a coach training a midfielder. The midfielder's goal in this case is to pass the ball to the striker in the best position. As we know there are multiple forwards on the field. How do we train the player the best place to pass to? How do we train him which player to pass to ? There are two choices

(a): Let the players play till an episode (i.e. either they score a goal , or the play is out of the field). There is a video of that full game. The midfielder watches the video of the full game and tries to learn the best passes in each situation. This is dynamic programming! The learning is offline (outside of the game), full sweep on the episode, the player knows the dynamics of the environment, and the player can learn from the full episode.
(b): What if the midfielder does not need to watch the full game? He updates his knowledge after each pass. For example, if the midfielder passes the ball to a forward and the forward and the forward scores. Then the midfielder can immediately learn that the pass was good. This is Monte Carlo learning! The learning is online (during the game), the player does not know the dynamics of the environment, and the player can learn from partial episodes. The player also can take advantage of videos of several games or episode and "average" the results to learn the best passes. This is what we call Monte Carlo learning.

(c) If the midfielder passes the ball to a forward and the forward is very close to the goal post , whether he scores or not, the midfielder can immediately learn what was the best move in that position. This is temporal difference learning! The learning is online (during the game), the player does not know the dynamics of the environment, and the player can learn from partial episodes.

### TODO: rewrite the above section so it looks more like my own words also add that i took  help from Gemini to build the intuition with the prompt.

#### build up the imagination and tie it to the midfielder passing to the forward

#### monte-carlo? how to differentiate with monte-carlo

TODO: think about difference with monte-carlo: done

Update i have got intution idea from Gemini
TODO: update the intuitive idea from Gemini. 
TODO: unsure share the prompt?
