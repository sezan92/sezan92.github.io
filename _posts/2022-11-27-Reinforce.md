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
[Include a meme ] 
[Include the history of Reinforce]

### Why Reinforce or Policy Gradient methods? 

In the value-based methods the policies are not learned directly. The learning is done according to the value. The value function is continuously updated. *WHAT IF WE* value function is not neede? What if we want to learn the policy directly? Good or bad this is actually the reason. Value-based methods work well, if the policy is discrete. If the policy is discrete we can know which action to take based on value function. But if it is continuous, then that is impossible. One can discretize the actions, but again, how many actions can one take? 

***We don't know which policy is the best!***
Also, there is no way to explore different actions! If the actions is from `-1.0` to `1.0`, how can one explore the action , let's say, `0.666` ? Here comes policy gradient methods!

***Choice of actions***
Value-based methods choose actions randomly. Making action choice erratic, at least in the exploration stage. While Policy gradients do not have this problem. Actions are based on gradients!

## Intuition

I find this [blog](https://towardsdatascience.com/an-intuitive-explanation-of-policy-gradient-part-1-reinforce-aa4392cbfd3c) to have the best intuition on Policy gradient method. Please check it out first before proceeding!

## Code Walkthrough

Assuming you have read the intuition blog, please go through the walkthrough.
### How to run?

# (TODO: sezan92)
- Add a github repo link
- add command to run the pipeline.
