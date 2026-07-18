---
type: skill
id: sprint-plan-generation
title: Sprint Plan Generator
description: "Assembling the committed sprint plan from the refined backlog, capacity, resource allocation, and risk assessment"
tags: [Tested, Agile, Planning]
connections:
  - target: llm-service
    type: runs_on
metadata:
  estimated_duration: "4 minutes"
  avg_tokens: 3000
  trigger: manual
---

## Sprint Plan Generator

This skill assembles the final committed sprint plan — the workflow's deliverable — by selecting and organising backlog items that fit within the team's capacity while respecting dependencies, allocations, and known risks.

### Core Capability

Given the refined backlog, the capacity summary, the resource allocation, and the risk assessment as its evidence base, this skill selects the items to commit, states a clear sprint goal, and summarises committed points against available capacity.

### Method

1. **Selection:** Choose backlog items that fit within available capacity, respecting priority and dependency order.
2. **Assignment reconciliation:** Cross-check the selection against the resource allocation so no member is over-committed and no dependency is stranded.
3. **Goal and summary:** State a single sprint goal and report total committed points versus capacity, flagging any risks that could threaten the commitment.

### Output Structure

A committed sprint plan document: the sprint goal, selected user stories with acceptance criteria, story-point estimates, dependencies, and a committed-versus-capacity summary.
