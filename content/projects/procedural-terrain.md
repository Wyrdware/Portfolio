---
date: '2023-09-30T20:36:29-04:00'
title: 'Procedural Terrain'
tags: ["C#", "Procedural Generation", "Data-Driven Design", "Technical Art", "Tools"]
summary: "A lightweight terrain generation tool using Perlin noise and animation curves to create hand-tuned environments in Unity."
cover:
  image: images/proc_terrain.png
weight: 3
---
## Overview

A lightweight procedural terrain generator for Unity, focused on artistic control and fast iteration. By combining Perlin noise, animation curves, and slope-based texture blending, it generates rich arctic landscapes with a curated, handcrafted aesthetic, without sacrificing the benefits of procedural content.

---

## Challenge

I wanted to explore procedural generation with perlin noise, and see how I could take a single layer and evoke a specific environment. The parameters had to be modifiable through just the inspector, allowing for quick iterations and the authoring of biome-specific terrain features.


---

## Approach

The key to achieving a hand-authored aesthetic was through the modification of perlin noise through animation curves in the inspector. This allowed for sculpting the terrain elevation and features of distinct biomes. Slope and height-based texture mapping and procedural prop placement brought fidelity to the geometry. Procedural generation was optimized through the use of chunks to aid in scalability. 

---

## Outcome

This procedural terrain generator is capable of producing a striking arctic landscape with a hand crafted feel, entirely through data-driven methods. Animation curves were utilized to generate biome-specific features while retaining a curated appearance. What this technique really does is put emphasis on generating procedural features that are seamlessly stitched together. Going forward I would like to apply these techniques to 3D perlin flow fields rendered through marching cubes. I discuss the advantages of 3D perlin flow fields over 3D perlin noise [here](/projects/scalar-field-visualization/).

---

## Links

- [GitHub – Wyrdware/ArcticTerrainGen](https://github.com/Wyrdware/ArcticTerrainGen)
