# Deep Learning In Robotics

## TLDR
- AI has a lot of potentials in Robotics 
- But robotics being robotics. It has a lot of difficulty yet. 
- Many engineers don’t like deep learning as it is black box - or personal issues 
- Applying Deep learning In robotics is still an active research area. 
- And as a result, it is risky as a job 
- But good and long term research field. 


![Sofia](/images/dl_in_robotics/2_thumb_sofia.png)

From Terminators to the Endgame, we all imagine AI to be synonymous with Robots. Every advertisement for Artificial Intelligence comes with a poster of a robot behaving like and/or surpassing human beings. Now, we might have a lot of software outperforming human beings in many tasks, but we don’t have - at least on the massive production scale- autonomous robots outperforming humans in day-to-day tasks. The most common robots in the production with consumer demands are the vacuum cleaner robots. The worth mentioning Deep Learning (DL) model they are using is Object detection - and probably in some cases, image segmentation. The other algorithms of the mobile robots like SLAM, navigation, behavior planning, sensor fusion, etc, are still using the non-DL methods. The DL-based approach in those tasks is still under active research. This makes the case for Deep Learning in Robotics research quite an interesting subject with great potential though. More on this later. 
 
## Why so slow progress 

![ros_turtle](/images/dl_in_robotics/1_ros_turtle.jpg)
[Credit](https://ja.m.wikipedia.org/wiki/%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB:ROS_C_logo.jpg)
 
 
Simply put, Robotics being Robotics. We have to understand the field of robotics. It is beautiful. It is a combination of Electrical Engineering, Mechanical Engineering, Computer Science, and in many cases Biomechanics. ( because in most cases we are imitating God's creation for building robots). But here is the problem. Different fields progress at different speeds. The fastest innovation right now is happening in the field of Computer science, in Software Engineering to be precise. Due to machines becoming more and more powerful, newer and newer algorithms are coming up virtually every other day. But the problem is, that the other fields in Robotics are not progressing so fast. Mechanical Engineering which is responsible for manufacturing actual robot hardware is the slowest of them. Innovation in mechanical engineering is very hard. For example, the efficiency of an internal combustion engine is at best [40%](https://www.greencarreports.com/news/1091436_toyota-gasoline-engine-achieves-thermal-efficiency-of-38-percent#:~:text=Most%20internal%20combustion%20engines%20are,around%2020%20percent%20thermal%20efficiency). It was invented in the 1850s. Think about it! After 170 years, the efficiency is still at 35 % !!! No doubt why the car companies are moving toward Electric vehicles! Due to the slow progress of other fields like Mechanical Engineering no matter how good a State-of-the-art (SOTA) a DL model is, most likely it might not be deployed in the robots. Because before deploying the architecture, you need to have compatible hardware in the robot. And the hardware team in your company might release the required update after 2-3 years - even if they want to release -. But in the next 2-3 years there will be another SOTA Deep learning architecture, or maybe a new field altogether! This makes the progress of AI Engineering in Robotics harder. 
 
## Many Engineers don’t like Deep learning 
 
That’s unfortunately true. Many engineers do not like deep learning. I cannot judge their intentions. But I can guess there are two reasons. First, deep learning is still a black box model. Although there are fields of research being conducted to have explainable AI, trying to explain different AI models, still it is not fully well understood. Second, many Robotics Engineers / Roboticists being traditional engineers, do not have enough confidence in this black box model. But hey! It is not new, is it?  
 
When Einstein first published papers on relativity, the physics world was mad. He was challenging all traditional notions of Newtonian physics without having any experimental data. Heck! Einstein himself was opposed to the probabilistic nature of Quantum Physics! And look where these two ground-breaking theories of Physics have taken the world into! Some other physicists didn't take Einstein's theories seriously because of personal reasons, political reasons, etc. Are there some engineers who do not like Deep learning due to similar reasons? Maybe. Cannot say for sure. Anyway, that is not the subject of my discussion. 
 
## Deep Learning in Robotics is still an active research area 
 
There is a big review paper on this topic describing the challenges of Deep Learning in Robotics! I intend to write blogs on it, but for now, I can refer to the actual [paper](https://arxiv.org/pdf/1804.06557.pdf). In summary, Robotics is not just one field. It has many subfields. Behavior planning, Control, the control there is manipulation, locomotive control, kinematics, kinetics, etc. Using Deep learning in those areas is still under research. We might see many research papers in those fields. But to get a robust enough deployable algorithm, the new model should beat all of the existing algorithms in the same task, the results must be reproduced by multiple neutral parties, and assuming the hardware is capable enough to deploy, the model must be optimized for the hardware! See the problem? This makes it really hard to deploy deep learning models. Because, one of the reasons deep learning-based architectures have improved NOW- instead of the 90s when many algorithms were invented - is the powerful hardware to deploy them. This leads to the following point 
 
## Risky as a Job 
 
Because of all the problems I mentioned in the last section, Deep learning Engineering in a Robotics environment is a risky job. Especially if your main income depends on it. Just think about it, your product manager comes in, and wants to get Mask-R-CNN level accuracy within a fraction of seconds. You say NO. He asks to segment a tiny part of an image with 720p resolution, you say no. He asks to map the building without any manual controller. If you still say no! Then heck! Why are you hired ?! But is it your fault? It makes it really risky to be a software engineer in deep learning for Robotics products. It was always risky in the real world. 
  
## But good as a research topic 
 
Because there are so many question marks in the application of deep learning in Robotics, it also makes an active and exciting research area. So anyone who loves the field of Robotics, and wants to do research, here you go. It will be long-term. As slowly but surely, many countries are Roboticizng everything. From baristas to car drivers to posts man, there is a chance of deploying Robots in everything. Which makes the research of Deep learning in Robotics a long-term prospect. 
 
## What should we do? 
 
I love robotics. Every time any part of a real-world robot works the level of joy it brings to my mind, is unimaginable! But should the enthusiast of AI and Robotics stop pursuing this field? !! Obviously NO! We must continue working on the field we love, but we also should the challenges that lie ahead. Otherwise, I might be hoping to create Jarvis out of the backyard in a week but we may not be able to code for properly talking in the first place! So the best practice should be, that we should have a long-term plan, have patience, look at the immediate challenges, keep working, and progress little by little. More on this later. 
 
 
***Please let me know if there is anything I missed in this blog and share your thoughts.***
