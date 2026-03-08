---
type: prompt
id: capacity-planner
title: Capacity Planner
description: "Task prompt for calculating team sprint capacity"
tags: []
connections:
  - target: resource-allocation
    type: derived_from
---

## Purpose

Calculates available team capacity for a sprint, accounting for individual availability and commitments.

## Prompt

Calculate team capacity for the sprint starting {{sprint_start}} lasting {{sprint_length}} days. For each team member, account for planned leave, recurring meetings, and other commitments. Produce a capacity summary showing available hours per person, total team capacity in story points, and any risks to capacity.
