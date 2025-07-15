---
title: "Mosaic"
date: 2022-08-01
summary: "A universal gameplay framework for Unity that enables full modularity in systems development. Leveraged by Echoes In The Mists"
tags: ["Unity", "Systems Architecture", "Game Development", "C#", "Modular Design", "Tools", "Data-Driven"]
cover:
  image: images/mosaic_diagram.png

weight: 1
---

## Overview

Mosaic is a universal gameplay framework for Unity used by designers and developers to build, collaborate on, and share gameplay systems. The framework ensures developed features are scalable, reusable, and fully cross compatible. This allows individuals, studios, and communities to invest in their systems creating value that is retained accross projects. 

Mosaic serves as the architectural foundation for *Echoes in the Mists*, an RIT capstone game featured at **Roc Games Fest**, showcased at the **2025 GDC NYS Pavilion**, and highlighted as part of RIT’s recognition as the **#3 MS game design program in the U.S**.

---

## Challenge

Game development is inherently iterative, but most gameplay systems are built rigidly, tied closely to a single project’s architecture and difficult to adapt elsewhere. As projects evolve, tech debt accumulates, making features costly to extend, remove, or reuse.

Temporary solutions often become entrenched, bloating the codebase. Less experienced developers, though valuable, can unintentionally compound these issues without clear architectural guidlines. As a result, even well-built systems can struggle to scale across teams, contributors, or future projects.

---

## Approach

Mosaic was developed through iterative prototyping and extensive research into scalable architectures, including game object models, programing paradigms, along with other related systems such as ability systems and character controllers. Mosaic was also the subject of my graduate thesis.

The resulting framework lies between the game object model and the character controller, offering true modularity through four components: **Behaviors**, **Modifiers**, **Decorators**, and **DataTags**. These four components ensure full modularity across all systems that uses Mosaic. The design was validated through use by peers with varying levels of experience on long term projects and feedback from mentors and colleagues in the field.

---

## Outcome

Mosaic demonstrated its value as a modular, scalable gameplay architecture, reducing tech debt and accelerating development. It powered *Echoes in the Mists*, a capstone game showcased at ROC Games Fest and GDC 2025. Its modular design enabled rapid iteration and parallel development across disciplines, while ensuring clean architectural boundaries.

Less experienced programmers successfully implemented complex systems, such as a fully modular animation-matched backstab, without introducing architectural overhead thanks to Mosaic.

Mosaic also enabled designers to compose and test behaviors independently. Its success highlights the power of well-designed abstractions to enable ambitious, sustainable game development at scale.

---

## Current Status

Mosaic is currently undergoing structural revisions. The system has been used in multiple Unity projects and is available for review or walkthroughs upon request.

---

## Interested?

If you’re building scalable systems, prototyping new gameplay mechanics, or need a tools-focused engineer, I’d love to chat about how Mosaic’s ideas might translate to your pipeline.

---

## Links

- [GitHub – Wyrdware/Mosaic](https://github.com/Wyrdware/Mosaic)
- [Used in: Echoes in the Mists →](./echoes)
- [RIT Names a Top 5 University To Study Game Design](https://www.rit.edu/news/rit-named-top-5-university-study-game-design)


