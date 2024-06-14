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

*Note*: It seems that the $v_k$ is improving iteratively, need some proving which was not given by the video

Got an intuition!

Let's suppose , you are in a car which moves randomly (hopefully you DO NOT drive such cars!).  The probability distribution and rewards are as follows, 

![image](/images/RL_1_W4_blog/image_6_initial.png)

That means, given the state, the car has 50% chance to move to the upper state or lower state. If it reaches the upper state, then according to the diagram, it will have 90% probability to reach the the state with reward $-1$ . But if it reaches the lower state, it has 90% probability to reach the state with reward $1$. In that case, for the upper state we can calculate the value $v_s$

![image2](/images/RL_1_W4_blog/image_7_first_state.png)

Using the equation above

reward $r=0$, final state value is the reward $-1$ or $1$

$v_s = 0.9 * (0 + (-1)) + 0.1 * (0 + 1)$

or, $v_s = -0.8$

We can calulate same value for the lower state.

![image3](/images/RL_1_W4_blog/image_8_second_state_value.png)

Now, we did not know the initial states value, right? From the same process, we can get the initial state value,

![initial_state_value_image](/images/RL_1_W4_blog/image_9_final_state.png)

It seems $vs=0$ ! It means no value? Yes! Because , by being on the initial state *ONLY* , there IS NO BENEFIT! As the process is completely random!!!

I hope the intution tries to help the readers understand about the bellman equation better!

## Policy Improvement

Now suppose, you had enough with that randomly selecting car! Now you know the value of each state , so you decided to do somethin! What did you do? you went to the next state with the higher value than that of yours! I mean that is the point of value , isn't it?!

![greedy](/images/RL_1_W4_blog/image_10_greedy_policy.png)

In that case , you go to the goal state pretty easily!!! Pretty common sense huh?

So because you just went to the states with higher value than yours, we can say you were "greedy". This kind of thinking, to change the policy $\pi$ into $\pi '$ is called *Greedy Policy* . Because you are greedy after all! The idea of policy improvement theorem is that, 

suppose you have value $q(s, \pi(s))$ for all states $s$ . Then at the next iteration, you choose new policy $\pi '(s)$ , which is to choose action with highest value $q(s, \pi(s))$ , then $\pi '$ must better or at least equal to the $\pi(s)$ ! In mathematical terms

$\begin{equation}
\pi ' (s) = \displaystyle\argmax_{a} \displaystyle\sum_{s'}\displaystyle\sum_r p(s' , r |s, a)[r + \gamma v_{\pi}(s')]
\end{equation}
$

$\begin{equation}
\implies \pi ' >= \pi 
\end{equation}$

## Policy Iteration

From the equation $(3)$, we see that the greedy policy should be better than the policy on which the value function is calculated. Suppose for policy $\pi_1$, we get value $v(\pi_1)$. Based on the $v(\pi_1)$ , we get greedy policy $\pi_2$ . Something like the following, 

$ \pi_1 \rightarrow v(\pi_1) \rightarrow \pi_2 \rightarrow v(\pi_2) \rightarrow ....\pi^*  $

whereas $\pi^*$ is the optimal policy. 

We can see a loop going on here,

![image11](/images/RL_1_W4_blog/image_11_policy_iteration.png)

### What if the initial policy is too bad?

This is personal note, in the more complex problems the initial policy also dictates if we can truly reach the optimal policy or not! These issues will come in the later blogs!

## Reference