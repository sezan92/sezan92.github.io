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

Let's use a Football (Soccer) game to build intuition.

#### Scenario: A Midfielder Learning to Make Effective Passes

Imagine a midfielder whose goal is to learn the best positions on the field from which to make passes, and what kind of passes lead to better scoring opportunities.

-   **Monte Carlo (MC) Approach for the Midfielder:**
    The midfielder is at position $s_t$ and makes a pass. To evaluate this action using MC, they would have to wait until the entire sequence of play resulting from that pass concludes. This could involve several other players touching the ball, movements across the field, and eventually, either a goal is scored, the ball goes out of play, or possession is lost. Only at the end of this entire "episode" does the midfielder get the full return $G_t$. They then update their value $V(s_t)$ based on this complete outcome. For example, if a goal was scored, the pass was good; if possession was lost quickly, it was bad. The learning happens only after the final result of that specific play is known.

-   **Temporal Difference (TD) Learning Approach for the Midfielder:**
    Now, consider the TD learning approach. The midfielder is at $s_t$ and makes a pass, and the ball moves to a teammate at a new position $s_{t+1}$ (e.g., a forward is now in a good spot).
    Instead of waiting for the entire play to finish, the midfielder can immediately update their estimate of $V(s_t)$. They do this by considering:
    1.  Any immediate reward $R_{t+1}$ received (usually 0 in this phase, unless the pass itself is directly rewarded).
    2.  Their *current estimate* of the value of the new state, $V(s_{t+1})$ (e.g., "how good is it for our forward to have the ball here?").
    The midfielder updates $V(s_t)$ based on $R_{t+1} + \\gamma V(s_{t+1})$. They are essentially saying, "The value of being in my current position and making that pass is now updated by the immediate outcome plus my best guess of how good the *next* situation is."
    They don't need to wait to see if a goal is *actually* scored from $s_{t+1}$. They learn from the *change in their estimated value* of the game state from one step to the next. If the pass puts the forward in a position that the midfielder *believes* is very valuable (high $V(s_{t+1})$), then the value of the passing action from $s_t$ is reinforced positively, even before the forward shoots. This is "bootstrapping" – using an existing estimate ($V(s_{t+1})$) to update another estimate ($V(s_t)$).

**Key Difference Illustrated:**

-   **MC:** "I made a pass. Let's see how this whole play turns out. Okay, we scored! That pass from that position must have been good." (Waits for the end).
-   **TD:** "I made a pass. The forward now has the ball in a really dangerous area. That's a good sign! My pass to get them there was likely a good move." (Updates immediately based on the estimated value of the next state).

This immediate feedback and ability to learn from incomplete episodes makes TD learning often more efficient than MC methods, especially in environments with long episodes.

The first scenario can be said as Dynamic programming. You wait until each full game (or Episode). The other can be said TD-error learning!

#### build up the imagination and tie it to the midfielder passing to the forward

#### monte-carlo? how to differentiate with monte-carlo

TODO: think about difference with monte-carlo: done

Update i have got intution idea from Gemini
TODO: update the intuitive idea from Gemini. 
TODO: unsure share the prompt?
