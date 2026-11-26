---
name: project-instructions-engineering
description: Write concise, durable project instructions for coding agents.
---

# Project Instructions Engineering

## Purpose
Write concise, durable project instructions for coding agents.

## Workflow
1. Document architecture entry points, versions, verified build/test commands, conventions, generated-file rules, migration policy, and security requirements.
2. Separate stable rules from task context.
3. Resolve instruction precedence.
4. Remove stale duplication.
5. Validate instructions against a real task and update them when architecture changes.

## Deliverables
- Project instruction file
- command verification table
- change log.

## Verification
- Confirm scope, constraints, and acceptance criteria.
- Ground decisions in repository evidence.
- Run relevant checks and report exact outcomes.
- Record unresolved assumptions and risks.

## Safety
Never store secrets or personal data in project instructions.

## Completion report
State scope, files inspected or changed, evidence, checks run, outcomes, remaining risks, and approvals required. Never fabricate tool output or test results. Preserve user work and prefer minimal, reversible changes.

## Provenance
Original NOVA SKILLS workflow informed by broad topics in Claude Code Ultimate Guide; not a copied chapter or bundled integration.
