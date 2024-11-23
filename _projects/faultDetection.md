---
layout: page
title: AI-powered Fault Detection 
description: Detecting Damage (ITSCs) in the Electric Drivetrain of Autonomous Robo-taxis
related_posts: false
img: assets/img/publication_preview/ITSC_wavelet.png
importance: 1
category: RWTH Aachen
related_publications: false
---


<div style="text-align: center;">
  <img src="/../assets/img/faultDetection/project_institutions.png" alt="Institutions" style="width: 80%;">
</div>

---

## Classification of ITSCs in Field-Oriented Controlled Electrical Machines using Convolutional Neural Networks

---


Excited to share our project on fault detection in Permanent Magnet Synchronous Machines (PMSMs) using convolutional neural networks (CNNs)! The project was part of AnRox, a development of an optimized drive system for automated electric driving. The methods, simulation tools and solutions developed in the project focus on the use case of a robot taxi. However, they are generally transferable to all electrically driven vehicles.
This work demonstrates how advanced modeling and machine learning techniques can detect inter-turn short circuits (ITSCs) with remarkable accuracy, providing significant insights into fault diagnostics for electric drives. With binary classification achieving 98% accuracy and multi-class classification at 90.2%, our approach shows promising potential for reliable real-world applications. 

Authors:

🔸 **Authors**: Duc Pham, Pablo Soler Garcia, Xinyi Yu, Rik W. De Doncker

For more information check out our paper!
📃 [Read the Paper](https://ieeexplore.ieee.org/document/10238782)  

---
### Abstract
The electric drivetrain of an autonomous driving vehicle is not only supposed to be efficient, but there are also high requirements for reliability and fault-tolerant capability. Inter-turn short circuits (ITSCs) can occur frequently and have a severe impact on the drivetrain. In this work, a machine learning method based on convolutional neural networks (CNNs) detects the fault in a binary classification problem and identifies eleven different classes in a multi-class classification. The faulty machine’s characteristics are calculated by finite-element (FE) simulations. Next, the machine inductances are used in a circuit simulation to consider a machine operation with fieldoriented control (FOC). With the current waveforms for different operating points and combinations of faults, a data processing workflow is presented. A continuous wavelet transform (CWT) is
performed on all three-phase currents. To enhance the harmonic content, the cone of influence (COI) is removed from the data and a column-wise normalization is applied. This allows an operating point independent classification of 11 fault classes. The binary classification has an accuracy of 98%. While the multi-class
problem with 11 classes has an overall accuracy of 90.2%, the reduction to 10 classes increases the accuracy to 97%.

---
### Introduction 
Permanent Magnet Synchronous Machines (PMSMs) are widely used in electric drivetrains due to their efficiency and compact size. However, they are susceptible to Inter-Turn Short Circuits (ITSCs), which occur when insulation fails, causing electrical contact between windings within the same phase. ITSCs can lead to overheating, demagnetization of permanent magnets, and even total machine failure. Early detection is crucial to prevent costly damage and ensure the safe operation of vehicles.

Our project tackled ITSC detection using CNNs trained on simulated data, providing a reliable way to identify faults during normal operation without the need for additional sensors.

---

#### Modeling ITSC Faults
We used finite-element (FE) simulations in PLECS to model the electrical and magnetic behavior of PMSMs under various fault conditions, including varying fault resistances and numbers of shorted turns. In MATLAB Simulink we designed the circuit simulations which incorporated these parameters into a Field-Oriented Control (FOC) scheme to emulate real-world operational scenarios. 

<div style="text-align: center;">
  <img src="/assets/img/faultDetection/faultModel.png" alt="faultModel" style="width: 90%; max-width: 800px;">
  <p style="font-size: 14px; color: gray;">Left: Theoretical model of an ITSC in phase U of a three-phase machine. <br>Right: Simulation setup to calculate the inductance if the PMSM with ITSCs.</p>
</div>

#### Wavelet Transform
To extract features from the three phase current waveforms, we applied a Continuous Wavelet Transform (CWT). This method captured the time-frequency representation of signals, highlighting harmonics caused by faults. Post-processing included normalization and the removal of edge artifacts (cone of influence) for clearer fault signatures.

<div style="text-align: center;">
  <img src="/assets/img/faultDetection/wavelet.png" alt="wavelet" style="width: 90%; max-width: 800px;">
  <p style="font-size: 14px; color: gray;">Data processing of three-phase current waveforms for generation of dataset. First column represents the current signals. Second column is the wavlet transforms of the signal. Third column displays both the removal of the cone of influence and the subsequent normalization. Last column shows the different transforms in different color channels representing one phase of the machine. </p>
</div>

#### Convolutional Neural Networks
The transformed data was fed into a ResNet18-based CNN. Pre-trained weights were fine-tuned on our dataset, leveraging advanced architectures to classify faults into binary (healthy/faulty) and multi-class (11 fault types) categories. 

---

### Results

The binary classifier distinguished between healthy and faulty states with 98% accuracy. The CNN's high true positive rate (95.9%) and area under the curve (AUC = 0.998) demonstrate its robustness in detecting faults. When estimating between the 11 fault severity classes, the CNN achieved an overall accuracy of 90.2%. While some classes with similar fault characteristics showed reduced accuracy, merging or refining class definitions improved performance to 97% for 10 classes.

Future work will focus on improving the resolution of similar fault classes and validating results with real-world measurement data to enhance reliability and applicability.


<div style="text-align: center;">
  <img src="/assets/img/faultDetection/results.png" alt="wavelet" style="width: 90%; max-width: 800px;">
  <p style="font-size: 14px; color: gray;">Left: Confusion matrix for fault detection with ResNet18
 <br>Right: Confusion matrix for multi-class classification with 11 classes based on ResNet18</p>
</div>
