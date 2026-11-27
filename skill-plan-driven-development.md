---
name: plan-driven-development
description: Execute complex software changes through reviewable plans and controlled scope.
---

# Plan Driven Development

## Purpose
Execute complex software changes through reviewable plans and controlled scope.

## Workflow
1. Inspect repository and Git state.
2. Split work into ordered tasks with dependencies and verification commands.
3. Flag risky operations for approval.
4. Implement coherent slices and test each slice.
5. Update the plan when evidence changes.
6. Inspect the final diff and report outcomes honestly.

## Deliverables
- Implementation plan
- checkpoint log
- diff review
- verification summary.

## Verification
- Confirm scope, constraints, and acceptance criteria.
- Ground decisions in repository evidence.
- Run relevant checks and report exact outcomes.
- Record unresolved assumptions and risks.

## Safety
Never claim tests passed unless run. Preserve user changes; do not reset or overwrite work without permission.

## Completion report
State scope, files inspected or changed, evidence, checks run, outcomes, remaining risks, and approvals required. Never fabricate tool output or test results. Preserve user work and prefer minimal, reversible changes.

## Provenance
Original NOVA SKILLS workflow informed by broad topics in Claude Code Ultimate Guide; not a copied chapter or bundled integration.
