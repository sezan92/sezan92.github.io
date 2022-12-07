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
This method was first introduced by Ronald J. Williams in the Paper [link](https://link.springer.com/content/pdf/10.1007/BF00992696.pdf). This paper is a lot more mathematical. Luckily we have intuition of it as well!

### Why Reinforce or Policy Gradient methods? 

In the value-based methods the policies are not learned directly. The learning is done according to the value. The value function is continuously updated. *WHAT IF WE* value function is not neede? What if we want to learn the policy directly? Good or bad this is actually the reason. Value-based methods work well, if the policy is discrete. If the policy is discrete we can know which action to take based on value function. But if it is continuous, then that is impossible. One can discretize the actions, but again, how many actions can one take? 

***We don't know which policy is the best!***
Also, there is no way to explore different actions! If the actions is from `-1.0` to `1.0`, how can one explore the action , let's say, `0.666` ? Here comes policy gradient methods!

***Choice of actions***
Value-based methods choose actions randomly. Making action choice erratic, at least in the exploration stage. While Policy gradients do not have this problem. Actions are based on gradients!

## Intuition

I find this [blog](https://towardsdatascience.com/an-intuitive-explanation-of-policy-gradient-part-1-reinforce-aa4392cbfd3c) to have the best intuition on Policy gradient method. Please check it out first before proceeding!

## Code Walkthrough

### Repository

The repository is [here](https://www.github.com/sezan92/rl)

Assuming you have read the intuition blog, please go through the walkthrough.
### How to run?

***Build Image***
```shell
docker compose build
```
***Run the container***
```shell
docker compose up
```

***Training***

```shell
python3 /src/reinforce_discrete.py LunarLander-v2 --train --save_model_path </path/to/save/the/model> --gamma <gamma hyper-parameter> --epoch <num_of_epoch> --plot <to plot or not> --plot_fig_path </path/to/save/the/plot>
```

***Inference***
- To setup for inference, run from outside the docker container
    ```shell
    sudo xhost +SI:localuser:<username>
    ```
- From another terminal run `docker exec -it <container_name>` and inside the container run,
    ```shell
    python3 /src/reinforce_discrete.py LunarLander-v2 --infer --infer_weight /path/to/saved/weight --infer_render <to render the inference or not> --infer_render_fps <fps for render video> --infer_video </path/to/save/inference/rendered/video.>
    ```