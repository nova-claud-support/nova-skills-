---
name: ai-cost-engineering
description: Control AI feature costs without silently sacrificing quality, privacy, or reliability.
---

# Ai Cost Engineering

## Purpose
Control AI feature costs without silently sacrificing quality, privacy, or reliability.

## Workflow
1. Measure baseline cost by workflow and accepted task.
2. Separate token, tool, storage, and infrastructure costs.
3. Use smaller models only after quality evaluation.
4. Reduce redundant context and cache stable retrieval with invalidation.
5. Enforce per-run budgets server-side.
6. Prevent retry storms.
7. Track cost alongside quality and review effort.

## Deliverables
- Cost baseline
- budget policy
- provider comparison
- efficiency report.

## Verification
- Confirm scope, constraints, and acceptance criteria.
- Ground decisions in repository evidence.
- Run relevant checks and report exact outcomes.
- Record unresolved assumptions and risks.

## Safety
Never bypass billing controls, quotas, or expose API keys.

## Completion report
State scope, files inspected or changed, evidence, checks run, outcomes, remaining risks, and approvals required. Never fabricate tool output or test results. Preserve user work and prefer minimal, reversible changes.

## Provenance
Original NOVA SKILLS workflow informed by broad topics in Claude Code Ultimate Guide; not a copied chapter or bundled integration.
