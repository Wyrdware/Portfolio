---
title: "Data Structure Debug Library"
date: 2023-04-30
summary: "A C++ debug and visualization tool developed to help students in SUNY Poly's CS 240 course learn data structures and algorithms."
tags: ["C++", "Tools Programming", "Debugging Tools", "Data Structures", "Technical Education"]
cover:
  image: images/debug_bars.png
weight: 6


---

# Overview

The **Data Structure Debug Library** is a lightweight C++ library developed during my time at SUNY Polytechnic Institute. The tool was developed for use by the *CS 240: Data Structures & Algorithms* class to provide students with meaningful insights into their code’s behavior.

I served as technical lead on this project, managing scope and developing the core systems and architecture. By emphasizing modularity and scalability early on in development, we were able to remove bottlenecks and merge conflicts during team collaboration. 

---

# Challenge

Students in CS 240 often encountered difficulty debugging complex data structures like trees, linked lists, and graphs. Traditional debugging tools tended to be too cumbersome for newer programmers. There was a need for a simple, accessible tool that could log and visualize the runtime state of student implementations without altering their underlying logic or requiring external dependencies.

---

# Approach

I led the design of the library’s architecture, collaborating with team members to ensure each module was incorporated in a scalable manner and was easy to use. The project was designed to be a header-only library so students could easily add it to their projects. JSON for Modern C++ was used to serialize the input data structure, and TIGR was used to render the visual analyzer. The program was designed to be non-intrusive and does not require modification of the program logic. It makes effective use of templates to support a variety of types and accounts for them dynamically.

---

# Outcome

The modular architecture allowed our team to generate a variety of features allowing users to visualize graphs and other data structures in a consistent way. This library's lightweight, header-only design makes adoption seamless. The tool received positive feedback from both faculty and students, highlighting its clarity and ease of use.

---

# Links

[GitHub – Wyrdware/DSDebug](https://github.com/Wyrdware/DSDebug)

