---
date: '2023-09-30T20:36:29-04:00'
title: 'Procedural Terrain'
tags: ["C#", "Procedural Generation", "Data-Driven Design", "Technical Art", "Tools"]
summary: "A series of explorations into procedural terrain generation in Unity."
cover:
  image: images/proc_gen_overview.png
weight: 3


---

# Overview
A series of explorations into procedural terrain generation in Unity.

---

![perlin terrain](/images/proc_terrain.png)

# Curve-Authored Terrain
I built a lightweight procedural terrain generator for Unity focused on artistic control. It uses Perlin noise shaped by animation curves and slope-based texture blending to create authored-feeling arctic landscapes without sacrificing performance.

**My Approach**

- Designed the system so every parameter is editable directly in the Inspector, enabling designers to tune and sculpt biomes.

- Implemented chunk-based generation for scalability, ensuring seamless stitching across large worlds.

- Used slope and height data to drive material blending and procedural prop placement,

**Outcome**
Delivers curated landscapes entirely from data-driven methods. This project established the foundation for my later terrain and GPU-accelerated marching cube systems.

---

![flowfield terrain](/images/mc_terrain.png)

# Marching Cubes Terrain
I built a proof-of-concept system for 3D terrain generation that supports overhangs, arches, and caves using marching cubes and Perlin flow fields. The goal was to produce smooth, continuous terrain without the floating artifacts common in traditional 3D noise.

**My Approach**

- Implemented a marching cubes renderer to visualize scalar fields.

- Generated the scalar field from a vertical gradient distorted by perlin flow fields, maintaining topological consistency while introducing complex features.

- Tuned the algorithm to preserve seamless geometry across chunks without post-processing cleanup.

**Outcome**
The system produces natural, artifact-free overhangs and caves. It established the framework for my later GPU implementation, where I re-engineered the pipeline for better performance.

--- 

![gpu marching cubes](/images/Noise.gif)

# GPU Marching Cubes
I ported my marching cubes terrain system to a compute-shader implementation, enabling real-time, large-scale mesh generation entirely on the GPU. The goal was to move from experimental prototypes to a solution that could be used in production.

**My Approach**

- Implemented the full marching cubes pipeline in a Unity compute shader, generating vertex and index data directly on the GPU.

- Used FastNoiseLite to populate the scalar field with smooth, noise-driven density values.

- Divided output into 15×15×15 voxel chunks to stay within Unity’s 65,000 vertex limit while supporting dynamic updates.

**Outcome**
The GPU implementation transformed the system from slow, single-threaded updates to fully real-time generation, capable of streaming and editing dense volumetric terrain interactively.