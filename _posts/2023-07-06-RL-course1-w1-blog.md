# Reinforcement Learning Course 1 Week 1

> Notes for Reinforcement Learning Course 1 Week 1.

## TLDR

- This note blog shows my notes on the Reinforcement learning (RL) course 1 week 1 video

### Background

I am an RL enthusiast for a long time. The concept of training an agent based solely on the points fascinated me from the beginning! I kept exploring the RL methods and architectures by myself. For example, the blogs of [The Game is ON!](https://sezan92.github.io/2020/03/22/RL.html) were based on my learning journey. It is still ongoing by the way!

*But something was missing*. I had some issues with the basic terminologies in the literature. Some of the important algorithms seemed very difficult to me. So I decided to step back and try to hone my basics! I tried to read The famous book by "Sutton and Barto", but the book being a big Textbook, it also seemed very hard!

*Somehow I got to know about the Reinforcement learning Specialization at the University of Alberta* and everything changed! In this blog series, I want to share my thoughts/ideas/notes about what I learned from the specialization. I will try to explain in simple language. The specialization is really good. The first blog of this (hopefully) continuing blog series is about Course 1, Week 1 of the specialization. If there is any concern/question/feedback, please do not hesitate to email me at sezan92[at]gmail[dot]com.

## Week 1

- In the first week, the instructors introduced k-arm bandit problem. It is a simple game with multiple buttons. Each button will give you a reward. you need to choose the best button by pressing each button and maximizing the reward. The best similar thing is gambling!! But in our life, we may take decisions by trial and error.

    The game in the course looks like following, ![k-armed-bandit](/images/RL_1_W1_blog/k-arm-bandits.png)

- One of the examples of K-armed bandits can be clinical trials
![k_armed_bandit_clinical_trial_pic_1](https://user-images.githubusercontent.com/11025093/220614930-30ff94e2-c943-4619-a25b-eebf9d7d279e.png)

    The big idea is that suppose a doctor has 3 patients. he doesn't know the medicine. so he trials 3 medicines for 3 patients. if he sees improvement in health in a patient for a certain medicine, he prescribes the medicine.

- Let's define action and reward. The action is the prescription of a certain medicine and the value is the effects of the medicine. Progress can be seen as positive reward, while the regress can be seen as negative rewards. The combination of the both is Action value.
![k_armed_bandit_action_values_equation](https://user-images.githubusercontent.com/11025093/220615216-d4df1955-58ba-4787-9e3c-7825c7dcbb88.png)

- assuming better health means better blood pressure, the instructor gives intuition by following the illustration

![k_armed_bandit_trial_picture_equation](https://user-images.githubusercontent.com/11025093/220615637-9f057782-791e-44e8-9c52-af9b115d4399.png)

- here each action $a$ , (i.e. medicine)  has action value $q(a)$ i.e. the blood pressure.

- Our real-life examples
![k_armed_bandit_other_examples](https://user-images.githubusercontent.com/11025093/220616144-23b61473-6cc1-43a6-8481-a61b2a6cc29a.png)

My note:

- I think the clinical trial example is not good. Because they are not random trials. After much research the doctors may get some candidates then they make a trial
- also all 3 patients must have similar conditions.
- the instructor could have gone with a simpler example, like food for a certain location, etc
- Also I find the intuition of the equation not so good.

### Action value

Action value is the value of an action. (I know it is not genius to figure it out). But the question is how can we know the value of an action?

from the video, how can we know the value of the action of prescribing one medicine? One of the ways is the sample averaging method.

![Screenshot from 2023-03-06 13-19-15](https://user-images.githubusercontent.com/11025093/223018545-601f20f3-fbc0-4b70-97f9-435955f93102.png)

#### intuition

for example, if some people had a headache and the doctor doesn't know the medicines  $A$ , $B$, $C$ which are the best. he tries all of them. Suppose for medicine $A$ the headache is cured 90 out of 100 times. for medicine $B$ it is 50 out of 100 times. then the action value for $A$ is $90/100$ => $0.9$ . now what about the other 10? They might have other factors, which leads us to the notion of $state$ value. more on that later. [Video minute 1:57]

### Greedy action

Suppose we get action values for all three actions after many trials. When we choose the action with the best action value, this is called greedy action selection. This process of choosing greedy action is known as exploitation.

![exploitation](https://user-images.githubusercontent.com/11025093/223735899-4f43cd27-b08f-4acf-ba69-bca4888aecb2.png)

On the other hand, we also can explore other actions at the expense of getting the best reward. this will let us know more about the actions. this is known, as one might have guessed exploration.

now the problem is, we cannot do both - at least with one model. This is a fundamental problem in the Reinforcement learning problem. known as the `Exploitation Exploration` dilemma.

we can rewrite the sample-average method for learning action values as follows,

![Screenshot from 2023-03-14 13-14-42](https://user-images.githubusercontent.com/11025093/224891672-873ee138-6926-4469-a73b-e7c5627ec263.png)

in other words,

![Screenshot from 2023-03-14 13-15-45](https://user-images.githubusercontent.com/11025093/224891760-ae8e47c8-85ef-44ae-9960-e796ef95a54b.png)

in the equation , $\frac{1}{n}$  is known for a limited number of steps. But what if we do not know how many steps will be taken?  For example, we will never know how many moves a game of chess can be won. In those cases, we can write $\alpha$ instead! It is a hyperparameter known as step size. it will dictate how quickly our agent can update the action value.

![Screenshot from 2023-03-14 13-16-25](https://user-images.githubusercontent.com/11025093/224891839-cee771ec-8256-49bf-84b1-bef8f4a0f8ff.png)

[upto 2:43]

### Non-stationary bandit problem

let's look at the equation again,
![Screenshot from 2023-03-27 14-56-30](https://user-images.githubusercontent.com/11025093/227853320-0cfacce5-6359-40e9-871a-bb6e43838779.png)

![Screenshot from 2023-03-27 15-01-49](https://user-images.githubusercontent.com/11025093/227853867-c625f498-0ec8-4921-90f9-533afbe3aaf4.png)

from the above two equations, we see that $Q_{n+1}$ depends on the most recent rewards more than the past rewards. making it possible to update over time

what does the (re-write of) the equation tells us?

it says that the Action values always give more focus on the recent rewards than the previous ones. **Why is it important?** It helps the model be updated. There might be some actions that might be time-dependent. e.g. some medicines might work in one season, but not in others, and vice versa. This equation helps us keep track of recent rewards and let the model learn from the most recent experiences.

### Exploration Exploitation trade-off

**Video1**

**What is the trade-off**

Exploration means the agent tries each action and sees what the action leads to.

Exploitation, on the other hand, means that the agent takes the action with the maximum reward, from his prior knowledge, which is always limited.

Now, if we let the agent always explore, the agent will not ever act according to the previous knowledge of best actions; resulting in never maximizing the total rewards. If we always let it exploit, we might miss the information about all plausible state-action pairs! This is known as the **exploration-exploitation dilemma**.

**Solution?**

One of the most popular solutions is Epsilon's greedy actions. For certain times let the agent explore, for other times let it exploit! **Then how to know when to do which one?** In this case, what we do, is set a threshold named $\epsilon$. Then generate a random floating point number (0.0-1.0). If the random number is greater than $\epsilon$, explore, otherwise exploit! Naturally, if we want to explore more, we will set the $\epsilon$ lower, otherwise bigger. In the training time, we in general want our agent to explore initially more, and exploit at the end more. So in the beginning the $\epsilon$ is higher, and in the end, it is lower! But there are other methods, this is good as a getting-started solution!

### For example

suppose for the medical trial of 3 medicines, the optimum values are
$q_1 = 0.25, q_2=0.75, q_3=0.5$

but initially, we do not know the optimum value. how about we start with high initial values,

$Q_1 = Q_2 = Q_3 = 2$

now let's remember the incremental update equation,

$Q_{n+1}  $&larr;$  Q_n + \alpha(R_n - Q_n)$

Let's assume positive feedback has point $1$ and negative has $0$.  After running some trials, we might get closer to the optimum values,

![Screenshot from 2023-04-25 14-08-25](https://user-images.githubusercontent.com/11025093/234179596-b7276248-f531-439f-bd8e-fd25fb9ade24.png)

### Comparison

![compare_performance](https://user-images.githubusercontent.com/11025093/235430182-8dd3a61c-33c7-4861-b2ff-73e879193e02.png)

from the image above it seems that the optimistic initial value setting will help us more compared to the epsilon greedy!

### Demerits

- We do not know what is the best optimistic initial value.
- it is temporary, i.e. after the first initial trials the explorations will get stopped

### My opinion

- We can use both epsilon greedy and optimistic initial values.

### Uppder confidence Action selection

The Epsilon greedy action selection works the following way

![Screenshot from 2023-06-05 12-22-11](https://github.com/sezan92/sezan92.github.io/assets/11025093/c3f8ea4b-ab22-458f-a6f7-e066aaa368c3)

Here, for exploration, we are choosing random actions uniformly. The problem is, we are giving the same weight to all random actions. How about while choosing the random action, we can choose the less explored action? In other words, we prioritize the actions with less uncertainty (due to that action being less explored).

For example, the uncertainty can be shown as follows,

![Screenshot from 2023-06-14 17-16-38](https://github.com/sezan92/sezan92.github.io/assets/11025093/0145c603-fb53-4e36-b7bc-10ca2d84af97)

in the process of UCB, we guess that the unknown action is good. i.e. high Q value. and hence called the upper confidence action value.

The equation for UCB combines exploration and exploitation like the following,

![Screenshot from 2023-07-03 15-29-56](https://github.com/sezan92/sezan92.github.io/assets/11025093/3b444071-158c-4399-8d9b-db8bfee511f6)

$t$ is the timesteps and $N_t(a)$ means the number of times an action $a$ is being taken. it means that the more we explore an action $a$, the lesser it will have an effect. like the following example,

![Screenshot from 2023-07-03 15-33-09](https://github.com/sezan92/sezan92.github.io/assets/11025093/ca1ab6ed-a86c-49ee-acaa-fece838f2bea)

where $c$ is the hyperparameter. on the 10-arm bandit test bed, the performance is as follows,

![Screenshot from 2023-07-03 15-35-20](https://github.com/sezan92/sezan92.github.io/assets/11025093/f60bed21-ac04-446c-819c-49877baec62d)
