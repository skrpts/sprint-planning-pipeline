---
type: workflow
id: sprint-planning-pipeline
title: Sprint Planning Pipeline
description: "End-to-end sprint planning from backlog to committed plan"
tags: [Production, Tested]
connections:
  - target: sprint-planning
    type: uses
  - target: resource-allocation
    type: uses
  - target: plan-sprint
    type: uses
  - target: allocate-resources
    type: uses
  - target: sprint-plan-generator
    type: uses
  - target: capacity-planner
    type: uses
---

## Overview

This workflow takes a product backlog and team roster through a complete sprint planning process, producing a committed sprint plan with balanced assignments.

## Pipeline Stages

### Stage 1: Backlog Refinement

Invoke the **sprint-planning** skill to break down epics and feature requests into well-scoped user stories with acceptance criteria and story point estimates.

### Stage 2: Capacity Planning

Invoke the **capacity-planner** prompt to calculate available team capacity for the upcoming sprint, accounting for holidays, meetings, and other commitments.

### Stage 3: Sprint Plan Generation

Invoke the **sprint-plan-generator** prompt to select and organise backlog items that fit within the team's capacity, respecting dependencies and priorities.

### Stage 4: Resource Allocation

Invoke the **resource-allocation** skill to assign stories to team members based on skills, availability, and workload balance.

## Output

A committed sprint plan containing:

- Selected user stories with acceptance criteria and story points
- Team member assignments with rationale
- Capacity utilisation summary
- Dependency map and risk flags
