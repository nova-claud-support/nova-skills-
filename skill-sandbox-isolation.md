---
name: sandbox-isolation
description: Isolate untrusted code and automated development tasks in constrained, disposable environments.
---

# Sandbox Isolation

## Purpose
Isolate untrusted code and automated development tasks in constrained, disposable environments.

## Workflow
1. Choose process, container, or VM isolation by risk.
2. Mount only required paths and keep source read-only when possible.
3. Deny network by default.
4. Use non-root identities, dropped capabilities, and resource limits.
5. Keep credentials outside the sandbox.
6. Inspect artifacts before export and destroy ephemeral environments afterward.

## Deliverables
- Isolation profile
- mount/network policy
- resource-limit tests
- artifact report.

## Verification
- Confirm scope, constraints, and acceptance criteria.
- Ground decisions in repository evidence.
- Run relevant checks and report exact outcomes.
- Record unresolved assumptions and risks.

## Safety
Do not run unknown code on a personal device or production host without suitable isolation and authorization.

## Completion report
State scope, files inspected or changed, evidence, checks run, outcomes, remaining risks, and approvals required. Never fabricate tool output or test results. Preserve user work and prefer minimal, reversible changes.

## Provenance
Original NOVA SKILLS workflow informed by broad topics in Claude Code Ultimate Guide; not a copied chapter or bundled integration.
