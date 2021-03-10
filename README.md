
# Lyapunov-Regularized Reinforcement Learning for Power System Transient Stability

This repository contains source code necessary to reproduce the results presented in the following paper:
[Lyapunov-Regularized Reinforcement Learning for Power System Transient Stability](https://arxiv.org/abs/2103.03869)  

Authors: Wenqi Cui and Baosen Zhang  

University of Washington 


# Motivation
Transient stability of power systems is becoming increasingly important because of the growing integration of renewable resources. These resources lead to a reduction in mechanical inertia but also provide increased flexibility in frequency responses. Namely, their power electronic interfaces can implement almost arbitrary control laws. To design these controllers, reinforcement learning (RL) has emerged as a powerful method in searching for optimal non-linear control policy parameterized by neural networks.

A key challenge is to enforce that a learned controller must be stabilizing. This paper proposes a Lyapunov regularized RL approach for optimal frequency control for transient stability in lossy networks. Because the lack of an analytical Lyapunov function, we learn a Lyapunov function parameterized by a neural network. The losses are specially designed with respect to the physical power system. The learned neural Lyapunov function is then utilized as a regularization to train the neural network controller by penalizing actions that violate the Lyapunov conditions. Case study shows that introducing the Lyapunov regularization enables the controller to be stabilizing and achieve smaller losses. 


# Framework for Lyapunov regularized RL
The RNN framework for training the neural network controller with regularization from a seperatly trained neural Lyapunov function
<img src="/RNN.png" height="200px" width="600px" >

# Language and Dependencies
All code are implemented in Python. Data for the power system is imported from MATLAB as 'IEEE_39bus_Kron.mat'. The coeffcient for linear droop control is obtained by fmincon function of Matlab as 'Sol_linear.mat'. We used the open-source Python package TensorFlow 2.0 to implement RNN and train the neural network models.


# Code References
We thank https://sourceforge.net/projects/pg-sync-models for developping open-sorce MATLAB toolbox for Kron Reduction
