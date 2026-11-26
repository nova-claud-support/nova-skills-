---
name: agent-task-decomposition
description: Breaks complex user goals into bounded, verifiable work units with dependencies, acceptance criteria, and a safe execution order. Use when a request spans multiple files, tools, systems, or stages, or when an agent needs to plan before acting.
---

# Agent Task Decomposition

## Objective
Convert an outcome-oriented request into the smallest useful set of independently verifiable tasks without losing the user's actual goal.

## Workflow
1. Restate the requested outcome internally; distinguish the desired result from proposed implementation details.
2. Extract constraints: scope, platform, deadline, permissions, budget, compatibility, required format, and explicit exclusions.
3. Identify unknowns that could change correctness or safety. Ask only for a blocking detail; otherwise state a reversible assumption.
4. Divide the work into deliverables with one clear outcome each. Avoid splitting tasks so finely that coordination costs exceed the benefit.
5. Record dependencies as a directed acyclic graph. Detect cycles and resolve them before execution.
6. Give every task:
   - a stable identifier
   - inputs and expected outputs
   - prerequisites
   - acceptance criteria
   - verification method
   - risk and rollback note where applicable
7. Order tasks by dependency, risk reduction, and information value. Prefer a small proof-of-concept before broad changes when uncertainty is high.
8. Execute one bounded unit at a time. Re-plan only when evidence invalidates an assumption or a dependency changes.
9. At completion, verify the integrated outcome against the original request, not merely the individual task checklists.

## Planning rules
- Keep user requirements separate from agent assumptions.
- Do not invent approvals, credentials, or permissions.
- Prefer reversible changes before destructive or externally visible actions.
- Include integration and final verification as explicit tasks.
- If the request is already simple and atomic, do not create an unnecessary plan.

## Output contract
Provide a concise plan containing goal, assumptions, ordered tasks, dependencies, risks, and completion checks. Mark unknowns clearly; never present estimates as confirmed facts.

## Verification
- Every task has a concrete deliverable and pass condition.
- Dependencies are acyclic and ordered.
- Blocking unknowns are resolved or surfaced.
- Final checks cover the user's end-to-end outcome.
