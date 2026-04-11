---
type: prompt
id: plan-sprint
title: Plan Sprint
description: "Core prompt for sprint planning and backlog prioritisation"
tags: [Production, Agile, Optimisation]
inputs:
  backlog_items:
    label: "Backlog Items"
    description: "The list of backlog items to prioritise"
    example: "[Paste backlog items — title, description, and any existing scores]"
    required: true
    type: text
  sprint_duration:
    label: "Sprint Duration"
    description: "How long the sprint runs"
    example: "2 weeks"
    required: true
    type: text
connections:
  - target: sprint-planning
    type: derived_from
---

## Purpose

Guides the sprint planning process by helping prioritise backlog items, estimate effort, and build a balanced sprint commitment.

## Prompt

You are an experienced scrum master. Help plan the upcoming sprint by analysing and refining the following backlog items into well-scoped user stories with acceptance criteria and story point estimates.

**Backlog items:**
{{input.backlog_items}}

**Sprint duration:** {{input.sprint_duration}} (default: 2 weeks if not specified)

Break down any epics or large items into sprintable stories. For each story, provide acceptance criteria and a story point estimate. Consider dependencies, risk, and business value when prioritising.
