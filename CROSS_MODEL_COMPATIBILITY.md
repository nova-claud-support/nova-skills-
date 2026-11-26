# Cross-Model Compatibility

## Purpose

NOVA SKILLS uses a portable instruction format so the same engineering workflows can be used with different AI models and coding-agent products. The canonical skill format is plain UTF-8 Markdown with a `SKILL.md` entry point and optional Markdown references.

## Compatibility contract

A model or host can use a skill when it can:

1. Read the skill's Markdown instructions.
2. Interpret the task triggers and follow the workflow.
3. Access the relevant project context supplied by the user or host.
4. Produce the required output and evidence, or clearly state what it cannot verify.

No skill may assume a vendor-specific command, hidden system prompt, proprietary API, special slash command, MCP server, shell, filesystem, browser, or autonomous agent is available unless the current host explicitly exposes it.

## Capability adaptation

Before execution, the agent must:

- Identify the capabilities actually available in the current session.
- Map each required operation to a supported tool or manual alternative.
- Avoid invoking tool names copied from another platform.
- Ask for missing files or permissions instead of pretending to have access.
- Preserve the workflow's intent, quality gates, and acceptance criteria when substituting tools.
- Mark unavailable checks as blocked or not verified; never report them as passed.
- Obtain user approval before external, destructive, costly, or irreversible actions.

## Three portability layers

- **Portable instructions:** Markdown workflow, decision rules, checklists, output contracts, and verification criteria. These are model-neutral.
- **Native discovery:** Automatic skill indexing, slash commands, plugin manifests, and agent routing. These depend on each host's supported conventions.
- **Tool execution:** File access, terminal commands, browser automation, APIs, MCP, and multi-agent delegation. These depend on actual permissions and integrations.

A skill being portable does not mean every host automatically discovers it or can execute every step.

## Generic invocation

When a host has no native skill loader, provide the relevant `SKILL.md` content as task context and ask the model to follow it. Include referenced checklist files when the skill names them. Keep the project-specific instructions and the skill workflow separate.

## Model-neutral output requirements

All agents should:

- State assumptions and unknowns.
- Distinguish inspected evidence from inference.
- Keep secrets out of outputs and logs.
- Explain tool limitations and substitutions.
- Provide reproducible verification steps.
- Avoid claiming a command, test, deployment, or file operation succeeded without confirmation.

## Compatibility testing

Test a skill on each target host using the same representative task. Compare:

- Correct trigger selection.
- Workflow adherence.
- Tool adaptation.
- Safety and approval handling.
- Verification quality.
- Output completeness.
- Honest reporting of unavailable capabilities.

Record host-specific setup separately; do not contaminate the portable skill body with platform-only instructions.

## Support statement

NOVA SKILLS is designed for any AI model or agent that can read and follow Markdown instructions. Native installation, automatic activation, tool use, and identical behavior cannot be guaranteed across every product or model. Those features require explicit host support.
