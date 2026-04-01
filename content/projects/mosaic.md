---
title: "Mosaic"
date: 2022-08-01
summary: "Designed and engineered a Unity package featured at GDC 2025 for its ability to rapidly develop gameplay mechanics and systems. Leveraged by Echoes In The Mists."

tags: ["Unity", "Systems Architecture", "Game Development", "C#", "Modular Design", "Tools", "Data-Driven"]
hiddenInSingle: true
cover:
  image: images/mosaic_diagram.png
  hiddenInSingle: true

weight: 4

---

> *“As a Designer on the Echoes in the Mists dev team, Mosaic provided me with a multitude of useful functions that made implementing game mechanics easy. The Mosaic toolset immensely helped iteration without me ever having to edit code. Since Mosaic features are all modular, I could quickly refine and playtest ideas immediately.”*  
> — Rinnie Bi | Level Developer, Echoes in the Mists

# Overview

Mosaic is a universal gameplay framework I developed for Unity used by designers and developers to build, collaborate on, and share gameplay systems. The framework ensures developed features are scalable, reusable, and fully cross compatible. This allows individuals, studios, and communities to invest in their systems, creating value that is retained across projects. 

Mosaic serves as the architectural foundation for *Echoes in the Mists*, an RIT capstone game featured at various local conventions, showcased at the **2025 GDC New York State Pavilion**, and highlighted as part of RIT’s recognition as the **#3 MS game design program in the U.S**.

---

![combat](/images/mosaic_diagram.png)
**Figure:** *This diagram shows how Mosaic integrates into an actor in Echoes in the Mists. The components inside the Mosaic box make up the full framework, while everything around it is user-developed and extends from it. All gameplay systems including AI, input, behaviors, modifiers, and data tags connect through this lightweight, modular core, allowing systems built for one actor to be reused across all actors with a minimal code footprint.*

# Approach

Mosaic was developed through iterative prototyping and extensive research into scalable architectures, including game object models, programming paradigms, and other related systems such as ability systems and character controllers. Mosaic was also the subject of my graduate thesis.

The resulting framework lies between the game object model and the character controller, offering true modularity through four components: **Behaviors**, **Modifiers**, **Decorators**, and **DataTags**. These four components ensure full modularity across all systems that use Mosaic. The design was validated through use by peers with varying levels of experience on long-term projects and feedback from mentors and colleagues in the field.

---

# Outcome

At GDC 2025, I was proud to demonstrate Mosaic’s value when I presented how my efforts on Mosaic allowed my team’s ambitious capstone game to become possible. Mosaic’s modular design enabled rapid iteration, parallel development across disciplines, and ensured clean architectural boundaries for *Echoes In the Mist*.

Mosaic, even when utilized by novice programmers, helped facilitate development of dynamic gameplay mechanics and systems without introducing architectural overhead.

Mosaic also enabled designers to compose and test behaviors independently. Its success highlights the power of well-designed abstractions to enable ambitious, sustainable game development at scale.

> *“Mosaic works as a springboard in early development. It made prototypes extremely quick to develop, especially for character systems. Because any action could be transferred between entities, creating new players or enemies was simple and consistent. It also streamlined the creation of animators, actions, and attacks by drawing from a shared base.”*  
> — James Zilberman | Software Developer, Bad Ideas Productions 

---

# Interested?

If you’re building scalable systems, prototyping new gameplay mechanics, or need a tools-focused engineer, I’d love to chat about how Mosaic’s ideas might translate to your pipeline.

---

# Links

- [GitHub – Wyrdware/Mosaic](https://github.com/Wyrdware/Mosaic)
- [Used in: Echoes in the Mists →](/projects/echoes)
- [Mosaic & Echoes in the Mists featured in article naming RIT a Top Five Game Design University](https://www.rit.edu/news/rit-named-top-5-university-study-game-design)


