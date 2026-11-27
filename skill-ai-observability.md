---
name: ai-observability
description: Instrument AI workflows to diagnose behavior, latency, cost, and failure modes.
---

# Ai Observability

## Purpose
Instrument AI workflows to diagnose behavior, latency, cost, and failure modes.

## Workflow
1. Assign correlation IDs to requests and tool calls.
2. Record provider, model, template version, latency, token usage, retries, and outcomes.
3. Trace retrieval and tools without excessive payload capture.
4. Separate operational logs from security audit events.
5. Redact sensitive data.
6. Define dashboards and validate alerts.

## Deliverables
- Event schema
- redacted trace
- metric definitions
- alert tests.

## Verification
- Confirm scope, constraints, and acceptance criteria.
- Ground decisions in repository evidence.
- Run relevant checks and report exact outcomes.
- Record unresolved assumptions and risks.

## Safety
Do not log credentials, personal data, or private prompts by default.

## Completion report
State scope, files inspected or changed, evidence, checks run, outcomes, remaining risks, and approvals required. Never fabricate tool output or test results. Preserve user work and prefer minimal, reversible changes.

## Provenance
Original NOVA SKILLS workflow informed by broad topics in Claude Code Ultimate Guide; not a copied chapter or bundled integration.
