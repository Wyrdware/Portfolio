---
title: "Data Structure Debug Library"
date: 2023-04-30
draft: false
summary: "A C++ debug and visualization tool designed to help students understand data structures in real time, used in SUNY Poly's CS 240 course."
tags: ["C++", "Debug Tools", "Educational Software", "Data Structures", "Visualization"]
---

## Project Overview

The **Data Structure Debug Library** is a lightweight C++ utility built to assist students in understanding, visualizing, and debugging their data structure implementations. Developed during my time at SUNY Polytechnic Institute, the tool was developed for *CS 240: Data Structures & Algorithms* to provide students with meaningful insights into their code’s behavior.

I served as technical lead on this group project, managing scope and developing the core systems and architectur.By emphasizing modularity and scalability early on in development, we were able to remove bottlnecks and merge conflicts during team collaboration. 

---

## Problem

Students in CS 240 often encountered difficulty debugging complex data structures like trees, linked lists, and graphs—especially when recursion, pointer errors, or logical bugs were involved. Traditional step-debugging tools were either too cumbersome or opaque for newer programmers.

There was a need for a simple, accessible tool that could log and visualize the runtime state of student implementations without altering their underlying logic or requiring external dependencies.

---

## My Approach

I led the design of the library’s architecture, collaborating with peers to ensure each module met our goals of clarity, minimal setup, and type safety. 
I personally implemented [X] and reviewed/integrated.
- **Non-intrusive**: Easy to drop into existing student projects with minimal setup
- **Header-only**: To avoid additional build complexity
- **Templated and flexible**: Supporting a variety of student-defined types and implementations
- **Extensible**: With core modules for linked lists, binary trees, and other common structures

### Key Features:
- `log_tree(Node*)` – Traverses and outputs tree structure to terminal or file
- `log_list(Node*)` – Prints linked list state and pointer relationships
- Structure-specific checks for null pointers, invalid links, and malformed structure shapes
- Plaintext outputs that can be used with external visualization tools

---

## Outcome

- Successfully deployed in SUNY Poly's *CS 240* course
- Helped students catch difficult logic errors (e.g. double-frees, orphaned nodes)
- Reduced time-to-debug in assignment testing
- Received positive informal feedback from instructors and students alike

---

## Technologies Used

- **Language**: C++17
- **Architecture**: Header-only modules with minimal dependencies
- **Design goals**: Simplicity, safety, and extensibility for educational settings

---

## Why It Matters

This project showcases:
- My **C++ proficiency**, particularly in designing type-safe, reusable utilities
- Strong **educational UX instincts**, designing for beginner-level programmers
- A focus on **developer tooling and internal software** that improves workflows
- Ability to **own and deliver a solution end-to-end**

---

## Repository

View the source and usage examples here:  
[GitHub – Wyrdware/DSDebug](https://github.com/Wyrdware/DSDebug)

---

## Future Improvements

- Add support for heap and hash table visualizations
- Integrate with graphical viewers (e.g. Graphviz, HTML outputs)
- Build a runtime sandbox for interactive demos

