---
name: lifecycle-hooks-automation
description: Design event-driven automation around development workflows with safe defaults and observable outcomes.
---

# Lifecycle Hooks Automation

## Purpose
Design event-driven automation around development workflows with safe defaults and observable outcomes.

## Workflow
1. Define each event and purpose.
2. Keep hooks deterministic, fast, and idempotent.
3. Validate payloads and paths.
4. Use pre-action gates and post-action reporting.
5. Offload long tasks to explicit job runners.
6. Bound time and output.
7. Test duplicate events, malformed input, timeouts, and permission failures.

## Deliverables
- Event map
- hook contract
- test matrix
- operational notes.

## Verification
- Confirm scope, constraints, and acceptance criteria.
- Ground decisions in repository evidence.
- Run relevant checks and report exact outcomes.
- Record unresolved assumptions and risks.

## Safety
Do not create hidden hooks or exfiltrate source code, secrets, or user data.

## Completion report
State scope, files inspected or changed, evidence, checks run, outcomes, remaining risks, and approvals required. Never fabricate tool output or test results. Preserve user work and prefer minimal, reversible changes.

## Provenance
Original NOVA SKILLS workflow informed by broad topics in Claude Code Ultimate Guide; not a copied chapter or bundled integration.
