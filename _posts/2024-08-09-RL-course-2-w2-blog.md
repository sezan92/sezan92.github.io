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

[first video done , next video.]