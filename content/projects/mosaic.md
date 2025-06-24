---
title: "Mosaic"
date: 2022-08-01
draft: false
summary: "A modular Unity framework for building scalable, reusable gameplay systems—used in the award-winning Echoes in the Mists and showcased at GDC."
tags: ["Unity", "Systems Architecture", "Game Development", "C#", "Modular Design"]
---

## Overview

Mosaic is a modular gameplay framework for Unity that enables designers and developers to build scalable, reusable gameplay systems. It became the architectural foundation for *Echoes in the Mists*, an RIT capstone game featured at Imagine RIT, spotlighted by Facebook and RIT, and showcased at the 2025 GDC NYS Pavilion.

---

## Challenge

Gameplay systems are often tightly coupled and hard to extend or reuse, especially in student teams. This leads to brittle, one-off solutions and code debt that slows down iteration and limits collaboration.

---

## Approach

- Designed a framework that sits between Unity’s GameObject model and the character controller
- Built modular runtime elements: **Behaviors**, **Modifiers**, **Decorators**, and **DataTags**
- Enabled runtime composition and deconstruction of features without code duplication
- Integrated a utility-based decision system to support modular AI behavior selection
- Created a unified external interface for interacting with actors abstractly

---

## Outcome

- Used in *Echoes in the Mists* ([view project →](./echoes)), a capstone game showcased at Imagine RIT and GDC
- Enabled rapid collaboration across disciplines and clean separation of systems
- Allowed a junior teammate to implement a full animation-matched backstab system in two days—with zero added tech debt—thanks to Mosaic’s reusable structure
- Resulting features were fully cross-compatible across characters and projects
- Contributed to RIT's recognition as a top 5 game design school (Princeton Review 2025)

---

## Tech Stack

Unity · C# · Modular Architecture · ScriptableObjects · Utility AI · Runtime Composition

---

## Current Status

Mosaic is undergoing significant structural revisions. The system has been used in multiple Unity projects and is available for review or walkthroughs upon request.

---

## Interested?

If you're building scalable systems, prototyping new gameplay mechanics, or need a tools-focused engineer, I’d love to chat about how Mosaic’s ideas might translate to your pipeline.

---

## Links

- [GitHub – Wyrdware/Mosaic](https://github.com/Wyrdware/Mosaic)
- [Used in: Echoes in the Mists →](./echoes)
