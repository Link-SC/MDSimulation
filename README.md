# MDSimulation  
Welcome to my CS1501 Programming Assignment. This task was derived from a programming assignment in the Princeton course COS226. This assignment uses an event-driven approach to simulate the motion of N colliding particles according to the laws of elastic collisions. More information please see http://arxiv.org/abs/2201.01100.  

Anyone is welcome to discuss with me about this or anything else 😉

-----

### Introduction
This is a 2D event-driven molecular dynamics simulation of elastic collisions between hard spheres, implemented in Java. This project visualizes particle motion in a unit box with configurable initial conditions.

-----

### Features

- **Elastic Collisions**: Particle-particle and particle-wall collisions with momentum conservation.
- **Event-Driven Simulation**: Priority queue-based approach for efficient collision prediction.
- **Color Support**: Particles can be customized with RGB colors.
- **Input Flexibility**: Load initial particle states from a text file.
- **Visualization**: Real-time animation using `StdDraw` from Princeton's `algs4` library.

This program uses a time-driven way to carry out experimental simulation, in the event-driven simulation, all particles move in straight trajectories with constant velocity between collisions. Therefore, we only need to maintain a time-ordered priority queue of future events to simulate what will happen. At any given time, the priority queue contains all collisions that may occur in the future. When particles collide and change direction, some events on the priority queue become invalid. So we can adopt a lazy strategy that leaves invalid conflicts on the priority queue, waiting for them to be identified and discarded when they are removed.  

------

### Input Data Format
The format of the dataset containing the initial information of the ball is as follows.  
`N`  
`rx ry vx vy mass radius r g b`  

Example Input ( data.txt )  
`4`  
`.1 .3 .01 0 .05 1 50 50 50`  
`.45 .3 0 0 .05 1 50 50 50`  
`.5501 .3 0 0 .05 1 50 50 50`  
`.6502 .3 0 0 .05 1 50 50 50`  

-----

### Prerequisites

- **Java 17+**
- [algs4.jar](https://algs4.cs.princeton.edu/code/) (Princeton Algorithms Library)

