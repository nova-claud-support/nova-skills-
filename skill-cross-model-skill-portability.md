---
name: cross-model-skill-portability
description: Design, convert, and audit reusable agent skills so the same workflow can be understood across different AI models and host applications. Use when creating a skill, importing a vendor-specific skill, or preparing a library for multiple runtimes.
---

# Cross-Model Skill Portability

## Objective
Produce one canonical skill that is understandable across models and can be adapted to different host runtimes without vendor-specific assumptions.

## Workflow
1. Identify the task outcome and separate it from the original platform's invocation syntax.
2. Extract reusable reasoning steps, constraints, examples, and acceptance criteria.
3. Remove vendor-specific frontmatter, slash commands, hook syntax, proprietary context variables, and hard-coded tool names unless isolated as optional adapters.
4. Use standard YAML frontmatter with name and description; add other portable fields only when necessary.
5. Express operations as capabilities: read, search, edit, execute, validate, or communicate.
6. For each required capability, provide a preferred method and fallback.
7. Replace assumptions about hidden model behavior with explicit instructions and observable decision criteria.
8. Avoid provider-specific prompt formats, token syntax, or private APIs.
9. Define verification using observable artifacts, tests, or user-confirmable evidence.
10. Test the skill when natively loaded and when supplied as ordinary Markdown context.

## Compatibility labels
- Portable instructions: the model can follow supplied text.
- Native discovery: the host automatically finds the skill.
- Tool-enabled: the host exposes operations required by the workflow.

Never conflate these levels.

## Guardrails
- Do not promise identical performance across models.
- Do not assume every model can call tools or modify files.
- Do not fabricate results when tools are unavailable.
- Preserve authorization, privacy, and approval requirements during conversion.

## Deliverables
A canonical SKILL.md, required capabilities and fallbacks, compatibility notes, and portability test evidence.

## Verification
- No required vendor-specific syntax remains in the portable core.
- The skill works without proprietary runtime context.
- Missing tools trigger safe fallbacks.
- Acceptance criteria remain consistent across tested runtimes.
