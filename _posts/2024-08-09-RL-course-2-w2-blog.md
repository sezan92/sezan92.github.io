# Reinforcement Learning Course 2 Week 4

> Notes for Reinforcement Learning Course 2 Week 2.

## TLDR

- Monte Carlo method

## Monte Carlo method

In the previous course, we learned about the dynamic programming method. In this method the dynamics of the environment is required. What if we do not or cannot have the dynamics of the environment? What if we have large random samples of the environment? In this case comes the Monte Carlo method for the rescue.

### What is Monte Carlo method ? 

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

In real life (IRL), how do we learn everything? Just think about it. For example Football (Americans call it Soccer, but it is the Real football!). How do you learn playing the game of football? Do you try to understand physics of football? For example, if you are taking a penalty kick there are two options for you to learn how to take an optimum penalty kick.

    a) You start learning the physics of penalty kick. That means you have to study the aerodynamics of the ball, the environment that day, the state of the Goalkeeper , and maybe then you can calculate the exact force and direction by which you have to hit the ball! 
    
    b) OR, you start practicing with the ball every day!


I think we all know the answer. WE DO NOT GO FOR (a)! Not only this is close to impossible, even it was possible, it would take ALL THE FUN THERE ARE IN A GAME! Anyway, (a) is Dynamic programming , (b) is Monte carlo learning.


Here it is what happening,

When you are taking thousands of shots you are collecting the "sample states" -> $s_t$

Kicking the ball is action -> $a_t$

You may score a goal or not. They can be reward $r_t$.

The most important part, your brain learns to kick the ball in the right force and direction by collecting the samples!!
