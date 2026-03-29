---
type: source
id: scrum-guide
title: Scrum Guide
description: "Reference material for Scrum framework practices and ceremonies"
tags: [Production, Agile, Planning]
connections: []
---

## Sprint Planning

Sprint planning is the event that kicks off each sprint. The entire Scrum team collaborates to define what can be delivered and how the work will be achieved.

### Inputs
- **Product backlog** — refined, ordered by the product owner, with top items meeting the Definition of Ready
- **Team capacity** — available hours per person for the sprint, accounting for leave, meetings, and other commitments
- **Velocity** — trailing 3-sprint average of completed story points (see Velocity section below)

### Outputs
- **Sprint goal** — a single, concise objective that gives the team a shared purpose and flexibility in how they achieve it
- **Sprint backlog** — the set of product backlog items selected for the sprint, plus a plan for delivering them

### Timebox
- 4 hours maximum for a 2-week sprint
- 2 hours maximum for a 1-week sprint
- Split into two parts: *what* will be done (item selection) and *how* it will be done (task breakdown)

## Estimation

### Fibonacci Scale
Use the modified Fibonacci sequence for story point estimates: **1, 2, 3, 5, 8, 13, 21**. Higher numbers reflect greater uncertainty — if something is estimated at 13 or 21, it likely needs breaking down further.

- **1** — trivial change, well-understood, minimal risk
- **2** — small task, straightforward implementation
- **3** — moderate effort, some decisions to make
- **5** — meaningful work, may involve multiple components
- **8** — significant effort, likely needs breaking into subtasks
- **13** — large and uncertain, should be split if possible
- **21** — too large for a single sprint item, must be decomposed

### T-Shirt Sizing
Use T-shirt sizes (XS, S, M, L, XL) for rough initial estimates during backlog refinement. Map to Fibonacci during sprint planning:
- XS = 1, S = 2, M = 3–5, L = 8, XL = 13+

### Planning Poker Process
1. Product owner describes the item and answers clarifying questions
2. Each team member privately selects an estimate
3. All estimates are revealed simultaneously
4. If estimates diverge significantly, the highest and lowest estimators explain their reasoning
5. Re-estimate after discussion until the team converges
6. If consensus cannot be reached after two rounds, take the higher estimate

## Definition of Ready

A product backlog item is ready for sprint planning when it meets all of the following:

- [ ] User story is written with clear "As a / I want / So that" structure
- [ ] Acceptance criteria are written and testable
- [ ] Dependencies on other teams or systems are identified and resolved (or have a plan)
- [ ] The item is estimable — the team understands it well enough to size it
- [ ] The item is small enough to complete within one sprint
- [ ] UI/UX designs are available (if applicable)
- [ ] Technical approach has been discussed (if the item involves significant unknowns)

Items that do not meet the Definition of Ready should not enter sprint planning. Send them back to refinement.

## Definition of Done

An increment is complete when it meets all of the following:

- [ ] Code is complete and implements all acceptance criteria
- [ ] All automated tests pass (unit, integration, end-to-end as applicable)
- [ ] Code has been peer reviewed and approved
- [ ] Documentation is updated (user-facing docs, API docs, inline comments as needed)
- [ ] Deployed to staging and verified
- [ ] No known defects introduced
- [ ] Product owner has accepted the increment

The Definition of Done is non-negotiable. Work that does not meet it is not done, regardless of how much effort went in. Partially done work is not counted towards velocity.

## Velocity

### How to Calculate
Velocity is the sum of story points for all items that met the Definition of Done in a sprint. Items that were partially completed score zero — there is no partial credit.

### Using Velocity for Planning
- Use the **trailing 3-sprint average** as the baseline for capacity planning
- If the team's composition or circumstances have changed significantly, weight recent sprints more heavily
- For new teams without history, start conservatively and adjust after 2–3 sprints
- **Never use velocity as a performance metric.** It is a planning tool, not a productivity measure. Comparing velocity across teams is meaningless. Using it to pressure teams to "go faster" leads to estimate inflation, which destroys its usefulness.

### Velocity Adjustments
- Subtract capacity for known absences (e.g., if a team member is on leave for half the sprint, reduce expected velocity proportionally)
- Account for sprint-specific overhead (e.g., a major release, a company event)
- If velocity is volatile (>30% variation between sprints), investigate the cause before adjusting planning

## Sprint Backlog Management

### Rules During the Sprint
- **Only the development team** can add or remove items from the sprint backlog
- The **product owner** can clarify scope and acceptance criteria but cannot change the sprint goal or force additional work in
- If new urgent work emerges, the team and product owner negotiate — something of equal size must be removed
- Items not completed by sprint end return to the product backlog. The product owner re-prioritises them for a future sprint — they do not automatically roll into the next sprint

### Healthy Sprint Backlog Practices
- Break selected items into tasks of roughly half a day to two days of work
- Make tasks visible and update status daily (not just at stand-up)
- If an item is blocked for more than one day, escalate it — do not let it sit silently
- Re-estimate remaining work mid-sprint if reality has diverged from the plan

## Common Anti-Patterns

### Estimate Padding
Teams inflate estimates to create a safety buffer. This erodes trust, makes velocity meaningless, and hides the real impediments. Instead, be honest about uncertainty and use spikes to reduce unknowns before committing.

### Carrying Over Incomplete Work Without Discussion
Silently rolling unfinished items into the next sprint avoids the uncomfortable conversation about why they were not completed. Always discuss carry-overs in the retrospective. Was the estimate wrong? Was scope unclear? Were there blockers? Each carry-over is a learning opportunity.

### Treating the Sprint Goal as Optional
The sprint goal exists to give the team focus and a basis for trade-off decisions during the sprint. If the team regularly ignores it or treats it as a formality, sprint planning loses its strategic value. The sprint goal should influence which items are selected and how the team prioritises when things go sideways.

### Skipping Retrospective Actions
Running a retrospective without following through on improvement actions is worse than not running one at all — it teaches the team that raising problems is pointless. Limit retrospective actions to 1–2 concrete, achievable improvements. Track them visibly. Review progress at the next retrospective.

### Overcommitting
Taking on more work than velocity supports to please stakeholders or "stretch" the team. This leads to rushed work, quality shortcuts, and burnout. Commit to what the data says the team can deliver, then focus on removing impediments to go faster sustainably.

### Not Refining the Backlog
Arriving at sprint planning with unrefined items forces the team to do refinement and planning in the same session, leading to poor estimates and vague commitments. Dedicate time each sprint (typically 10% of capacity) to refining upcoming items so they meet the Definition of Ready.
