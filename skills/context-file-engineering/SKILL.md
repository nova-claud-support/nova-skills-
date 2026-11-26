---
name: context-file-engineering
description: Create concise, portable repository instruction files that help different AI models understand project architecture, conventions, workflows, and safety requirements. Use when setting up or maintaining AGENTS.md or equivalent project guidance.
---

# Context File Engineering

## Objective
Create durable project guidance understood by multiple models and coding-agent hosts.

## Workflow
1. Identify actual architecture, languages, build system, test commands, and conventions.
2. Separate stable project facts from temporary task notes.
3. Use plain Markdown headings and direct instructions.
4. Document critical paths, generated files, dependency rules, test commands, and security requirements.
5. State tool capabilities as requirements, not assumptions.
6. Define instruction precedence when multiple context files exist.
7. Avoid vendor-specific syntax in the canonical file.
8. Keep host-specific adapters short and refer to canonical guidance where supported.
9. Validate the instructions with a fresh session or second agent performing a small task.
10. Update guidance when verified project behavior changes.

## Content checklist
Project purpose and architecture; important directories; supported versions; setup/build/lint/test commands; style and dependency policy; security requirements; generated-file rules; review expectations.

## Guardrails
- Never store credentials, personal data, or private tokens.
- Do not invent commands or architecture details.
- Avoid duplicating entire documentation pages.
- Keep canonical instructions independent of one vendor's proprietary features.

## Verification
- Instructions match the repository.
- Commands are verified or marked unverified.
- A model without vendor-specific features can follow the guidance.
- Host-specific limitations are documented separately.
