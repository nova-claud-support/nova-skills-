---
name: agent-harness-engineering
description: Design the runtime around an AI coding agent: task contracts, tool adapters, state, policy gates, recovery, and acceptance.
---

# Agent Harness Engineering

## Purpose
Design the runtime around an AI coding agent: task contracts, tool adapters, state, policy gates, recovery, and acceptance.

## Workflow
1. Define objective, scope, constraints, acceptance criteria, and budgets.
2. Separate model, tools, policy gate, state store, runner, and evaluator.
3. Authorize every tool call with least privilege.
4. Persist run IDs, checkpoints, tool results, and terminal status.
5. Bound retries and support cancellation, resume, and rollback.
6. Stop on acceptance, exhausted budget, repeated failure, or required approval.

## Deliverables
- Task contract
- permission matrix
- run-state schema
- recovery tests.

## Verification
- Confirm scope, constraints, and acceptance criteria.
- Ground decisions in repository evidence.
- Run relevant checks and report exact outcomes.
- Record unresolved assumptions and risks.

## Safety
Never grant unrestricted shell, network, credentials, or production access.

## Completion report
State scope, files inspected or changed, evidence, checks run, outcomes, remaining risks, and approvals required. Never fabricate tool output or test results. Preserve user work and prefer minimal, reversible changes.

## Provenance
Original NOVA SKILLS workflow informed by broad topics in Claude Code Ultimate Guide; not a copied chapter or bundled integration.
