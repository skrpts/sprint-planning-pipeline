---
type: prompt
id: sprint-plan-generator
title: Sprint Plan Generator
description: "Task prompt for generating a structured sprint plan"
tags: [Production, Agile, Planning]
context_params:
  refined_backlog:
    label: "Refined Backlog"
    description: "The refined, sprintable backlog from the sprint planning stage."
    required: false
  team_capacity:
    label: "Team Capacity"
    description: "The capacity summary — available hours and total capacity in story points."
    required: false
  resource_allocation:
    label: "Resource Allocation"
    description: "Story-to-member assignments and workload balance."
    required: false
  risk_assessment:
    label: "Risk Assessment"
    description: "Identified risks that could threaten the sprint commitment."
    required: false
    default_from_previous: true
connections:
  - target: sprint-planning
    type: derived_from
---

## Purpose

Generates a complete sprint plan document from backlog items and team velocity data.

## Prompt

Using the refined backlog, team capacity, resource allocation, and risk assessment below, select and organize items for the upcoming sprint.

- **Refined backlog:** {{step.context.refined_backlog}}
- **Team capacity:** {{step.context.team_capacity}}
- **Resource allocation:** {{step.context.resource_allocation}}
- **Risk assessment:** {{step.context.risk_assessment}}

For each selected item, include the user story, acceptance criteria, story point estimate, and any dependencies. Reconcile the selection against the resource allocation so no member is over-committed, and account for the flagged risks. Produce a sprint goal statement and a summary of total committed points versus capacity.
