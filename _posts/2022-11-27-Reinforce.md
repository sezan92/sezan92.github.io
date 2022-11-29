# The Game, is On! REINFORCE!
> Enter the world of Policy Gradient methods!

### Previous blogs

- [The Prequel, Q Learning](https://sezan92.github.io/2020/03/18/QLearning.html)
- [Deep Q Network](https://sezan92.github.io/2020/03/18/DQN.html)
- [Double Deep Q Network](https://sezan92.github.io/2020/03/18/DDQN.html)
- [Duelling Double Deep Q Network!](https://sezan92.github.io/2020/03/18/D3QN.html)

## Reinforce

In this blog i am writing about new type of Reinforcement learning (will be referred as RL) method. REINFORCE method.

### History
[Include the history of Reinforce]

### Why Reinforce or Policy Gradient methods? 

In the value gradient method (check the name if it is correct) we do not learn the policy directly. We learn the policy according to the value. *WHAT IF WE* don't want to learn the value, we want to learn the policy directly. Good or bad this is actually the reason. Value-gradient method works okay if the policy is discrete. If the policy is discrete we can know which action to take based on value function. But if it is continuous, then there is a big problem.

***We don't know which policy is the best!***
Also, there is no way to explore different actions!

