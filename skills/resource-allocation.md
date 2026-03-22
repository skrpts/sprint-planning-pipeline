---
type: skill
id: resource-allocation
title: Resource Allocation
description: "Optimises team assignments based on skills, availability, and priorities"
tags: [Production]
connections:
  - target: llm-service
    type: runs_on
---

## Capability

Balances workload across team members considering their skills, current commitments, and project priorities.

## When to Use

- Sprint planning
- Mid-sprint rebalancing
- Cross-team resource requests

## Inputs

Team roster with skills, current assignments, project priority list

## Outputs

Allocation recommendations with rationale and conflict flags
