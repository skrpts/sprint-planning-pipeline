---
type: prompt
id: sprint-plan-generator
title: Sprint Plan Generator
description: "Task prompt for generating a structured sprint plan"
tags: [Production, Agile, Planning]
connections:
  - target: sprint-planning
    type: derived_from
---

## Purpose

Generates a complete sprint plan document from backlog items and team velocity data.

## Prompt

Using the refined backlog and team capacity analysis below, select and organize items for the upcoming sprint.

- **Refined backlog:** {{steps.previous.output}}
- **Team capacity:** {{steps.Resource Allocation.output}}

For each selected item, include the user story, acceptance criteria, story point estimate, and any dependencies. Produce a sprint goal statement and a summary of total committed points versus capacity.
