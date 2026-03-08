---
type: prompt
id: sprint-plan-generator
title: Sprint Plan Generator
description: "Task prompt for generating a structured sprint plan"
tags: []
connections:
  - target: sprint-planning
    type: derived_from
---

## Purpose

Generates a complete sprint plan document from backlog items and team velocity data.

## Prompt

Given the following product backlog and team velocity of {{velocity}} points per sprint, select and organise items for the upcoming sprint. For each selected item, include the user story, acceptance criteria, story point estimate, and any dependencies. Produce a sprint goal statement and a summary of total committed points versus capacity.
