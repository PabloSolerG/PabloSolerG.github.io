---
layout: page
title: Adapting to the Unfamiliar
description: Leveraging Latent Space in Reinforcement Learning for Cross-Environment Generalization
related_posts: false
img: assets/img/DLProject/dream_dmlab.gif
importance: 2
category: ETH Zürich
related_publications: false
---

<div style="text-align: center;">
  <img src="/../assets/img/DLProject/lab_logo.png" alt="Institutions" style="width: 100%;">
</div>

---

 <img src="/../assets/img/DLProject/header.gif" alt="Overview" style="width: 100%;">

---

This project is part of the course Deep Learning. Adapting to the Unfamiliar! This project explores how reinforcement learning (RL) agents can leverage pre-trained world models to accelerate adaptation to new environments. By training DreamerV2 on multiple Atari game environments, we built a latent space dynamics model capturing the fundamental features of these environments. Our approach improved learning speed and performance in novel, unseen environments. 
Our findings show that using pre-trained world models offers significant advantages in speed and early performance during RL training. Fine-tuning all components of the model (encoder, decoder, and latent space) is critical for achieving these benefits. However, the limited number of environments and training steps in this project constrained the generalization capabilities of our model.

🔸 Authors: Jona Schulz, Lukas von Briel, Pablo Soler

<p> For more details, check out our report <a href="/../assets/pdf/DLProject.pdf" target="_blank">here</a>.</p>

---

### Introduction 

Reinforcement learning often struggles to adapt quickly to new tasks. Inspired by how humans generalize knowledge, this project explores world models to encode the dynamics of multiple environments into a shared latent space. By fine-tuning these pre-trained models, we enabled faster and more efficient learning of RL agents in new settings. Our main research questions:

- Does a pre-trained world model improve RL training speed in novel environments?
- How does a world model encode shared properties across different environments?

---

### Methods

We conducted experiments in two setups:

- MinAtar Environments: Simplified 10x10 pixel versions of Atari games (e.g., Breakout, Asterix) for computational efficiency.
- Atari Environments: Full-scale Atari games from OpenAI Gym for more complex dynamics.

 

Our project was based on the DreamerV2 architecture, which combines a world model and an actor-critic module. The World model encodes observations into a latent space and predicts future states. This way the model learns the dynamics of the environment to predict the next frame. By doing so it not only gains a deeper understanding of its surroundings, but it also enables itself to train with "dreamed" environments without having to physically interact with the environment. The Actor-Critic model trains the RL agent using dreamed trajectories.
 
<div style="text-align: center;margin-bottom: 20px"> <img src="/assets/img/DLProject/predictions.gif" alt="Dreamed States" style="width: 90%; max-width: 800px;"> </div>
To adapt DreamerV2 for MinAtar, we modified the observation encoder and decoder to handle the smaller 10x10 input size. These can be seen in the following image.

<div style="text-align: center;margin-bottom: 20px"> <img src="/assets/img/DLProject/model_alterations.png" alt="Encoder-Decoder" style="width: 100%; max-width: 800px;"> </div>
   
#### Training Procedure
Our training process involved three stages:

- Dataset Acquisition: Collecting data from multiple environments using DQN-based agents.
- World Model Pre-Training: Training DreamerV2's world model on the collected dataset.
- Fine-Tuning: Adapting the pre-trained model to a novel environment.

--- 

### Results

#### MinAtar Experiments
We trained DreamerV2 on four MinAtar games and fine-tuned it on a novel environment, Space Invaders (all with similar controls). The pre-trained world model accelerated learning, as shown in the loss comparison:

<div style="text-align: center;">
  <img src="/assets/img/DLProject/minAtar_loss.png" alt="minAtar_loss" style="width: 70%; max-width: 800px;">
  <p style="font-size: 14px; color: gray;">World model loss comparison of a DreamerV2 agent with pre-trained world model with and without a fixed RSSM and an agent trained from scratch on MinAtar Space Invaders.</p>
</div>


In full-scale Atari games, our pre-trained model demonstrated faster convergence during the initial training stages on the Breakout environment.

<div style="text-align: center;">
  <img src="/assets/img/DLProject/atari_return.png" alt="minAtar_loss" style="width: 70%; max-width: 800px;">
  <p style="font-size: 14px; color: gray;">Reward per episode comparison of a pre-trained and a non-pretrained DreamerV2 agent during fine-tuning on Breakout.</p>
</div>