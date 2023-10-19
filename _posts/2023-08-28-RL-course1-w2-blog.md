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
- Your commute to work, coming back home, working at the office all are action $a$.
- For each action, we have state transition probability $p_a$.

Let me first show you a scarry final diagram, ![scary](/images/RL_1_W2_blog/image_9_MDP_intuition.PNG)

### How did we get here?

From the beginning, your energy level is either high or low. Which are the states.

![first](/images/RL_1_W2_blog/image_3_MDP_intuition.PNG)

In the morning you (hopefully) wake up and commute to work.
![second](/images/RL_1_W2_blog/image_4_MDP_intuition.PNG)

The world is not deterministic my friend! "Probably" you will go to work, or probably no!. So let us give this going to work a probability, $p_a= \alpha$ . So, if you somehow stay at home, that would have probability , $(1-\alpha)$!
![third](/images/RL_1_W2_blog/image_5_MDP_intuition.PNG).

If you stay at home, you will get some negative feedbacks from the office!  Let us say, you will get, reward $r=-1$. If you go to office, you will get reward $r=+1$.

![fourth](/images/RL_1_W2_blog/image_6_MDP_intuition.PNG)

Again, you may work at the office, or waste your time! Let us say you work at the office with the probability $p_a=\beta$. You will get the reward of $10$. But because of that , your energy will decrease!

![fifth](/images/RL_1_W2_blog/image_7_MDP_intuition.PNG).

After you finish your work, you get back home. But you may not! If you get back home with the probability of $\gamma$, you will get the negative reward (because your company likes "Hard working" people who overtime!) of $r=-1$.

![sixth](/images/RL_1_W2_blog/image_8_MDP_intuition.PNG)

But if you stay late (with the probability of $1-\gamma$), and work overtime? You get reward, $r=+5$.

![seventh](/images/RL_1_W2_blog/image_9_MDP_intuition.PNG)


### What we see from the above plots?

The power of Markov Decision Process lies in that , we can convert any situations into a pair of $state, action, probability, reward$!! This helps us  formalize any problem anywhere!


## Goal of the Reinforcement Learning

In one sentance, the goal of the reinforcement learning is to maximize the future rewards.
What do we mean by that ?

Well, in the above example of MDP, if we always prioritize the immediate reward, what will happen? If we are asleep to keep our energy high, one day we will run out of money and we will starve! If we keep working to get rewards from the companies, we will lose our personal lives , families,and energy! So what do we need? Maximizing the future rewards! We need both work and personal lives to have the best of all worlds! This is always the goal of any RL agent!!

## The reward Hypothesis

This video is very important about the philosophy behind Reinforcement learning. The video is craftfully presented by Michael Littman. The basic idea of Reinforcement learning is that we do not teach the agent the exact actions. Rather we feed them the rewards for a certain action at a certain state. From these informations the agents should learn the correct actions to maximize the total or cumulative rewards.


Now this idea has an assumption. That is, the environment is giving us back the correct rewards. But in real life do we get the correct rewards? time: 4:14

## Reference

- All of the screenshots are from Course 1, Week 1 of Reinforcement Learning Specialization.