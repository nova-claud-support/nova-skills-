---
name: prompt-injection-defense
description: Defend coding agents against instructions embedded in untrusted files, issues, webpages, logs, and tool output.
---

# Prompt Injection Defense

## Purpose
Defend coding agents against instructions embedded in untrusted files, issues, webpages, logs, and tool output.

## Workflow
1. Map untrusted inputs and trust boundaries.
2. Keep system policy separate from retrieved data.
3. Label external content as untrusted.
4. Validate tool schemas, paths, and permissions outside the model.
5. Require approval for external disclosure or destructive actions.
6. Minimize secrets in context and logs.
7. Test benign injection attempts across retrieval and tool channels.

## Deliverables
- Threat model
- trust-boundary map
- tool allowlist
- regression suite.

## Verification
- Confirm scope, constraints, and acceptance criteria.
- Ground decisions in repository evidence.
- Run relevant checks and report exact outcomes.
- Record unresolved assumptions and risks.

## Safety
Defensive design and authorized testing only. Never bypass another system's controls.

## Completion report
State scope, files inspected or changed, evidence, checks run, outcomes, remaining risks, and approvals required. Never fabricate tool output or test results. Preserve user work and prefer minimal, reversible changes.

## Provenance
Original NOVA SKILLS workflow informed by broad topics in Claude Code Ultimate Guide; not a copied chapter or bundled integration.
