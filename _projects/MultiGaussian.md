---
layout: page
title: Multi-Domain GS
description: Semantic Information Embedding in Gaussian Splats for Reinforcement Learning Training Speed-Up 
related_posts: false
img: assets/img/MultiGS/GS_preview.gif
importance: 1
category: ETH Zürich
related_publications: false
---

<div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden;">
    <iframe width="820" height="460" src="https://www.youtube.com/embed/mRDarTzl9aI?si=iFpn_CBUj9qql_SZ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

--- 

I am aiming to submit this project for a publication in December of 2024. More information will follow then!

---

### Abstract
Reinforcement Learning (RL) has emerged as a powerful paradigm for developing autonomous navigation systems, being applied extensively within autonomous navigation. However, these systems are often limited to geometric representations due to the slow rendering times of realistic training environments. Consequently, navigation algorithms typically lack semantic perception of their surroundings, hindering their ability to make robust decisions. 
Simultaneously, recent advancements in computer graphics have introduced Gaussian splatting, a technique capable of rendering high-quality, photorealistic scenes at unprecedented speeds. This thesis proposes a novel multi-domain Gaussian splatting implementation that integrates both visual and semantic information, creating a versatile and efficient framework for RL training in navigation tasks. Our method automatically converts simulated environments into semantically rich Gaussian splats, embedding crucial navigational data such as surface risk assessment and traversability directly into the representation. By achieving a 300-fold increase in rendering speed while enhancing semantic quality, this approach offers a promising solution to accelerate the training of RL agents in complex, realistic environments.

---