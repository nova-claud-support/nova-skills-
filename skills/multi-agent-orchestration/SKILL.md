---
name: multi-agent-orchestration
description: Coordinate specialized agents through bounded tasks, explicit ownership, and reviewable integration.
---

# Multi Agent Orchestration

## Purpose
Coordinate specialized agents through bounded tasks, explicit ownership, and reviewable integration.

## Workflow
1. Decompose objectives into independent packages with acceptance criteria.
2. Assign one owner per file.
3. Parallelize research but serialize shared edits.
4. Define handoff contracts for evidence, changed files, risks, and status.
5. Report blockers and uncertainty.
6. Integrate outputs and run complete tests.
7. Cap concurrency and budgets.

## Deliverables
- Task dependency graph
- ownership map
- integration checklist
- final report.

## Verification
- Confirm scope, constraints, and acceptance criteria.
- Ground decisions in repository evidence.
- Run relevant checks and report exact outcomes.
- Record unresolved assumptions and risks.

## Safety
Prevent uncontrolled delegation, shared credentials, and unreviewed external actions.

## Completion report
State scope, files inspected or changed, evidence, checks run, outcomes, remaining risks, and approvals required. Never fabricate tool output or test results. Preserve user work and prefer minimal, reversible changes.

## Provenance
Original NOVA SKILLS workflow informed by broad topics in Claude Code Ultimate Guide; not a copied chapter or bundled integration.
