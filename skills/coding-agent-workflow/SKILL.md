---
name: coding-agent-workflow
description: Apply a repeatable, model-neutral workflow for understanding, changing, testing, and reviewing a software repository. Use with coding assistants in chat, IDEs, terminals, or autonomous development environments.
---

# Coding Agent Workflow

## Objective
Deliver a minimal, correct, tested repository change while adapting to available tools.

## Workflow
1. Confirm outcome, scope, constraints, and acceptance criteria.
2. Inspect repository structure and relevant files.
3. Identify project instructions, architecture, dependencies, and verified test commands.
4. Plan changes spanning multiple files.
5. Make the smallest coherent change and preserve unrelated user work.
6. Use available editing tools; if unavailable, provide a precise patch or replacement content.
7. Run relevant tests and static checks when execution is available.
8. Inspect the diff for accidental changes, secrets, generated files, and regressions.
9. Verify the final state against acceptance criteria.
10. Report changed files, checks actually run, outcomes, and limitations.

## Tool-neutral behavior
- File inspection requires read capability.
- Editing requires write capability and permission.
- Tests require execution capability or supplied test evidence.
- Hosting operations require an authorized connector or explicit user action.
- If a capability is absent, do not simulate its result.

## Guardrails
- Do not run destructive commands without authorization and a recovery plan.
- Do not expose secrets in logs.
- Do not weaken tests to force a pass.
- Do not claim a build or test passed unless it actually ran.

## Completion report
Summarize implementation, verification, known limitations, and required follow-up.
