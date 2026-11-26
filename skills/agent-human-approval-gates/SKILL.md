---
name: agent-human-approval-gates
description: Adds explicit human review gates to agent workflows before consequential, irreversible, privacy-sensitive, or externally visible actions. Use when agents can publish, delete, purchase, send messages, change permissions, or modify important systems.
---

# Agent Human Approval Gates

## Objective
Ensure consequential actions occur only with informed, specific authorization and within the approved scope.

## Workflow
1. Classify each planned action by impact, reversibility, privacy exposure, and external visibility.
2. Mark actions requiring approval before execution. Typical examples include deletion, publication, external messaging, permission changes, and irreversible production changes.
3. Prepare a review summary that states:
   - exact action and target
   - scope and affected records
   - expected outcome
   - material risks
   - reversibility and rollback plan
4. Present a preview or diff whenever the action changes content or configuration.
5. Ask for clear approval tied to that specific action and scope.
6. Treat ambiguous, expired, or unrelated approval as no approval.
7. Re-check the target state immediately before execution to detect intervening changes.
8. Execute only the approved operation. Stop if scope, target, or impact differs from the preview.
9. Verify the result and report what changed, what did not, and any residual risk.
10. For recurring workflows, define approval thresholds and expiry explicitly; do not infer blanket consent.

## Guardrails
- Approval for one action does not authorize adjacent actions.
- Never bypass access controls or platform safeguards.
- Do not bundle low-risk and high-impact operations into one opaque approval.
- If a tool cannot pause for approval, do not invoke it for a gated action.
- Preserve an audit record without retaining unnecessary sensitive content.

## Verification
- Approval is explicit, current, and scoped.
- Preview matches the executed target and operation.
- No unapproved side effects occurred.
- Post-action state is verified and reported.
