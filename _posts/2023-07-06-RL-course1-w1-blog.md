# Reinforcement Learning Course 1 Week 1
> Notes for Reinforcement Learning Course 1 Week 1.

## TLDR

- This note blog shows my notes on the Reinforcement learning course 1 Week 1 videos


### Story

I am and was an RL enthusiast for a long time. The concept of training an agent based on rewards or punishments only fascinated me from the beginning. So I kept exploring RL methods, and architectures by myself for a bit of time. For example, the blogs of [The Game is ON!](https://sezan92.github.io/2020/03/22/RL.html) were the result of my learning RL.

But there was something missing. I had some issues with basic terminologies in the Reinforcement learning literature. Also some basic algorithms seemed very difficult for me. So I had to step back . I tried to read The famous book by Sutton and Barto. But there were something missing.

*Then I got to know about Reinforcement learning Specialization by University of Alberta*

###  Week 1

- Introduced k-arm bandit problem. It is a simple game with multiple buttons. (screenshot). Each button will give you reward. you need to choose the best button by pressing each button and maximizing the reward. Best similar thing is gambing!! But in our life we may take decisions by trial and error. 


## Update 2023/02/22

- Here the instructor gave example of clinical trial as k-armed bandit
![k_armed_bandit_clinical_trial_pic_1](https://user-images.githubusercontent.com/11025093/220614930-30ff94e2-c943-4619-a25b-eebf9d7d279e.png)

The big idea is that suppose a doctor has 3 patients. he doesnt know the medicine. so he trials 3 medicines for 3 patients. if he sees improvement in health in a patient for a certain medicine , he prescribes with the medicine.

- then the instructor defines the action and the reward combined as action value. here the action is the prescription and value is the better health.
![k_armed_bandit_action_values_equation](https://user-images.githubusercontent.com/11025093/220615216-d4df1955-58ba-4787-9e3c-7825c7dcbb88.png)

- assuming the better health means better blood pressure, the instructor gives intuiton by following illustration
 
![k_armed_bandit_trial_picture_equation](https://user-images.githubusercontent.com/11025093/220615637-9f057782-791e-44e8-9c52-af9b115d4399.png)

- here each action $a$ , (i.e. medicine)  has action value $q(a)$ i.e. the blood pressure.

- Our real life examples
![k_armed_bandit_other_examples](https://user-images.githubusercontent.com/11025093/220616144-23b61473-6cc1-43a6-8481-a61b2a6cc29a.png)


My note:

- I think clinical trial example is not good. Because they are not random trials. After many researches the doctors may get some candidates then they make a trial
- also all 3 patients must have similar condition.
- the instructor could have gone with a simpler example, like food for a certain location etc
- ALso i find the intuition of the equation not so good.

