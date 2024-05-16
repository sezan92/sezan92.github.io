# Reinforcement Learning Course 1 Week 4

> Notes for Reinforcement Learning Course 1 Week 4.

## TLDR

- Evaluate the policy: How good the policy is?
- Update the policy: Let's improve our actions!
- Dynamic Programming in the context of Reinforcement learning

### Prerequisites

Previous blog , [Reinforcement Learning Course 1, Week 3](https://sezan92.github.io/2023/11/21/RL-course1-w3-blog.html)

## Policy Evaluation

From the previous blog, we came to know about value of a state. We can denote this as $v(s)$. Now the value of a state will depend on two things. One, how easily we can get the maximum reward from the state. Two, is what action we will take, i.e. what policy we will follow on that state! We can denote it as $v_{\pi}(s)$. Which means, the "value of a state while following the policy $\pi$".

![](/images/RL_1_W4_blog/image_1_Policy_Evaluation.png)

From the first blog, we can recall
$
\begin{equation}
v_{\pi} (s) = \displaystyle\sum_a \pi(a|s) \displaystyle\sum_{s'}\displaystyle\sum_r p(s', r|s, a)[r + \gamma v_{\pi} (s')]
\end{equation}
$

For each state we will get different equation right? From the equations we should be able to solve and get the optimum value $v_{\pi}$! But the problem is that in practice, the states are in many cases continuous! That means infinite states and hence, infinite equations are possible! Not to mention for different policies $\pi$, the equations will change! So what do we do? We go for iterative solution! We use Dynamic Programming algorithms (yeah, that dynamic programming which is used in problem solving!)

![](/images/RL_1_W4_blog/image_2_LinearSolver_DP.png) [upto 2:21]



## Control

Control in this domain means improving the policy. How do we know which policy is better policy? Simple! The policy for which, the value of the same states are greater! If the $v_{\pi2}$ for all states are greater than $v_{\pi1}$ , then we can tell $\pi_1$ is better than $\pi_2$ ! What if the policys values are not greater but equal to the all of previous policies? We can assume that we have converged to the optimal policy!

![](/images/RL_1_W4_blog/image_3_Control_improving_policy.png)

*Note* there is a mention of "strictly" better policy, I am not sure what does that mean. I will check in the book if I can get better idea!

### How will we use Dynamic Programming? 

Well, to be honest, the it will become more clear as the course and hence this blog progresses! But in short, the dynamic programming will be used to approximate the optimal value and the optimal model of the environment to get the optimal policy!. More on that later!

## Iterative Policy Evaluation

What is the Iterative policy evaluation? Simple. We have the bellman equation at (1) right ? 
Suppose we have initial random policy value $v_k$. What if we tug the value into the (1) ?
$
\begin{equation}
v_{k+1} (s) = \displaystyle\sum_a \pi(a|s) \displaystyle\sum_{s'}\displaystyle\sum_r p(s', r|s, a)[r + \gamma v_k (s')]
\end{equation}
$

What does it mean? It means, using the bellman equation we got better at estimating the optmum value function!! If we do this over all states certain "iterations" we should get the optimum value function!! When do we know the value function has reached the optimal value? When the value functions are not changing! Because the $v_{\pi}$ has only one unique solution to the bellman equation.

![](/images/RL_1_W4_blog/image_5_vk_vpi.png)

### Intuition

![intuition](/images/RL_1_W4_blog/image_6_policy_evaluation_intuition.png)

*Note*: It seems that the $v_k$ is improving iteratively, need some proving which was not given by the video

Got an intuition, 



## Reference