---
layout: page
title: HoloSpot
description: Intuitive Object Manipulation via Mixed Reality Drag-and-Drop
related_posts: false
img: assets/img/holospot/icon.png
importance: 1
category: ETH Zürich
related_publications: false
---

<div style="text-align: center;">
  <img src="/../assets/img/holospot/lab_logo.png" alt="Institutions" style="width: 100%;">
</div>

---

We are thrilled to announce that our latest research paper, “HoloSpot: Intuitive Object Manipulation via Mixed Reality Drag-and-Drop”, is now available for you to read! This work dives into Human-robot interaction through mixed reality technologies enabling novel, intuitive interfaces to control robots in remote operations. In this paper, we present an interface system projecting a 3D representation of a scanned room as a scaled-down 'dollhouse' hologram, allowing users to select and manipulate objects using a straightforward drag-and-drop interface. We then translate these drag-and-drop user commands into real-time robot actions based on the recent spot-compose framework. Our interface made object placement tasks more intuitive and three times more accurate than using mouse and keyboard. I see promising opportunities for this system to handle remote logistics operations, especially in inaccessible environments. Thanks to the whole team and to all the people who participated in the user study!


🔸 **Authors**: Pablo Soler Garcia, Petar Lukovic, Lucie Reynaud, Andrea Sgobbi, Federica Bruni, Martin Brun, Marc Zünd, Riccardo Bollati, Marc Pollefeys, Hermann Blum and Zuria Bauer Hartwig


For more information check out our paper or our project page!

📃 [Read the Paper](https://arxiv.org/abs/2410.11110)  
🏠 [Visit the Project Webpage](https://holospot.github.io/)  


<div style="text-align: center;">
  <iframe width="560" height="315" src="https://www.youtube.com/embed/PN45oQVyvGA" frameborder="0" allowfullscreen></iframe>
</div>

---

<div style="text-align: center;">
  <img src="/../assets/img/holospot/holospot.png" alt="HoloSpot" style="width: 80%;">
</div>

---

### Abstract

Human-robot interaction through mixed reality (MR) technologies enables novel, intuitive interfaces to control robots in remote operations. Such interfaces facilitate operations in hazardous environments, where human presence is risky, yet human oversight remains crucial. Potential environments include disaster response scenarios and areas with high radiation or toxic chemicals.

In this paper we present an interface system projecting a 3D representation of a scanned room as a scaled-down 'dollhouse' hologram, allowing users to select and manipulate objects using a straightforward drag-and-drop interface. We then translate these drag-and-drop user commands into real-time robot actions based on the recent spot-compose framework.

The Unity-based application provides an interactive tutorial and a user-friendly experience, ensuring ease of use. Through comprehensive end-to-end testing, we validate the system's capability in executing pick-and-place tasks and a complementary user study affirms the interface's intuitive controls. Our findings highlight the advantages of this interface in improving user experience and operational efficiency. This work lays the groundwork for a robust framework that advances the potential for seamless human-robot collaboration in diverse applications.

---

### Setup

#### Scene Acquisition
To get the semantic scene understanding needed for the pick and place tasks, the scene is scanned by the robot and with an iPad's LiDAR. Both scans are then aligned and the higher resolution iPad scan is used to segment the scene with OpenMask3D. Using the segmentation labels, movable objects are separated from the static background scene and loaded on the HoloLens2. 

<div style="text-align: center;margin-bottom: 20px">
    <img src="/../assets/img/holospot/offline_pipeline.png" alt="Offline Pipeline" style="width: 90%;">
</div>

#### AR Interface
A PC in the room acts as the server of the communication between the Spot and the Hololens. The augmented reality app allows the users to move objects in the scene using a simple drag and drop interface. When a user moves an object, the Hololens sends the information of the selected object and the drop location. The server calculates the optimal grasping pose using AnyGrasp and plans the robot's paths. After every action the robot returns to the start position and aligns its local map using a qr code.


<div style="text-align: center;">
  <img src="/../assets/img/holospot/online_pipeline.png" alt="Online Pipeline" style=" width: 90%;">
</div>

---

### Results
We tested our mixed reality interface extensively, and the results are exciting! A user study with 24 participants revealed that our drag-and-drop Hololens interface outperformed a traditional 2D mouse-and-keyboard setup, with placement accuracy more than three times higher. Users found the interface intuitive and enjoyable, completing tasks with minimal frustration and rating their experience highly. Across 240 trials with a variety of objects, the interface demonstrated a success rate of 72% without introducing significant failure modes.

<div style="text-align: center;margin-bottom: 20px">
  <img src="/../assets/img/holospot/User_study.png" alt="Online Pipeline" style=" width: 50%;">
</div>

<div style="text-align: center;">
  <img src="/../assets/img/holospot/success.png" alt="Online Pipeline" style=" width: 90%;">
</div>


---
### The Holospot Team at CVG
<div style="display: flex; justify-content: center; align-items: center; gap: 20px;">
  <img src="/../assets/img/holospot/holospot_portrait.jpg" alt="Me and Spot" style="width: 60%;">
  <img src="/../assets/img/holospot/team_photo.gif" alt="Team Photo" style="width: 40%;">
</div>
