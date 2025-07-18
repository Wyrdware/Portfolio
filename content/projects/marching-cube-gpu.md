---
date: '2024-05-14T20:36:43-04:00'
title: 'Marching Cube GPU'
tags: ["C#", "HLSL", "Rendering", "Technical Art","Performance Optimization"]
Summary: "Real time scalar field visualization and noise generation in Unity, made to develop a deeper understanding of procedural generation."
cover:
  image: images/mc_compute.png
weight: 6
---
## Overview

This project is an exploration of generating real-time 3D meshes in Unity using a compute shader implementation of the Marching Cubes algorithm. The goal was to experiment with GPU-based mesh generation, chunking, and noise-driven scalar fields.

---

## Challenge

Previous explorations of the marching cube algorithm were single threaded on the CPU, leading to poor performance when modifying the terrain. The goal was to use marching cubes and perlin noise to generate and render scalar fields in real time.

---

## Approach

Implementing marching cubes into a compute shader and utilizing FastNoiseLite to populate the scalar field allowed the generation to take place in real time. This output was chunked to 15x15x15 cubes to stay under unity’s 65,000 vertex limit

---

## Outcome

By moving the marching cubes algorithm to the GPU and utilizing FastNoiseLite, generation was able to be achieved at a large scale and in real time. 

---

## Links

- [GitHub – Wyrdware/marching-cubes-compute](https://github.com/Wyrdware/marching-cubes-compute)
