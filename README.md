# Actor-Policy-Reinforcement-Learning-Catenary-Robots

<p align="center">
  <img width="460" height="300" src="https://github.com/diegosdantonio/Actor-Policy-Reinforcement-Learning-Catenary-Robots/blob/main/figures/EXP1.gif">
</p>

## Introduction
In the realm of aerial cable manipulation, catenary robots have emerged as a novel solution. These systems, each formed by two quadcopters connected via a non-stretchable cable, offer a new approach to complex manipulation tasks like tying knots and hitches.


[![IMAGE ALT TEXT HERE](https://youtu.be/Ci6wI2GcJEw)](https://youtu.be/Ci6wI2GcJEw)

[![IMAGE ALT TEXT HERE](https://youtu.be/rOAVMieaIJA)](https://youtu.be/rOAVMieaIJA)



## The Challenge
Controlling the dynamics of catenary robots presents unique challenges due to the complex, nonlinear effects arising from physical interactions and cable dynamics. The goal is to develop a model that enables coordinated manipulation of interlacing cables.

## Key Contributions
1. **Cooperative Dynamics Model**: Establishing a control model for multiple catenary robots.
2. **Unity Environment Integration**: Creating a simulation environment for refining control strategies.

## Problem Statement
The study explores controlling a system of catenary robots capable of manipulating objects by intertwining their cables, forming a tree-like structure in mid-air.

### World Frame Definition
A global reference frame, $\{\mathcal{W}\}$, is established in $\mathbb{R}^3$ with the z-axis pointing upwards.

### System Dynamics Model
The model focuses on the cooperative transportation of a payload by $n$ quadrotors, each connected by massless cables. 

### Kinematic Model of Each Robot
The position of each robot $i$ at any time $t$ is expressed as:

$$\[ \mathbf{p}_i(t) = \begin{bmatrix} x_i(t) \\ y_i(t) \end{bmatrix} \]$$

### Newton-Euler Equations for Dynamics
For robot $i$ with mass $m_i$, the equation of motion is:

$$\[ m_i \ddot{\mathbf{p}}_i(t) = \mathbf{f}_i(t) + \mathbf{f}_{rl} \]$$

### Control Action Based on Errors
A PD controller is used for trajectory tracking:

$$\[ \mathbf{u}_i(t) = k_p \mathbf{e}_i(t) + k_d \dot{\mathbf{e}}_i(t) \]$$

![Robots Interlacing Cables](figures/robots.png)

## Actor Policy Gradient Method
This method addresses the challenges posed by the catenary robots' complex dynamics.

### Policy Representation
The policy function is defined as:

\[ \pi_\theta(a | s) = P[A=a | S=s; \theta] \]

### Action Space for Catenary Robots
Actions include velocity changes and exploratory actions during the learning phase.

### Objective Function
The goal is to maximize the expected cumulative reward:

\[ J(\theta) = \mathbb{E}_{\pi_\theta}[R(s, a)] \]

### Policy Gradient
Adjusting the policy parameters $\theta$ to maximize the objective function:

\[ \theta_{\text{new}} = \theta_{\text{old}} + \alpha \nabla_\theta J(\theta) \]

## Experiments and Results
In the Unity-based simulation, robots follow specific trajectories, and their control inputs are based on positional errors.

![Linear Projection in Simulation1](https://github.com/diegosdantonio/Actor-Policy-Reinforcement-Learning-Catenary-Robots/blob/main/figures/draw_lines3.png)

![Linear Projection in Simulation2](https://github.com/diegosdantonio/Actor-Policy-Reinforcement-Learning-Catenary-Robots/blob/main/figures/draw_lines.png)

## Conclusions
This research demonstrates the potential of the Actor Policy Gradient framework in a simulated environment and sets the stage for real-world applications. The model assumes robots as point entities in a 2D plane, but future work will consider more complex scenarios.


**References**
1. Meng, X., Ollero, A., et al. (2022). Advances in Aerial Manipulation.
2. D'Antonio, D. S. (Year). The Catenary Robot: Design and Control.
