---
name: agent-memory-management
description: Maintains useful, privacy-conscious working memory for agents by separating durable facts from temporary state and recording provenance, confidence, and expiry. Use when an agent must preserve context across sessions or decide what should not be retained.
---

# Agent Memory Management

## Objective
Preserve only information that improves future task performance while preventing stale assumptions, unnecessary personal data retention, and false claims of memory.

## Workflow
1. Identify the memory purpose: continuity, user preference, project state, or reusable technical knowledge.
2. Classify each candidate item:
   - durable and reusable
   - temporary task state
   - sensitive or unnecessary
   - unverified assumption
3. Exclude credentials, authentication tokens, private keys, and unrelated sensitive personal information.
4. Record the source and timestamp or project version for facts that can become stale.
5. Store preferences as preferences, not universal requirements. Preserve explicit exceptions.
6. Separate confirmed facts from inferred details and confidence levels.
7. Add expiry or revalidation conditions to temporary state, versions, and environment details.
8. Before using recalled context, check whether it is relevant to the current request and whether newer evidence supersedes it.
9. When the user corrects a fact, prefer the correction and identify dependent notes that may now be stale.
10. For deletion or forgetting requests, follow the platform's supported memory controls; do not claim deletion without confirmation.

## Memory record format
Use a compact structure:
- Item
- Category
- Source/provenance
- Confidence: confirmed, user-stated, or inferred
- Last verified
- Expiry/revalidation trigger
- Privacy rationale

## Guardrails
- Minimize retention; usefulness alone does not justify storing sensitive data.
- Never fabricate continuity or claim to remember information that is unavailable.
- Do not convert a one-time instruction into a permanent preference without clear intent.
- Do not treat old project state as current without checking.
- Respect user corrections and requests to avoid a topic.

## Verification
- Each retained item has a clear future use.
- Sensitive secrets are excluded.
- Provenance and uncertainty are visible.
- Stale items are revalidated before use.
