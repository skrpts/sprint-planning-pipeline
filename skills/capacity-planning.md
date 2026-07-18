---
type: skill
id: capacity-planning
title: Capacity Planner
description: "Calculating available team capacity for a sprint from the roster, accounting for leave, meetings, and other commitments"
tags: [Tested, Agile, Planning]
connections:
  - target: llm-service
    type: runs_on
metadata:
  estimated_duration: "3 minutes"
  avg_tokens: 2500
  trigger: manual
---

## Capacity Planner

This skill calculates the team's realistic available capacity for the upcoming sprint, so the sprint plan is committed against genuine availability rather than a headline headcount.

### Core Capability

Given the team roster and sprint duration, this skill works out per-person available hours, converts them into a total team capacity in story points, and surfaces the commitments — planned leave, recurring meetings, on-call, and other overheads — that erode nominal capacity.

### Method

1. **Per-person availability:** For each team member, start from nominal sprint hours and subtract planned leave, recurring meetings, and other known commitments.
2. **Capacity conversion:** Aggregate available hours into a total team capacity expressed in story points using the team's established velocity.
3. **Risk surfacing:** Flag any capacity risks — single points of failure, thin coverage, or members whose availability is uncertain.

### Output Structure

A capacity summary showing available hours per person, total team capacity in story points, and any risks to capacity. This feeds the sprint plan generation stage downstream.
