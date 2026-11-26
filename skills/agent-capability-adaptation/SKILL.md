---
name: agent-capability-adaptation
description: Adapt an agent workflow to the tools and permissions actually available in its host without changing the user's intended outcome. Use when moving skills between chat models, coding agents, IDEs, or automation platforms.
---

# Agent Capability Adaptation

## Objective
Map a portable workflow onto the current host's real capabilities without fabricating tool use or using unsafe workarounds.

## Workflow
1. Inspect available tool descriptions and permission boundaries.
2. Map capabilities: context input, file read/write, search, code execution, browser, API, and approval handling.
3. Compare workflow requirements with the capability map.
4. Mark each step supported, constrained, or unavailable.
5. Bind supported steps to the narrowest suitable tool.
6. For unavailable steps, ask for an upload or relevant output, provide a patch, or explain the limitation.
7. Preserve acceptance criteria; do not silently lower quality.
8. Check permissions and side effects before writes, publication, deletion, or external communication.
9. Execute only supported operations and inspect actual results.
10. Report completed, partial, and blocked steps separately.

## Capability map
| Capability | Available? | Constraint | Fallback |
|---|---|---|---|
| Read files | Yes/No | Scope and file types | Ask for upload or excerpt |
| Write files | Yes/No | Allowed paths and approvals | Provide a patch |
| Execute code | Yes/No | Language and sandbox | Give reproducible test steps |
| Browse web | Yes/No | Domains and freshness | State limitation |
| Call APIs | Yes/No | Connections and permissions | Provide request template |
| Human approval | Yes/No | Confirmation mechanism | Stop before consequential action |

## Guardrails
- Never claim a tool was used when it was not.
- Never bypass missing permission or safety controls.
- Do not expose credentials while adapting a workflow.
- Reasoning ability does not imply execution capability.

## Verification
- Every operation is supported or has a fallback.
- User intent and constraints remain intact.
- Side effects are authorized and verified.
