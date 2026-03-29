---
type: prompt
id: allocate-resources
title: Allocate Resources
description: "Core prompt for optimising team member assignments"
tags: [Production, planning:sprint, planning:team]
connections:
  - target: resource-allocation
    type: derived_from
---

## Purpose

Produces balanced work assignments by matching team member skills and availability to sprint backlog items.

## Prompt

You are a resource planning specialist. Using the sprint plan and capacity analysis below, produce optimal assignments for each team member.

- **Sprint plan:** {{steps.sprint-plan-generator.output}}
- **Capacity analysis:** {{steps.capacity-planner.output}}

Balance workload evenly, match skills to tasks, flag any conflicts or over-allocations, and provide rationale for each assignment.
