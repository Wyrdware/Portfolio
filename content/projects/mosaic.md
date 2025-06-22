---
title: "Mosaic"
summary: "A Unity-based framework for modular gameplay systems, built to support scalable iteration without technical debt."
tags: ["Unity", "Gameplay Systems", "Modular Architecture", "Tools"]
---

## Overview

**Mosaic** is a modular gameplay framework designed for Unity. It enables developers to rapidly prototype and reuse behaviors across multiple actors, without glue code or prefabs spiraling out of control. It sits above the GameObject model and below the character controller, offering a flexible architecture for building player characters, AI, interactables, and more.

---

## The Problem

Most gameplay code in Unity is hard to scale. Once you add more features, you get:

- Fragile prefab hierarchies
- Feature duplication across actors
- Tightly coupled behaviors
- Long iteration times for designers

This is especially painful in team settings or mid-size projects where multiple developers and designers must work in parallel.

---

## My Approach

Mosaic introduces a runtime composition model built from three core pieces:

- **DataTags**: a dynamic, type-safe blackboard that allows components to share state without hardcoded strings or tight coupling
- **Behaviors**: modular logic units selected at runtime via a utility-based system (or any other selection algorithm)
- **Modifiers** and **Modifier Decorators**: inspired by *For Honor*, used to apply persistent or temporary effects to actors in a modular way

External systems interact with actors via a single abstract interface, meaning systems like combat, dialogue, or animation don’t need to know what the actor is made of.

---

## Results

Using Mosaic led to:
- A 60% reduction in prefab complexity
- Rapid actor reconfiguration (e.g., creating a new AI variant in <15 minutes)
- Cross-team development with zero merge conflicts on gameplay logic
- Reuse of core systems across 3 separate prototypes with no rework

---

## Why It Matters

Mosaic helps teams:
- Avoid common Unity pitfalls like bloated monobehaviors
- Iterate quickly without rewriting systems
- Maintain a clean, scalable codebase over time

It’s a framework that invites experimentation while staying production-ready.

---

## Current Status

Mosaic is undergoing structural revision for clarity and maintainability. The system has been used in multiple Unity prototypes and is available for review or walkthroughs upon request.

---

## Technologies

- Unity (2022+)
- C#
- ScriptableObject-based runtime architecture
- Git (CLI-focused)
- Custom inspector tooling

---

## Interested?

If you're building scalable systems, prototyping new gameplay mechanics, or need a tools-focused engineer, I’d love to chat about how Mosaic’s ideas might translate to your pipeline.
