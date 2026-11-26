---
name: handoff
description: Create a portable, task-focused handoff document so another agent or session can continue work without re-reading the full conversation.
argument-hint: "What should the next session focus on?"
disable-model-invocation: true
---

# Handoff

Create a concise, portable Markdown handoff for a different agent, session, harness, repository, directory, colleague, or parallel side task. This skill is deliberately user-invoked: do not trigger it automatically. Use it when work must cross a boundary that the current conversation or session context cannot cross.

## When to use it

Use a handoff when at least one of these is true:

- The work is moving to a different model host, agent harness, or tool environment.
- The next agent will work in another repository or directory.
- A colleague needs a self-contained brief.
- A side investigation will run in parallel while the current session remains active.
- The current session is ending and a portable continuation file is explicitly requested.

Do not use a handoff merely to continue the same task in the same environment. Prefer the host's context-compaction or continuation mechanism when available. Do not claim that a handoff is equivalent to a native fork, session clone, or context compaction.

## Inputs and focus

1. If the user supplies an argument, treat it as the next session's objective and tailor the handoff around it.
2. Otherwise infer the immediate continuation goal from the active conversation.
3. Preserve the user's actual intent, constraints, decisions, environment, current progress, blockers, and next actions.
4. Include only context that helps the receiving agent act. Avoid transcript-style summaries and unrelated history.
5. If the destination or purpose is unclear and materially affects the handoff, ask one concise clarification before writing.

## Workflow

1. Review the current conversation and any relevant artifacts that are available to you.
2. Identify the live task state:
   - objective and expected outcome;
   - work completed and verified;
   - work remaining, in priority order;
   - decisions and constraints that must not be changed;
   - current environment, relevant paths, versions, and tool limitations;
   - blockers, risks, dependencies, and pending user approvals.
3. Separate verified facts from assumptions, proposals, and unverified reports. Label uncertainty explicitly; never turn an assumption into a completed fact.
4. Identify existing durable artifacts such as specifications, plans, architecture decisions, issues, commits, diffs, and test reports.
5. Reference those artifacts by concise path or stable identifier instead of copying their contents. Include a URL only when it is needed and already known.
6. Suggest only the skills that are genuinely useful for the receiving agent's next task. Do not invent skill names; distinguish installed/available skills from suggestions that need discovery.
7. Redact secrets and sensitive personal information before writing. Never include API keys, access tokens, passwords, private keys, session cookies, recovery codes, or unnecessary personal identifiers. Replace them with clear placeholders such as [REDACTED].
8. Choose a temporary directory appropriate to the operating system:
   - Unix-like systems: use the configured temporary directory (for example, TMPDIR) and fall back to /tmp.
   - Windows: use the configured temporary directory (for example, TEMP).
   - If the runtime exposes a dedicated temporary-file API, prefer it.
9. Create a uniquely named Markdown file in that temporary directory, not in the project workspace. Avoid overwriting an existing file. If the environment cannot create files or cannot identify a safe temporary location, explain the limitation and provide the handoff content in the response rather than claiming a file was created.
10. Read the completed file back when possible and verify that it is readable, focused, and free of secrets.
11. Report the exact resulting path and explain that temporary files may be cleared by the operating system or runtime. If the handoff must survive longer, ask the user to move it to durable storage.

## Required document structure

Use this structure, omitting sections that genuinely do not apply:

# Handoff: [short task title]

## Next-session objective
One or two sentences describing what the receiving agent must accomplish.

## Current state
A compact account of what is in progress and why.

## Verified progress
Only completed work supported by available evidence. Include relevant test or validation outcomes.

## Decisions and constraints
Important user requirements, accepted choices, compatibility constraints, and safety boundaries.

## Environment
Relevant operating system, runtime, repository/directory, versions, and available tools. Omit unknown details rather than guessing.

## Open work
Prioritized, actionable next steps.

## Blockers and risks
Unresolved failures, dependencies, uncertain claims, and approvals required.

## Existing artifacts
Paths or stable identifiers for durable documents, plans, issues, commits, diffs, and reports. Do not duplicate their contents.

## Suggested skills
A short list of relevant skills for the next agent, with a one-line reason for each. If none are clearly relevant, state that no additional skill is required.

## Quality checks

Before handing off, verify:

- A new agent can understand the task without the original conversation.
- The objective is tailored to the stated next-session focus.
- Completed work is distinguishable from pending work.
- Claims are supported or clearly marked as uncertain.
- Durable artifacts are referenced rather than duplicated.
- The document is materially shorter than the source conversation.
- No secrets or unnecessary personal data remain.
- The file exists at the reported path and can be read, when file access is available.
- The original session remains untouched; a handoff creates a copy of context, it does not end or reset the current session.

## Portability and failure handling

Use plain Markdown and ordinary filesystem operations supported by the host. Do not assume a particular vendor's Skill tool, shell, operating system, or temporary-directory variable exists. Adapt to available capabilities and state limitations plainly.

If the next agent cannot access a referenced artifact, mark it as an access dependency instead of copying large amounts of content into the handoff. Never fabricate paths, commits, test results, tool access, or completion status.

A handoff is a transport document, not permanent project memory. Once the work is complete, durable decisions belong in the appropriate project documentation rather than in an old handoff.
