---
layout: page
title: ML on Microcontrollers
description: Real-Time Hand Detection on MAX78000 using Machine Learning
related_posts: false
img: assets/img/MLonMCU/preview_cut.gif
importance: 2
category: ETH Zürich
related_publications: false
---

<div style="text-align: center;margin-bottom: 20px"> <img src="/assets/img/MLonMCU/results_dataset.png" alt="header" style="width: 100%; max-width: 800px;"> </div>

---

Gesture-based interfaces have immense potential in VR/AR devices and household appliances, enabling more intuitive human-device interaction. However, implementing machine learning algorithms on microcontrollers presents unique challenges, particularly in minimizing power consumption, memory usage, and computational costs.

This project aimed to develop an efficient and lightweight hand detection algorithm for use on a resource-constrained microcontroller board (MAX78000FTHR). By introducing quantization, pruning, and architecture optimization techniques, we achieved high accuracy while maintaining minimal memory and energy usage. This project was part of the course Machine Learning for Microcontrollers.

🔸 Authors: Pablo Soler, Miguel Cuba

---

### Implementation
#### Hardware
The project used the MAX78000FTHR evaluation kit, a microcontroller equipped with:
<div style="display: flex; align-items: center; justify-content: center; gap: 20px;">
  <div style="flex: 1; max-width: 50%;">
    <ul>
      <li>ARM Cortex-M4F (100 MHz)</li>
      <li>RISC-V Core (60 MHz)</li>
      <li>CNN Accelerator with 64 processors</li>
      <li>512 KB Flash (432 KB for weights)</li>
      <li>128 KB SRAM</li>
      <li>64x64 px Image Sensor</li>
    </ul>
  </div>

  <div style="flex: 1; max-width: 50%; text-align: center;">
    <img src="/assets/img/MLonMCU/MAX7800.png" alt="MAX78000FTHR Board" style="width: 100%; max-width: 300px;">
    <p style="font-size: 14px; color: gray;">MAX78000FTHR Board</p>
  </div>
</div>


It is basically a microcontroller with a mini GPU. These features made it ideal for on-device deep learning tasks requiring low latency and power consumption.

#### Dataset
<div style="text-align: center;margin-bottom: 20px"> <img src="/assets/img/MLonMCU/Egohands.png" alt="Egohands Dataset" style="width: 100%; max-width: 800px;"> </div>


We utilized the Egohands Dataset, the largest first-person hand dataset, with 15,000 labeled hands across 4,800 frames (720x1280px). The dataset was downscaled to 64x64px for compatibility with the image sensor. For data augmentation the following techniques were used to improve generalization: 

<div style="display: flex; align-items: center; justify-content: center; gap: 20px;">
  <div style="flex: 1; max-width: 50%;">
    <ul>
      <li>Horizontal flips</li>
      <li>Color jitter (Hue, Brightness, Saturation)</li>
      <li>Random scaling</li>
      <li>Random shifts and cropping</li>
    </ul>
  </div>

  <div style="flex: 1; max-width: 50%; text-align: center;">
    <img src="/assets/img/MLonMCU/data_augmentations.png" alt="Data Augmentations" style="width: 100%">
  </div>
</div>
 
#### Model Architecture
The model was inspired by Tinyissimo YOLO, which we adapted slightly to fit into our board's memory.

<div style="text-align: center;"> <img src="/assets/img/MLonMCU/tinyissimo.png" alt="Hand Detection Model" style="width: 90%;margin-bottom: 20px"> </div>

### Post-Processing
The output format of the model is based on the YOLO grid-like cell output. As normal YOLO models, we filter low confidence boxes and then apply Non-Max Suppression (NMS) to overlapping boxes. 

<div style="text-align: center;"> <img src="/assets/img/MLonMCU/post_processing.png" alt="Post Processing" style="width: 90%;margin-bottom: 20px"> </div>

### Quantization and Pruning
To increase the frames per second that the microcontroller can process, we pruned and quantized the network to different degrees to see which yielded the best balance between accuracy and efficiency. For pruning we tested structured L2 (layer specific) pruning and unstructured L1 pruning with pruning ratios from 0.1 to 0.5. We ended up going with a 8 and 4 Bit mixed precision quantization approach and pruning only the final convolutional layer with a pruning ratio of 0.2. 

<div style="text-align: center;"> <img src="/assets/img/MLonMCU/results_MACCs.png" alt="Quantization" style="width: 90%;margin-bottom: 20px"> </div>


### Results
Our final model had an accuracy of 0.88 on the Egohands dataset needing only 412kB and 29M per inference. Image preprocessing took 6ms and running inference took 5.5ms, leading to over 60fps on the microcontroller's camera sensor.

<div style="text-align: center;"> <img src="/assets/img/MLonMCU/results_final.png" alt="Final Results" style="width: 100%;margin-bottom: 20px"> </div>