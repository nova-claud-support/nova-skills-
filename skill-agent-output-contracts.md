---
name: agent-output-contracts
description: Defines and validates machine-readable and human-facing output contracts for AI agents, including schemas, required fields, error states, and compatibility. Use when an agent produces JSON, structured reports, API payloads, or outputs consumed by another system.
---

# Agent Output Contracts

## Objective
Make agent outputs predictable, parseable, and honest about missing or uncertain information.

## Workflow
1. Identify the consumer: person, API, database, downstream agent, or automated pipeline.
2. Choose the simplest suitable format. Use prose for human explanation and a schema-backed format for machine consumption.
3. Define required fields, optional fields, types, allowed values, null semantics, and size limits.
4. Define success, partial-success, and error representations before generation.
5. Separate observed values from estimates, assumptions, and recommendations.
6. Validate generated data against the contract. Check types, required fields, enums, ranges, and cross-field constraints.
7. Escape or encode values using the rules of the target format. Never concatenate untrusted strings into executable syntax.
8. Preserve backward compatibility where consumers may depend on existing fields.
9. Include versioning when the contract changes incompatibly.
10. Provide a concise human-readable explanation alongside structured output when appropriate.

## JSON rules
- Emit valid JSON with double-quoted keys and strings.
- Do not include comments, trailing commas, or Markdown fences when raw JSON is requested.
- Use null only when the contract defines its meaning.
- Do not silently replace missing data with invented defaults.
- Keep errors machine-readable with a stable code and safe message.

## Guardrails
- Do not claim schema validation unless a validator or equivalent check ran.
- Do not expose internal reasoning, credentials, or private system data in output fields.
- Do not put executable code in data fields unless explicitly required and safely handled.

## Verification
- Output parses in the target format.
- All required fields and constraints pass.
- Unknown values remain distinguishable from known values.
- Consumer compatibility is considered and documented.
