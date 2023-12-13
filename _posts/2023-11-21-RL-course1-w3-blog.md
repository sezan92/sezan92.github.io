# Reinforcement Learning Course 1 Week 3

> Notes for Reinforcement Learning Course 1 Week 3.

## TLDR


### Prerequisites

Previous blog, [Reinforcement learning specialization, Course 1, week 2](https://sezan92.github.io/2023/11/17/RL-course1-w2-blog.html).


## Policies!

So what is a policy? Simply put whatever action is taken by the agent in a certain state. For example, if the day (state) is Monday , I will have to go to work. If the day is Saturday, I will sleep. We can formulate,

$\pi (S_{day}=Monday) = {Work} $\
$\pi (S_{day}=Saturday) = {Sleep} $

This can be shown as 

![image](/images/RL_1_W3_blog/image_1_Deterministic_policy.png)

For our example, we can say,

| State ($s$)    | Action ($a = \pi (s)$) |
|----------|--------|
| Monday   | Work   |
| Saturday | Sleep  |

But this does not take into account the fact of randomness!
[start about stochastic policy]