# Reinforcement Learning Course 2 Week 4

> Notes for Reinforcement Learning Course 2 Week 2.

## TLDR

- Monte Carlo method

## Monte Carlo method

In the previous course, we learned about the dynamic programming method. This method requires the dynamics of the environment. What if we do not or cannot have the dynamics of the environment? What if we have large random samples of the environment? In this case, the Monte Carlo method comes to the rescue.

### What is the Monte Carlo method? 

Simple. For a certain state, $s$ , we take random samples of the returns $(r^s_0, r^s_1, r^s_2, r^s_3...r^s_n)$. We will average 
$
\begin{equation}
v^s_{\pi} = \frac{\sum^n_{i=0} r_i}{n}
\end{equation}
$

Simple, right?

### Real life intuition!

![penalty](/images/RL_2_W2_blog/image_1_pexels_penalty.jpg)

The above photo is taken from pexels[dot]com.

In real life (IRL), how do we learn everything? Just think about it. For example Football (Americans call it Soccer, but it is Real football!). How do you learn to play the game of football? Do you try to understand the physics of football? For example, if you are taking a penalty kick there are two options for you to learn how to take an optimum penalty kick.

 a) You start learning the physics of penalty kick. That means you have to study the aerodynamics of the ball, the environment that day, and the state of the Goalkeeper, and maybe then you can calculate the exact force and direction by which you have to hit the ball! 
    
 b) OR, you start practicing with the ball every day!


I think we all know the answer. WE DO NOT GO FOR (a)! Not only is this close to impossible, but even if it was possible, it would take ALL THE FUN THERE ARE IN A GAME! Anyway, (a) is Dynamic programming, and (b) is Monte Carlo learning. Actually, very close to it! But you get the big idea, right?


Here is what is happening,

When you are taking thousands of shots you are collecting the "sample states" -> $s_t$

Kicking the ball is action -> $a_t$

You may score a goal or not. They can be rewarded $r_t$.

The most important part, your brain learns to kick the ball in the right force and direction by collecting the samples!!


## Exploration

For the Monte Carlo method, as the agent does not have full knowledge of the dynamics of the environment and it is basically a sampling-based method, it is necessary to give the agent as much as information possible of different states.

### Let's get back to the penalty kick situation

Suppose you are a goalkeeper, You want to train yourself as much as possible. You are never able to know the physics of all football matches. Even if you do, by the time you can calculate the position of the penalty taker, it's already the goal! So what should you do? Like I said, practice!!! The more different types of goal-stopping practice you can do, the more probability of stopping the goals in the real matches!! These different scenarios of shooting practice are samples. The more diverse the samples are the better the chances of training yourself for the games or in other words "generalizing" the agent! This is exactly what exploration does!

![GK](/images/RL_2_W2_blog/image_2_pexels_GK.jpg)

## Exploration in the environments!

So! We have got an idea about the need for exploration! How to do it in an RL environment? 
There are two popular ways to do so!

### Exploring start policy

In this case, the agent will start at a random initial state every time it starts playing the game.
This way the agent should start learning to generalize. For example, if you play chess, you are always starting from the same initial state.
How about we randomize your initialize your state every time?! Sometimes you might be just before an obvious checkmate, sometimes you might be check-mated!
Either way, you will learn to train yourself in all sorts of initial positions! But it has a problem. It only deals with random initial states!
It does not directly affect the behavior of the agent as per the policy! For example, back to chess, if you always follow a certain policy for chess, 
no matter what initial state, your policy might not be affected.

### Epsilon-soft policy 

In this case, the agent will choose random action based on a threshold $\epsilon$, which is why this policy is named $\epsilon$ -soft policy. The biggest advantage is that the agent will learn about the value of a state and action at any state at any time. This policy has more chance of training the agent with all of the available state spaces. 

Going back to our Football (aka Soccer) intuition, it is more like trying different types of shots at different places of the D-box! Sometimes you try the working action or / shots, sometimes you experiment in practice!

