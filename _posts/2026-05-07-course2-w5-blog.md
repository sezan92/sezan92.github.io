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

Model is just a way of representing the environment. That is , for each state, and action to the environment, we should get the same reward and reward. Let's think about a video game of football match. Here are the players, the goal posts, the referees. The state and action - in this case- the ball  and player position, and the kick/ pass/ block , the reward will be similar , i.e. scording goals, blocking goals etc! But this is obvious from the example, you will not get the exact reward of scording goals!  in the same way, the model is representation of the environment. Not a "Replacement" of the environment. The purpose of this model is to get the simulated experience ( similar to the football game)  which will help your policy in the end!

![Model_objective](/images/RL_2_W5_blog/image_2_model_objective.png)

## Types of Models

There are two types of models

- Sample models.
- Distribution models.

### Sample Models

What is a sample model? Let's put it this way, Suppose you have flipped multiple coins OR flipped same coin several times. Now you write down the heads and tails of those flipps. This is exactly SAMPLE MODEL! ***How about we write down the probabilities of each coins heads or tails?***

### Distribution model

Here comes the distribution model! If we know the probability distributions (or better, the functions) of the coin flips either one after the other or parallel flips we can get the distributions of each head or tail right?! This is Distribution model! 

![Types_of_models](/images/RL_2_W5_blog/image_3_model_types.png)


### Sample Model vs Distribution Model

As we go forward ,we can realize the environemts to deal with, will be way complex to let distribution models deal with them! Think about [Atari Games](https://en.wikipedia.org/wiki/Atari_Games). How many states action and rewards are there! But if we want to use RL in real world - we need the sample based models!!

Think about this! Notice how many pausible outcomes for 12 dices ? But if we take the sample model approach, we can get the distribution (in other words, the outcomes of rolling 12 dices maybe 10000 times ), we still get some kind of working data with less computation and hassle.

![sample_vs_dist_dice_12_role](/images/RL_2_W5_blog/image_4_12_dice_distribution.png)

The distribution model, which is getting the exact probability is useful when number of parameters are low (compared to the power of computation obviously!)


## 2026/07/02

- [ ] Write about the video (https://www.coursera.org/learn/sample-based-learning-methods/lecture/mdEPi/random-tabular-q-planning)


