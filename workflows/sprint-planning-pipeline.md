---
type: workflow
id: sprint-planning-pipeline
title: Sprint Planning Pipeline
description: "End-to-end sprint planning from backlog to committed plan"
tags: [Production, Tested, Agile, Planning]
connections:
  - target: sprint-planning
    type: uses
  - target: resource-allocation
    type: uses
  - target: progress-tracking
    type: uses
  - target: plan-sprint
    type: uses
  - target: allocate-resources
    type: uses
  - target: track-progress
    type: uses
  - target: sprint-plan-generator
    type: uses
  - target: capacity-planner
    type: uses
  - target: llm-service
    type: runs_on
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

## Inputs

| Name | Required | Description | Example |
|------|----------|-------------|---------|
| `{{input.backlog_items}}` | Yes | Backlog items or epics to plan into the sprint | User stories, feature requests, or epic descriptions |
| `{{input.team_roster}}` | Yes | Team members with their skills and availability | "Alice (frontend, 8pts), Bob (backend, 6pts)" |
| `{{input.sprint_duration}}` | No | Length of the sprint in weeks (defaults to 2) | "2 weeks" |

## Outputs

| Name | Description |
|------|-------------|
| Sprint plan | Selected user stories with assignments, capacity utilisation, and dependency map |

## Setup

Before running this workflow:

1. **Prepare your backlog** — gather backlog items, epics, or feature requests to feed into the pipeline. You can paste them directly or pull from your project management tool.
2. **List your team** — note each team member's skills, capacity, and any upcoming absences.

No specific AI provider or API key is required beyond your configured skrptiq LLM provider.

## Provider Notes

- Works well with any model — no specific provider requirements
- Larger models may produce more nuanced capacity and dependency analysis

## Example Input

To test this workflow immediately after import:

```
Backlog items: "As a user I can reset my password via email", "As an admin I can bulk-import users from CSV", "Refactor authentication module for OAuth2 support"
Team roster: "Alice (frontend, 8pts available), Bob (backend, 10pts available), Carol (full-stack, 6pts available)"
Sprint duration: 2 weeks
```
