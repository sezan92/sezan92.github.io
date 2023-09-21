# Reinforcement Learning Course 1 Week 2

> Notes for Reinforcement Learning Course 1 Week 2.

## TLDR

- Introduction to MDPs

### Prerequisites

To start reading this blog, please read the first blog of the series, [Reinforcement learning specialization, Course 1, week 1](https://sezan92.github.io/2023/08/14/RL-course1-w1-blog.html).

## K-armed bandit into Markov Decision Process

### Problems of K-armed bandit world.

- In the K-armed bandit problem , all actions are the same. For example in a medical trial, we choose medicine from one of the three. We do not choose like, medicine in one time, and the exercise in the other situation, for example. In the real world, we need to choose different actions for different situations.

- The another issue with the K-armed bandit problem does not consider the long term consequences. For example, a patient may heal right away for a medicine A compared to that of medicine B, but it might have some other life time side effects. The K-armed bandit problem do not consider that.

### Then how does the real world more like?

In the real world, we interact with the environment, we get some feedback (it might be positive/ negative or neutral). Then based on the new state we take new actions!. Some thing like this,

![MDP](/images/RL_1_W2_blog/image_1_MDP_interaction.png)

[upto 5:07]