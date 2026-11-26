---
name: loop-graph-engineering
description: Design bounded loops and explicit state graphs for automated development workflows.
---

# Loop Graph Engineering

## Purpose
Design bounded loops and explicit state graphs for automated development workflows.

## Workflow
1. Use loops only with measurable progress and stop rules.
2. Model multi-stage work as states, guards, and transitions.
3. Set iteration, time, and tool budgets.
4. Separate planning, execution, verification, and repair.
5. Persist state, detect repeated unchanged outputs, and test timeout, cancellation, and partial completion.

## Deliverables
- State diagram
- transition table
- stop-condition tests
- run trace.

## Verification
- Confirm scope, constraints, and acceptance criteria.
- Ground decisions in repository evidence.
- Run relevant checks and report exact outcomes.
- Record unresolved assumptions and risks.

## Safety
Never create unbounded autonomous loops or unattended external changes.

## Completion report
State scope, files inspected or changed, evidence, checks run, outcomes, remaining risks, and approvals required. Never fabricate tool output or test results. Preserve user work and prefer minimal, reversible changes.

## Provenance
Original NOVA SKILLS workflow informed by broad topics in Claude Code Ultimate Guide; not a copied chapter or bundled integration.
