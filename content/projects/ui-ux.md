---
title: "UI UX Systems"
date: 2024-05-01
summary: "Over the years I’ve explored UX and UI design from both the technical and experiential sides, and now teach the subject in WVU’s graduate program. This section highlights a few of the systems I’ve built."
tags: ["UI/UX", "UX Engineering", "Gameplay UI", "Accessibility", "Technical Design"]
cover:
  image: images/uiux_header.png

weight: 8
draft: true

---

# Overview
Over the years I’ve explored UX and UI design from both the technical and experiential sides, and now teach the subject in WVU’s graduate program. This section highlights a few of the systems I’ve built.

---

![pastel radial](/images/pastel_radial.png)

# Pastel (2024)
Engineered a dynamic radial UI system enabling Pastel’s color-mixing gameplay, where players control anywhere from one to ten slimes at once. The interface adapts fluidly to each configuration, visualizing relationships through real-time render textures and multiple cameras. The system I built procedurally generates and caches its masks in real time using compute shaders, **replacing what would have been over 100 hand-authored** assets with a flexible, data-driven approach. Cached generation and parameter matching ensured near-instant performance, while an MVC architecture cleanly separated gameplay logic from rendering. The result was a flexible, performant UI that kept players oriented and reinforced the game’s playful, readable aesthetic.

---

![star inventory](/images/star_ui.png)
# S.T.A.R. (2022)
Led engineering and built a modular, dynamic inventory system in Unity for *STAR*, a large-scale project developed by **27 students over 12 weeks**. Designed as the backbone of the game’s object model, every element that defines an entity, from equipped items and ship hulls to craftable resources, exists within its inventory. This unified structure models all entity components through the same inventory logic, from ship hulls to resources, creating a consistent foundation for gameplay and UI design.

To support a fast-moving, multi-disciplinary team, I developed the inventory to be data-driven and extensible, enabling designers and programmers to implement unique UI layouts and logic without code conflicts. One example, the power-management module, uses a custom triangle selector I built to distribute energy between engines, shields, and weapons through barycentric coordinates, forming the foundation of the game’s strategic combat loop.

---

![grid inventory](/images/re_style.gif) 
# Grid Inventory (2021)
Developed a grid-based inventory system in Unity for items of varying shapes and sizes, where objects transition seamlessly between the game world and inventory space. Each item remains part of the active simulation, able to contract status effects and influence neighboring items within the grid.

Though an earlier project, it reflects my systems mindset, building interfaces that feel like part of the game rather than being layered on top. What I learned here still shapes how I design UI/UX today.
