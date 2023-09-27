# Reinforcement Learning Course 1 Week 2

> Notes for Reinforcement Learning Course 1 Week 2.

## TLDR

- Introduction to MDP
- Dynamics of MDP

### Prerequisites

To start reading this blog, please read the first blog of the series, [Reinforcement learning specialization, Course 1, week 1](https://sezan92.github.io/2023/08/14/RL-course1-w1-blog.html).

## K-armed bandit into Markov Decision Process

### Problems of K-armed bandit world.

- In the K-armed bandit problem, all actions are the same. For example in a medical trial, we choose medicine from one of the three. We do not choose, medicine at one time, and exercise in the other situation, for example. In the real world, we need to choose different actions for different situations.

- Another issue with the K-armed bandit problem does not consider the long-term consequences. For example, a patient may heal right away for medicine A compared to that of medicine B, but it might have some other lifetime side effects. The K-armed bandit problem does not consider that.

### Then what does the real world more like?

In the real world, we interact with the environment, we get some feedback (it might be positive/ negative or neutral). Then based on the new state we take new actions! Something like this,

![MDP](/images/RL_1_W2_blog/image_1_MDP_interaction.png)

where,

$S_t$ : State at time $t$.
$S_{t+1}$: State after action $A_t$ at time $t+1$

This cycle of $(state, action, new state, reward)$ is known as *Markov Decision Process* (MDP in short).

### Representation of MDP

The mathematical representation of the MDP is as follows

![MDP_Dynamics](/images/RL_1_W2_blog/image_2_MDP_Dynamics.png)

In the above haunted (!) mathematical picture the terms mean as follows,

$p(s', r|s, a)$: It means the probability of a new state and reward given the current state $s$, and action $a$.

We assume the environment is stochastic, and hence it is shown as a probability function. Because of that the summation of probabilities, across all rewards and states is $1$.

## Real Life Intuition

We can express any real life events or cyles of events as MDP. This is the flexibility power of MDP framework. For example, 5 days-a-week work life. Let's assume the following,

- Your energy level is the state $s$
- Your commute to and from work , and work at the office is the action $a$.

[explain video 2, make a hand-drawn diagram]



## Reference

- All of the screenshots are from Course 1, Week 1 of Reinforcement Learning Specialization.