---
name: production-change-safety
description: Control production change risk through staged release, monitoring, and rollback.
---

# Production Change Safety

## Purpose
Control production change risk through staged release, monitoring, and rollback.

## Workflow
1. Classify blast radius and reversibility.
2. Require reviewed diffs and relevant tests.
3. Prefer backward-compatible migrations.
4. Stage rollouts where supported.
5. Define health indicators and abort thresholds before release.
6. Test rollback or forward-fix steps.
7. Inspect post-release evidence and document incidents.

## Deliverables
- Risk assessment
- release checklist
- rollback plan
- post-release evidence.

## Verification
- Confirm scope, constraints, and acceptance criteria.
- Ground decisions in repository evidence.
- Run relevant checks and report exact outcomes.
- Record unresolved assumptions and risks.

## Safety
Never expose production credentials to an agent or allow autonomous destructive production changes.

## Completion report
State scope, files inspected or changed, evidence, checks run, outcomes, remaining risks, and approvals required. Never fabricate tool output or test results. Preserve user work and prefer minimal, reversible changes.

## Provenance
Original NOVA SKILLS workflow informed by broad topics in Claude Code Ultimate Guide; not a copied chapter or bundled integration.
