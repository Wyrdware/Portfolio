---
title: "Mosaic"
date: YYYY-MM-DD
draft: false
summary: "A modular gameplay framework for Unity focused on scalable, reusable systems and rapid iteration."
tags: ["Unity", "C#", "Game Systems", "Modular Design", "Tools Development"]
---

## Project Overview

_One or two sentences that explain what Mosaic is in plain terms. Focus on clarity._  
Example:  
**Mosaic** is a gameplay systems framework for Unity that enables fully modular, decoupled actor behavior across player characters, NPCs, interactables, and more. It was designed to solve the challenges of scalability, code reuse, and rapid iteration during game development.

---

## Problem

_Describe the fundamental issue Mosaic was built to solve. You can emphasize one or more of the following:_
- The throwaway nature of prototyped gameplay code
- The high cost of iteration in Unity’s component model
- How tightly coupled systems create scaling issues for teams
- The difficulty of testing and reusing gameplay logic across actors or projects

---

## My Approach

_This section explains how Mosaic solves the above problems. Cover:_

- **System position**: where Mosaic fits in the engine stack (e.g., between GameObject and controller)
- **Design principles**: modularity, data safety, extensibility
- **Core architecture**:
  - `DataTags`: dynamic, type-safe blackboard for state
  - `Behaviors`: runtime-selectable logic modules (mention utility AI if applicable)
  - `Modifiers` and `Modifier Decorators`: inspired by For Honor, used for time-based and overlapping effects

_Optionally, note influences (e.g., Game Programming Patterns), and how Mosaic improves on Unity’s component model._

---

## Outcome

_What value did Mosaic deliver? Choose examples like:_

- Significant reduction in prefab complexity
- Increased feature reuse across actors/projects
- Faster design iteration by non-programmers
- Multiple devs working on independent systems without conflicts
- Adoption or interest by external teams or collaborators

---

## Why It Matters

_A brief but strong paragraph connecting Mosaic’s usefulness to larger development goals:_

- Scaling teams and pipelines without scaling complexity
- Reducing technical debt in gameplay code
- Creating durable systems that don’t get rewritten every project
- Empowering designers with reusable, composable building blocks

---

## Project Status

_A short note on its current state:_
- Whether it's production-ready or under active revision
- What improvements are being made (e.g., refactoring, documentation)
- Whether you plan to open-source or keep it private (and how to request access)

---

## Technologies Used

_List only the essentials to signal technical literacy:_

- Unity (version)
- C#
- ScriptableObjects
- Git (mono-repo ready, CLI preferred)
- Custom inspector tooling (if relevant)

---

## Optional Extras

_Leave space to add these if/when you're ready:_
- Embedded YouTube demo or short WebM/GIF
- Before/after prefab complexity screenshots
- Link to design doc, Notion page, or technical write-up
