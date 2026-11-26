# Skill Compatibility Policy

NOVA SKILLS is a cross-model skill library, not a Claude Code-only package.

## What cross-model means
Canonical skill files use plain Markdown and portable metadata. Any model that can read the instructions can attempt to follow them. Automatic discovery and direct actions depend on the host application, its skill loader, available tools, and permissions.

## Supported usage modes
- Native skill loader: install the folder in the host's supported skill directory.
- Project context: include the skill instructions in project-level context where supported.
- Manual context: provide the SKILL.md content to the model as part of the task.

## Compatibility expectations
The library is designed for use with GPT, Claude, Gemini, Llama, Qwen, DeepSeek, and other model families through compatible host applications. This is a design target, not a claim that every model or host has been individually tested or offers identical behavior.

## Portable core rules
- Standard Markdown and minimal standard YAML frontmatter.
- No mandatory vendor-specific slash commands, hooks, agents, or runtime variables.
- Tool-neutral capability descriptions with explicit fallbacks.
- Observable verification and honest reporting.
- Safety, privacy, and authorization rules independent of a provider.

## Host adapters
A host-specific adapter may document installation paths or map generic capabilities to native tools. Adapters must not fork canonical skill instructions unless a genuine runtime limitation requires it.

See PORTABILITY.md for the authoring and validation standard.

## Cross-model execution standard

The expanded engineering pack is authored as plain Markdown with portable `name` and `description` metadata. Each imported workflow includes a cross-model portability section requiring capability detection, tool substitution, explicit limitations, and evidence-based completion claims.

For the full operational contract, see `CROSS_MODEL_COMPATIBILITY.md`. For user-facing loading and invocation steps, see `AGENT_SKILLS_GUIDE.md`.

The same skill can be supplied as ordinary context to any model that can read Markdown. Automatic discovery, native commands, filesystem access, browser control, and agent delegation remain host-dependent and must not be assumed.


## Google skill pack

The Google product and technology pack is stored under `skills/google/`. Its canonical instructions remain plain Markdown and can be supplied to any model that can read Markdown. Tool invocations, Google Cloud access, API credentials, product availability, and automatic skill discovery depend on the host runtime and explicit permissions. Every imported skill includes cross-model adaptation and execution safeguards; do not assume commands are executable in every environment.
