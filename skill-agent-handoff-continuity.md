---
name: agent-handoff-continuity
description: Create reliable, compact handoffs between AI-agent sessions or between human and AI collaborators. Use when work may pause, context may be lost, or another agent must continue safely without repeating discovery.
---

# Agent Handoff Continuity

## Objective
Produce a verifiable checkpoint that lets the next worker resume a task without inventing progress or repeating completed work.

## Procedure
1. **Capture the goal:** State the requested outcome, acceptance criteria, and explicit constraints.
2. **Record the current state:** Identify the active branch, relevant files, environment assumptions, and the last confirmed working state. Never include secrets, tokens, private keys, or personal data.
3. **Separate facts from hypotheses:** Label observations as verified, inferred, or unverified. Attach concise evidence such as test names, command outcomes, or file paths.
4. **List completed work:** Describe changes made and checks actually run. Do not mark a task complete merely because code was written.
5. **List open work:** Order remaining tasks by dependency and impact. Include blockers and the exact information needed to resolve them.
6. **Define the next safe action:** Give one small, reversible next step and its expected result.
7. **Preserve rollback context:** Note changed files and how to restore the previous state using the project's normal version-control workflow.

## Handoff format
- Goal and acceptance criteria
- Verified current state
- Changes completed
- Tests and outcomes
- Open questions and blockers
- Next action
- Rollback notes

## Quality gates
- A new agent can identify what is true without relying on conversational guesswork.
- No credentials or sensitive user data are present.
- Every completion claim has evidence.
- Unverified assumptions are clearly labeled.
- The next action is bounded and reversible.

## Boundaries
Do not claim to have run commands, inspected files, or changed remote systems unless that action was actually performed. If context is missing, ask for the smallest necessary clarification instead of fabricating it.
