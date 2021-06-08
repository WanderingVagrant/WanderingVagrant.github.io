---
layout: post
title:  "What is a Physics Engine"
#date:   2021-06-06 18:17:00 -0700
categories: jekyll update
---
Hi readers!    
In this post, I'm going to discuss the basics of a physics engine, and give a basic overview different ways in which they are built.     

- [The Absolute Basics](#the-absolute-basics)
- [The Core Loop](#the-core-loop)
- [Rigid Bodies vs Soft Bodies](#rigid-bodies-vs-soft-bodies)
- [Movement](#movement)
- [Collision Detection](#collision-detection)
- [Collision Resolution](#collision-resolution)

## The Absolute Basics
A physics engine is what it sounds like, the part of a program that simulates real-life physics. They can be used in many different contexts, from video games, to biomedical research, to CGI in the most popular movies. But why would someone need a physics engine, and what exactly can they do?    

One use most of you would have experienced already is in animating advanced CGI graphics in modern movies. Detailed 3d cloth and fluid moving is a very difficult thing to animate, and very time-consuming to do by hand, but with the help of a physics engine it can be done well and in less time.      

Another use, and the one my physics engine is based on, is for approximating the movement of objects in video games according to real-life physics. Figuring out the trajectory of a bullet in a shooter and determining the movement of the main character in a platformer is all the work of a physics engine.     


## The Core Loop

![image](images/PhysLoop.png)
But how exactly does a video-game physics engine work? The most commonly used paradigm is by setting up a world where physics happens. Then you add some global constants like gravity or air resistance, and then you add in all the entities to populate the world and do physics on those objects.     

The actual core loop of a physics engine looks somewhat like this on all the objects in the world. Calculate the new positions of all objects based on their current velocities, then detect collisions, and resolve those collisions with a change in momentum or force. However, each of these steps has few different widely used methods.

## Rigid Bodies vs Soft Bodies

For the first step in the loop, calculating the positions of the objects depends a lot on what those objects are, and they can generally be classified into two types. A rigid body, or a soft body. A rigid body is generally the type of object most used in physics classes.     

They are incompressible objects made up of a set of shapes connected by unchangeable joints. Some examples would be a pendulum, a simple stick figure, and most objects in 2d simulation. Rigid bodies are the more simplified and unrealistic type of object since most real-life objects are compressible.     

A soft body on the other hand is the opposite, and consists of components like springs or elastic materials and generally involve much more complex math to calculate the position and forces for. Some examples would be hair, clothes, and most objects in very realistic physics simulations.    

This is why I will elaborate only on rigid body dynamics.

## Movement

For rigid bodies, the main types of motion that we need to account for are rotation and translation. Translation is simply moving the whole body in some direction along the center of mass and can be calculated by the simple equation from the velocity, d = vt.    

However, there are many methods of different precisions for calculating the linear velocity as often the movement equations boil down to a series of differential equations that can't be solved directly quickly. Most physics engines use approximations like Euler's method or more accurate approximations like the Runge-Kutta methods. 

Rotation however occurs whenever a force or impulse is applied at an angle relative to the center of rotation. Based on this angle, and the distance of the force to the center of rotation, and the moment of inertia, we can calculate the angular velocity and therefore the rotation. 

Rotating in 2D as I implemented in my own physics engine is relatively simple as you just rotate something around a central point, but in 3d it becomes much harder. Different methods exist for 3D rotation from the simple Euler Angles that were initially devised, to the complex quaternions that are used in today's modern physics engines.
 
## Collision Detection

A collision is when two objects touch each other or overlap, and in most games it provokes some kind of response, whether it gives you a power-up, or the car deforms spectacularly in a car crash simulation.   

Detecting the collisions is a surprising challenge, however. One obvious method is to check if all possible pairs of objects are colliding, but this method is extremely inefficient because the time it takes increases with the square of the number of objects in the world. This is why most physics engines divide the task into two parts, broad phase and narrow phase.    

In the broad phase, the focus is eliminating all objects that have no chance of colliding with each other such as those extremely far from each other.

Then the narrow phase checks all the pairs of objects that actually have a chance of colliding. 

## Collision Resolution

The final step is collision resolution, what do we do now that we know objects are colliding.? Well in rigid bodies the basic answer is simple, they need to bounce off of each other. There are a few ways of calculating this, but all of them generally use the concept of constraints.     

Constraints are limitations to an object’s degrees of freedom, or how it can move. They can be as simple as forcing two objects to remain a minimum distance apart, or more complicated like the limits to the motion of a human arm. A physics engine can use linear algebra with force or impulse to solve these constraints and find the final positions of the colliding objects.     

That ends this basic overview of how physics engines work.

