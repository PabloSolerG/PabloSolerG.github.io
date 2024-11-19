---
layout: page
title: Walk the Dog
description: Person Following via Transformer-based Feature Matching
related_posts: false
img: assets/img/walkTheDog/navigation_map.gif
importance: 1
category: ETH Zürich
related_publications: false
---


<div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden;">
    <iframe width="820" height="400" src="https://www.youtube.com/embed/o3NmWS8RWTQ?si=zCl_xkICO6kXpygB" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>


---

I'm excited to share this project for the class Robot Learning by Prof. Dr. Fisher Yu: an autonomous person-following system for the Unitree Go1 quadruped robot! This system combines novel object detection, person re-identification, and navigation technologies to enable the robot to reliably follow a target in dynamic environments. Equipped with a custom-designed module featuring a Jetson Orin Nano, ZED2i stereo camera, and LiDAR, the Unitree Go1 can autonomously track individuals, avoid obstacles, and plan efficient paths.
  
This project highlights the growing potential of quadruped robots in applications like assistive technology, security, and human-robot interaction. Our experiments demonstrated reliable person-following in real-world settings. 

<p>If you're interested in the full details of the implentation, have a look at our full report <a href="/../assets/pdf/walkTheDog.pdf" target="_blank">here</a>.</p>


🔸 Authors: Pablo Soler, Dario Dittli, Sam Sulaimanov

 <img src="/../assets/img/walkTheDog/Total_pipeline.svg" alt="Overview" style="width: 90%;">

---

### Abstract 

This project presents the development of an autonomous person-following system for a quadruped robot, specifically the Unitree Go1. The project addresses the growing need for advanced robotic assistance in various fields, including guide dogs for the visually impaired, security applications, and enhanced human-robot interaction.
Our approach integrates cutting-edge object detection, person re-identification, and navigation technologies to create a robust tracking and navigation system. We equipped the Unitree Go1 with a custom-designed backpack containing a Jetson Orin Nano computer, ZED2i stereo camera, and LiDAR sensor to enable accurate perception and decision-making.

---

### Hardware
We designed a custom backpack for the Unitree Go1 robot to enable autonomous person-following. The backpack houses an NVIDIA Jetson Orin Nano, a ZED 2i stereo camera, and an RPLIDAR C1 2D LiDAR. This setup allows for high-performance object detection, depth perception, and obstacle detection. The entire system is mounted on a laser-cut, lightweight frame and communicates with the robot via Ethernet, enabling seamless integration with the ROS 2 ecosystem.

<div style="display: flex; justify-content: center; align-items: center; gap: 20px;">
  <img src="/../assets/img/walkTheDog/bag_design.png" alt="Bag Design" style="width: 30%;">
  <img src="/../assets/img/walkTheDog/CAD_Unitree_GO1_cropped.PNG" alt="CAD Design" style="width: 40%;">
  <img src="/../assets/img/walkTheDog/Robot.png" alt="CAD Design" style="width: 30%;">
</div>

---

### Vision

Our vision pipeline combines YOLOv5 for person detection, a Vision Transformer (SOLIDER) for person re-identification and a Kalman filter-based tracking system for maintaining the target. We achieve person re-id by using the SOLIDER framework, which generates feature representations balancing semantic and appearance information, tailored for tasks like identifying individuals. Using a Vision Transformer-based architecture inspired by TransReID, we extract features from image patches, mitigating biases caused by variations in camera angles or viewpoints. To ensure efficient target identification, a reference dataset is generated for each person, and matches are confirmed using feature similarity. The pipeline optimizes computational load while maintaining accurate and stable tracking.

<div style="display: flex; justify-content: center; align-items: center; gap: 20px;">
  <img src="/../assets/img/walkTheDog/Vision Pipeline.svg" alt="Vision" style="width: 90%;">
</div>

### Navigation 

We leveraged ROS 2's Nav2 framework to create a 2D costmap from the LiDAR data and implemented Dijkstra’s algorithm for precise path planning. To enhance performance, the costmap is simplified into a lower-resolution, binary representation. The robot dynamically plans paths to the target's 3D coordinates while avoiding obstacles, recalculating the path every second if the target remains visible. 

<div style="display: flex; justify-content: center; align-items: center; gap: 20px;margin-bottom: 20px">
  <img src="/../assets/img/walkTheDog/Navigation_Pipeline.svg" alt="Navigation" style="width: 60%;">
</div>

### More Results


<div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden;">
    <iframe width="840" height="472" src="https://www.youtube.com/embed/OpZmHFAkHi0?si=SzREpd_NxlHjWTJo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

---

#### Thanks to the Computer Vision Lab for letting us play with their robot!

<div style="display: flex; justify-content: center; align-items: center; gap: 20px;margin-bottom: 20px">
  <img src="/../assets/img/walkTheDog/robot_cart.jpg" alt="Robot-Cart" style="width: 80%;">
</div>
