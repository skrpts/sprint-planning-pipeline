# Release Notes

## v1.1.29
GH#863 Wave 1 (#858-A1 class) — fix the intent/output mismatch (K-045): the bundle shipped the `sprint-plan-generator` and `capacity-planner` prompts and the docs said to run them, but the `execution:` block never invoked either — so the workflow's real deliverable (the committed sprint plan) and the capacity summary were never produced. Wired both as execution steps in dependency order with backing skills so they are `from_step`-addressable: added a **Capacity Planner** step (skill `capacity-planning`) after backlog refinement, and a **Sprint Plan Generator** step (skill `sprint-plan-generation`) as the last content step before language-polish. Rewired the generator's cross-step inputs to an explicit `from_step`-bound graph via named `context_params` (`{{step.context.*}}`): refined backlog ← Sprint Planning, team capacity ← Capacity Planner, resource allocation ← Resource Allocation, risk assessment ← Risk Assessment — replacing the old positional/title refs (`{{steps.previous.output}}`, `{{steps.Resource Allocation.output}}`). Completed the tail: repinned `polish-language` 1.0.1→1.0.6 (the version exposing the bindable `source` slot) and bound `language-polish`'s `source` ← the Sprint Plan Generator, so the `output_step` polishes the actual committed sprint plan rather than its positional previous. Manifest: +2 skills (skills 1→3, total 6→8). No new required inputs.

## v1.1.28
GH#845 — republish with American English (en-US) content, completing the source-only GH#805 flip that never reached the Hub. Copy only — no functional or behaviour change.

## v1.1.27
GH#753 — supply allocate-resources via `bindings: sprint_plan { from_step: "Sprint Planning" }` and re-pin the dep to v1.0.3 (position-safe). Restores the resolved reference after the shared-prompt fix; no behavior change. Canonical scan clean.

## v1.1.26
GH#745 — declare per-step `output: {name, type}` on every execution step (sprint_plan/text, resource_allocation/text, progress/text, risk_assessment/text, polished_plan/text). Lights up the #744 rich flow-map. Content-only; no bindings or logic changes.

## v1.1.25
GH#645 Row 3b — migrate to K-037 dep-referenced schema. Strip 11 inline shared-content files and declare 11 hub-shared deps (UUID id + slug name + version + checksum from `gen-dep-checksums.mjs`). Internal slug references rewritten for E2 rename/mirror-drop pair(s): sprint-ceremony-playbook→planning-playbook. Closes pre-Step-3 inline-vendoring for this bundle.

## v1.1.24
Wave 2: re-signed with canonical engine signing pipeline.

## v1.1.23
Tags migrated inline into manifest (GH#586). tags.yaml retired.

## v1.1.22
Bundle re-signed with canonical engine signing pipeline (Wave 2 migration).

## v1.1.21
Signature fix — RELEASE_NOTES.md now included in integrity checksum.

## v1.1.20
Initial catalog release with full structural and content-quality validation. All scanner checks pass.
