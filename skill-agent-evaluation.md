---
name: agent-evaluation
description: Evaluate coding agents using repeatable tasks, acceptance tests, and evidence.
---

# Agent Evaluation

## Purpose
Evaluate coding agents using repeatable tasks, acceptance tests, and evidence.

## Workflow
1. Build representative tasks and define outcomes before runs.
2. Capture baseline commit, environment, model, and tools.
3. Score correctness, regressions, security, maintainability, and test quality.
4. Measure latency and cost separately.
5. Repeat nondeterministic trials and version benchmark changes with rationale.

## Deliverables
- Benchmark specification
- run manifest
- scorecard
- failure taxonomy.

## Verification
- Confirm scope, constraints, and acceptance criteria.
- Ground decisions in repository evidence.
- Run relevant checks and report exact outcomes.
- Record unresolved assumptions and risks.

## Safety
Do not generalize from tiny or cherry-picked samples. Avoid production data and real secrets.

## Completion report
State scope, files inspected or changed, evidence, checks run, outcomes, remaining risks, and approvals required. Never fabricate tool output or test results. Preserve user work and prefer minimal, reversible changes.

## Provenance
Original NOVA SKILLS workflow informed by broad topics in Claude Code Ultimate Guide; not a copied chapter or bundled integration.
