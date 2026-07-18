---
type: prompt
id: capacity-planner
title: Capacity Planner
description: "Task prompt for calculating team sprint capacity"
tags: [Production, Agile, Citations, Planning]
inputs:
  team_roster:
    label: "Team Roster"
    description: "Full team roster with roles and availability"
    example: "[List team members, roles, and hours available]"
    required: true
    type: text
  sprint_duration:
    label: "Sprint Duration"
    description: "How long the sprint runs"
    example: "2 weeks"
    required: true
    type: text
context_params:
  refined_backlog:
    label: "Refined Backlog"
    description: "The refined, sprintable backlog — used to size capacity risk against the planned scope."
    required: false
    default_from_previous: true
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

**Refined backlog (planned scope):** {{step.context.refined_backlog}}

For each team member, account for planned leave, recurring meetings, and other commitments. Produce a capacity summary showing available hours per person, total team capacity in story points, and any risks to capacity — including whether available capacity is sufficient for the refined backlog's scope.
