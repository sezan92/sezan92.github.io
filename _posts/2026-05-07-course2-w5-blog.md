# Reinforcement Learning course 2 week 5

## TLDR

- Model , What is it?

## Model and why do we need it?

Before starting about model, let's think what kind of learning algorithms we have encountered till now.

In dynamic programming we have to know the model of the environment. That is the transition probabilities and the reward function. 

In the monte carlo method we do not need to know the model, but we need to wait till the end of the episode to update the value function. That is kind of knowing  the model because you are getting all the information at the end of the episode.

In TD learning method, we do not need to know the model, neither we need to wait till the end of the episode. We can update the value function at every time step and at random time step.

All of them have some of their own advantages and disadvantages.

How about we combine the advantages of the model-based and mondel-free methods?

## What is a model?

Let's define a model first.

![Model](/images/RL_2_W5_blog/image_1_model.png)


TODO

2026/05/10
- [] complete writeup on this video https://www.coursera.org/learn/sample-based-learning-methods/home/module/4

