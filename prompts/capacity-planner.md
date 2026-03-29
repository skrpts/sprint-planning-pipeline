---
type: prompt
id: capacity-planner
title: Capacity Planner
description: "Task prompt for calculating team sprint capacity"
tags: [Production, planning:sprint, planning:team, research:citations]
connections:
  - target: resource-allocation
    type: derived_from
---

## Purpose

Calculates available team capacity for a sprint, accounting for individual availability and commitments.

## Prompt

Calculate team capacity for the upcoming sprint.

**Team roster:**
{{input.team_roster}}

**Sprint duration:** {{input.sprint_duration}} (default: 2 weeks if not specified)

For each team member, account for planned leave, recurring meetings, and other commitments. Produce a capacity summary showing available hours per person, total team capacity in story points, and any risks to capacity.
