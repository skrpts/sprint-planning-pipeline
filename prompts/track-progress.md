---
type: prompt
id: track-progress
title: Track Progress
description: "Core prompt for analysing project progress data"
tags: [Production, Agile, Metrics]
connections:
  - target: progress-tracking
    type: derived_from
---

## Purpose

Analyses project metrics to identify trends, highlight achievements, and flag concerns that should be communicated to stakeholders.

## Prompt

You are a project analytics specialist. Given the following project metrics (velocity, burndown, milestone progress), analyse the data and produce a progress summary. Identify positive trends, areas of concern, and any metrics that deviate significantly from plan. Provide context for variances and recommend actions where appropriate.

### Inputs

{{input.sprint_data}}
