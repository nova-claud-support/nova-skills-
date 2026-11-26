# Agent Skills Usage Guide

NOVA SKILLS contains reusable engineering workflows, specialist agent personas, and reference checklists.

## Using a skill with any AI model

1. Choose the relevant folder under `skills/`.
2. Provide its `SKILL.md` content to the model, either through the host's native skill loader or as ordinary task context.
3. Include any referenced checklist from `references/`.
4. Give the model the project files and task details it is allowed to inspect.
5. Ask it to follow the workflow and report evidence for each verification gate.
6. Review the result before accepting changes or approving external actions.

## If the platform supports native skills

Use that platform's documented skill directory or plugin format. Keep the canonical Markdown skill unchanged where possible, and place platform-specific configuration in a separate adapter.

## If the platform does not support native skills

Paste or attach the relevant Markdown files to the conversation. The skill remains usable as instructions, but automatic discovery and direct tool execution may not be available.

## Personas

Files under `agents/` describe specialist review perspectives. They are role prompts, not independent agents by themselves. A host must support agent delegation to run them as separate workers; otherwise, ask the current model to apply the persona as a review mode.

## References

Files under `references/` are shared checklists and supporting material. Preserve the directory relationship when copying skills that refer to these files, or include the referenced checklist alongside the skill.

## Honest capability reporting

Never claim that an integration, command, test, browser action, or deployment ran unless the current host confirms it. If a required capability is unavailable, provide a manual alternative and mark the check as unverified.
