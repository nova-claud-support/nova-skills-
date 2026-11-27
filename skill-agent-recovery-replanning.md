---
name: agent-recovery-replanning
description: Diagnoses failed agent steps and safely resumes work using observed state, bounded retries, and explicit recovery plans. Use when a tool call, build, deployment, workflow, or multi-step task fails or returns an ambiguous result.
---

# Agent Recovery and Replanning

## Objective
Recover from failure without compounding damage, duplicating side effects, or claiming success prematurely.

## Workflow
1. Stop the failing sequence. Do not repeat the same action until its side effects are understood.
2. Capture the exact error, failed step, inputs (excluding secrets), timestamp, and last known successful checkpoint.
3. Classify the failure: invalid input, permission, unavailable dependency, transient service, timeout, partial completion, or logic defect.
4. Inspect current state using read-only operations before retrying.
5. Determine whether the operation is idempotent. If not, search for evidence that it already completed.
6. Identify the smallest corrective action. Avoid unrelated refactors during recovery.
7. Set a bounded retry policy for plausibly transient failures. Use backoff only when supported by the execution environment.
8. If the failure is deterministic, correct the cause rather than repeating the request.
9. Resume from the last verified checkpoint. Re-run dependent checks affected by the correction.
10. If recovery remains blocked, preserve diagnostics and report the blocker, impact, and safe next step.

## Recovery matrix
- Permission denied: verify account scope and authorization; do not attempt to bypass controls.
- Invalid argument: compare inputs with the tool contract and correct the specific field.
- Timeout: inspect remote state before repeating a write.
- Partial update: enumerate changed resources and reconcile them one by one.
- Build/test failure: isolate the failing stage and retain the first meaningful error.
- Unknown failure: reduce scope and gather evidence before taking further action.

## Guardrails
- Never hide errors or convert a failed operation into a success message.
- Never retry destructive or financial actions without checking state and authorization.
- Preserve user data; create backups or checkpoints before risky repairs when possible.
- Do not expose secrets in diagnostics.

## Verification
- Root cause or current blocker is evidence-based.
- No duplicate side effects were introduced.
- Recovered state passes relevant tests.
- Final status distinguishes completed, partially completed, and blocked work.
