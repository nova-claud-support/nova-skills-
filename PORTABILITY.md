# NOVA SKILLS Portability Standard

## Goal
NOVA SKILLS is model-agnostic. Skills are authored once as plain Markdown workflows and are not designed exclusively for Claude Code or any single model vendor.

## Compatibility principle
A skill can be used by any AI model or agent runtime that can receive the skill instructions as context and follow the workflow. Native automatic discovery, tool access, file access, and execution depend on the host application; a Markdown skill cannot create capabilities that the host does not provide.

## Three compatibility levels
1. Portable instructions — the model can follow supplied text.
2. Native skill loading — the host automatically discovers the skill.
3. Tool-enabled execution — the host exposes required operations with suitable permissions.

Never describe Level 1 as automatic installation or Level 3 as guaranteed across all hosts.

## Authoring contract
- Use portable frontmatter fields only: name, description, license, compatibility, metadata, and allowed-tools. Prefer name and description.
- Keep names lowercase and hyphenated; the folder name must match name.
- Write instructions for "the agent" or "the model", not a vendor-specific assistant.
- Do not require slash commands, proprietary hooks, subagent APIs, hidden context variables, or vendor-specific frontmatter.
- Describe capabilities by intent (read a file, run a test, inspect a diff), not assumed tool names.
- For each tool-dependent step, state the required capability and a safe fallback.
- Treat terminal commands as optional examples, not universal model abilities.
- Never assume browsing, code execution, file editing, or connected-account access unless the host exposes it.
- Preserve safety, privacy, authorization, and approval requirements across runtimes.

## Tool adaptation pattern
For each operation specify its goal, required capability, preferred method, fallback, and verification method.

## Runtime installation
The canonical source remains skills/<skill-name>/SKILL.md. Copy each skill folder into the discovery directory supported by the target host. Common conventions include .agents/skills, .claude/skills, .cursor/skills, .github/skills, and .gemini/skills. These paths are host-specific, not interchangeable guarantees. Confirm the target application's loading behavior. If native discovery is unavailable, provide SKILL.md as project instructions or task context.

## Model coverage
The same instructions may be used with GPT-family, Claude-family, Gemini-family, Llama-family, Qwen-family, DeepSeek-family, and other models, provided the host can supply the instructions. Quality and tool execution vary; validate each target combination rather than claiming identical behavior.

## Release checklist
- Standard frontmatter only.
- No vendor-specific commands or hidden runtime assumptions.
- Tool requirements and fallbacks are explicit.
- No secrets or personal data in examples.
- Safety and approval gates remain intact.
- Manual-context fallback exists.
- Test native loading and plain-context use.
- Compatibility claims distinguish model capability from host capability.
