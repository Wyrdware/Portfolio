---
date: '2023-10-01T16:34:12-04:00'
title: 'Optimized Schooling Behavior'
tags: ["C#", "AI", "Flocking Algorithm", "Performance Optimization", "Obstacle Avoidance", "Boids"]
summary: "A boid simulation with obstacle avoidance, designer friendly pathing, and optimized for a game embeded in the web browser."
cover:
  image: images/fish_follow.png
weight: 7


---
# Overview

I designed and implemented the 3D schooling simulation for Untitled Fish Game. This was optimized for browsers, supporting hundreds of fish in real time. The system supports advanced features like obstacle avoidance, designer-authored pathing, and spatial bounding, making it ideal for dynamic aquatic or aerial scenes. The player's interaction with this simulation was the core component of gameplay with this project. 

---

# Challenge

Simple flocking algorithms struggle with obstacle avoidance and performance in real-time environments. My goal was to build a performant, extensible simulation capable of avoiding collisions, reacting to environmental bounds, enabling designer control, and maintaining behaviour that could be easily intuited by the player.

---

# Approach

- Built on established flocking algorithms to enable fast iteration and reliable results
- Developed a two-stage obstacle avoidance system using sphere casting and raycasting
- Implemented bounding zones that passively redirect out-of-bounds agents
- Exposed boid behavior to designers via flexible pathing tools (e.g., orbit and directional paths)

---

# Outcome

The system supports large, responsive schools of fish navigating complex 3D environments with both high stability and low performance cost. When demonstrated at expos, the game quickly garnered attention, especialy from children who would become transfixed by their mesmerizing movement and reactivity. As an aside, this was a particularly interesting game to demo as young children were *significantly* better at the game than adults. 
- Fish respond to player proximity and follow authored movement paths
- Simulation runs reliably at large scales, even in dense or obstacle-laden environments
- Designers can easily tune or extend flocking behavior without modifying the core system

---

# Links

- [Play the game:](https://wyrdware.itch.io/fish-game)