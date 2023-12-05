# **NeuN3t20: Convolutional Spiking Neural Network for Vehicle Collision Avoidance**

**Overview -** NeuN3t20 is an initiative culminating in the construction of a Convolutional Spiking Neural Network based on the ResNet20 architecture. The primary focus of this project is real-time video-based vehicle collision prediction. 




## **Key Features**
>**Architecture:** Constructed on the ResNet20 framework, NeuN3t20 leverages a convolutional spiking neural network for enhanced performance in vehicle collision prediction.
>
>**Real-Time Prediction:** The CSNN is optimized for real-time video analysis, allowing for swift and accurate vehicle collision avoidance predictions.
>
>**Adversarial Robustness:** NeuN3t20 showcases superior adversarial robustness, outperforming current state-of-the-art approaches in handling challenging scenarios.
>
>**Energy Efficiency:** The project places a strong emphasis on energy efficiency, ensuring that the neural network operates optimally in resource-constrained environments.




## **Dataset**

This work utilizes a simulation-based dataset, created using a driving simulation known as Carla. This dataset consists of sequences each of which represents various scenarios in driving, where some represent a collision course while others represent safe driving. This dataset satisfies the requirements of mimicking real-world driving conditions under different circumstances and providing First-Person-View (FPV), which are some of the crucial criteria when addressing autonomous driving. The data has both safe and risky classes with 7000 sequences each. Each sequence consists of 8 images before the collision. The resolution of each frame in every sequence is 144 x 216 for training and inference. [More Info](https://towardsdatascience.com/building-a-deep-learning-model-to-judge-if-you-are-at-risk-1c96f90d666c)

<img width="1287" alt="CollisionOrNot" src="https://github.com/MPEROR-9102/NeuN3t20/assets/97546729/00f338d2-f82e-4680-a2a6-9df7b595c5e6">




## **NeuN3t20 Architecture**

NeuN3t20 architecture consists of 20 layers, that is, 18 layers in the blocks, a convolutional layer, and a fully connected layer at the bottom of architecture respectively.

<img width="1287" alt="NeuN3t20Arch" src="https://github.com/MPEROR-9102/NeuN3t20/assets/97546729/f46b9010-5a01-4bb4-a9ab-aed959a4b48d">

**SF** - Spiking Function;
**BNTT** - Batch Normalization Through Time




## **Training Method**

This work employed BNTT-Backpropagation, that is, Surrogate-Gradient Backpropagation in combination with Batch Normalization Through Time (BNTT) to train from scratch. [BNTT-Backpropagation](https://www.frontiersin.org/articles/10.3389/fnins.2021.773954/full)




## **Evaluation**

<p align="justify">The objective is to compare the performance of the proposed approach, NeuN3t20 against other spatio-temporal feature extractors, which include ConvLSTM and CNN+LSTM, on CollisionOrNot dataset. It includes comparing test accuracy and adversarial robustness(L-infinity Projected Gradient Descent (LinfPGD) attack in a blackbox circumstance for perturbation strengths ranging from 0 to 1).</p>


<p align="center"><img width="480" alt="TestAcc" src="https://github.com/MPEROR-9102/NeuN3t20/assets/97546729/79f882a2-07db-4ee3-a388-b79d15843e53"></p>
<p align="justify">NeuN3t20 surpassed the test accuracy of CNN+LSTM and performed on par with ConvLSTM by achieving a peak accuracy of 97.17%. In terms of parameter count, NeuN3t20 outperformed both the competitive approaches by a great margin having just 0.27 million parameters to perform this event recognition task.</p>
<p align="justify" ><strong>This substantially lower parameter count coupled with competitive accuracy of NeuN3t20 can be supported with the fact of SNNs’ unique spiking behavior modelling and information encoding scheme. NeuN3t20 leveraging event-based or temporal representation of frames is significantly more effective than ANNs processing the frames in a continuous sequence, which in this scenario require a larger number of parameters to capture the same information.</strong></p>


<p align="center"><img width="455" alt="AdvInpAcc" src="https://github.com/MPEROR-9102/NeuN3t20/assets/97546729/0e1c7894-a21e-4f3d-876f-83ce52dd502b"></p>
<p align="justify">The robustness of NeuN3t20 against ConvLSTM is tested(since both have competitive test accuracies). NeuN3t20 is more
robust than ConvLSTM all along the range of perturbation strengths. Especially in the range 0 to 0.1, where the perturbed inputs seem visually imperceptible to the raw inputs, proposed approach performance remained nearly the same without any deterioration</p>
<p align="justify" ><strong>An SNN's temporal development of the neurons' membrane potential is caused by the network's stochastic input from noisy neurons in the form of a Poisson spike train. When compared to ANNs, an SNN is adversarially more resilient due to the intrinsic noise it contains. Particularly in the event of a blackbox attacks, in which the attacker is unaware of the parameters of the target model.</strong></p>
