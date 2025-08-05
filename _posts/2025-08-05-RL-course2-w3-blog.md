# Reinforcement Learning Course 2 Week 2

> Notes for Reinforcement Learning Course 2 Week 2.

## TLDR

- Intuition to Temporal Difference (TD) learning method


## What is TD Learning?

TD learning method can be said a combination of Monte Carlo and Dynamic Programming. Let's look at the update equation for TD learning:
$$\begin{equation}
V(s_t) \leftarrow V(s_t) + \alpha [R_{t+1} + \gamma V(s_{t+1}) - V(s_t)]
\end{equation}$$

That means the value of a state is determined by the immediate reward received and the estimated value of the next state.


### Intuition for TD learning method vs Monte Carlo

Let's build an intuition from the most beautiful game in the world: football (or soccer, if you are in the USA).

Suppose you are a coach training a midfielder. The midfielder's goal in this case is to pass the ball to the striker in the best position. As we know there are multiple forwards on the field. How do we train the player the best place to pass to? How do we train him which player to pass to ? There are two choices

(a): Let the players play till an episode (i.e. either they score a goal , or the play is out of the field). There is a video of that full game. The midfielder watches the video of the full game and tries to learn the best passes in each situation. This is dynamic programming! The learning is offline (outside of the game), full sweep on the episode, the player knows the dynamics of the environment, and the player can learn from the full episode.

(b): What if the midfielder does not need to watch the full game? He updates his knowledge after each pass. For example, if the midfielder passes the ball to a forward and  the forward scores, the midfielder can immediately learn that the pass was good. This is Monte Carlo learning! The learning is online (during the game), the player does not know the dynamics of the environment, and the player can learn from partial episodes. The player also can take advantage of videos of several games or episode and "average" the results to learn the best passes. This is also a type of Monte Carlo learning.

(c) If the midfielder passes the ball to a forward and the forward is very close to the goal post , whether he scores or not, the midfielder can immediately learn what was the best move in that position. This is temporal difference learning! The learning is online (during the game), the player does not know the dynamics of the environment, and the player can learn from partial episodes. The difference with the monte carlo method is that in this case, *the forward DOES NOT need to score*. The midfielder can learn from the immediate reward of the pass and the estimated value of the next state (i.e. the position of the forward)! In the case of the Monte Carlo method, the midfielder needs to wait until the forward scores or the play is out of the field to learn from the pass. In this case, the midfielder can learn from every pass he makes, even if the forward does not score.


## what is the difference between TD learning and Monte Carlo?

From the above example we might think that what is the actual difference between TD learning and Monte Carlo? If you read carefully, in the monte-carlo method, the player needs to wait until the forward scores or the play is out of the field to learn from the pass. In the case of TD learning, the midfielder can learn from every pass he makes, even if the forward does not score.

### Difference in equations of the RL methods we have learned so far

(Note that I have used GitHub Copilot to generate the table below and repurposed it)

| Method                  | Update Equation                                                                 | Key Difference                                                                                     |
|-------------------------|---------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|
| Dynamic Programming     | $$V(s_t) \leftarrow \max_a \sum_{s'} P(s'\|s_t, a) [R(s_t, a, s') + \gamma V(s')]$$  | Requires a model of the environment (transition probabilities $P$), updates value function using full knowledge of dynamics. |
| Monte Carlo             | $$V(s_t) \leftarrow V(s_t) + \alpha [G_t - V(s_t)]$$                            | Requires full trajectory to compute $G_t$, updates value function after the episode ends.         |
| Temporal Difference (TD)| $$V(s_t) \leftarrow V(s_t) + \alpha [R_{t+1} + \gamma V(s_{t+1}) - V(s_t)]$$    | Updates value function after each step using immediate reward $R_{t+1}$ and estimated next state. |

## Conclusion
And that's it! This was comparatively short blog post! But it took me a while to figure out a good intuition!!

### References

[1] The details of the equations are taken from the Reinforcement learning specialization Coursera.

[2] I used GitHub Copilot to refine the writeup , not gonna lie. Specially the table showing the difference!
