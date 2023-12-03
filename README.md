# **NeuN3t20: Convolutional Spiking Neural Network for Vehicle Collision Avoidance**

## **Overview**

NeuN3t20 is an initiative culminating in the construction of a Convolutional Spiking Neural Network based on the ResNet20 architecture. The primary focus of this project is real-time video-based vehicle collision prediction. 


## **Key Features**
>**Architecture:** Constructed on the ResNet20 framework, NeuN3t20 leverages a convolutional spiking neural network for enhanced performance in vehicle collision prediction.
>
>**Real-Time Prediction:** The CSNN is optimized for real-time video analysis, allowing for swift and accurate vehicle collision avoidance predictions.
>
>**Adversarial Robustness:** NeuN3t20 showcases superior adversarial robustness, outperforming current state-of-the-art approaches in handling challenging scenarios.
>
>**Energy Efficiency:** The project places a strong emphasis on energy efficiency, ensuring that the neural network operates optimally in resource-constrained environments.


## **Dataset**
>This work utilizes a simulation-based dataset, created using a driving simulation known as Carla. This dataset consists of sequences each of which represents various scenarios in driving, where some represent a collision course while others represent safe driving.
>
>This dataset satisfies the requirements of mimicking real-world driving conditions under different circumstances and providing First-Person-View (FPV), which are some of the crucial criteria when addressing autonomous driving.
>
>The data has both safe and risky classes with 7000 sequences each. Each sequence consists of 8 images before the collision. The resolution of each frame in every sequence is 144 x 216 for training and inference.


# **Training Method**

This work employed BNTT-Backpropagation, that is, Surrogate-Gradient Backpropagation in combination with Batch Normalization Through Time (BNTT) to train from scratch. [BNTT-Backpropagation](https://www.frontiersin.org/articles/10.3389/fnins.2021.773954/full)


<img width="1287" alt="Screenshot 2023-12-03 at 4 04 20 PM" src="https://github.com/MPEROR-9102/NeuN3t20/assets/97546729/00f338d2-f82e-4680-a2a6-9df7b595c5e6">
