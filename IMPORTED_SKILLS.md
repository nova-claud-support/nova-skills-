# Imported Skills

Thirty selected engineering, software delivery, AI, data, and interface skills have been added to NOVA SKILLS. External repository URLs and source hyperlinks have intentionally been omitted from the imported skill files.

- senior-architect
- senior-backend
- senior-frontend
- senior-fullstack
- code-reviewer
- tdd-guide
- api-design-reviewer
- api-test-suite-builder
- database-designer
- dependency-auditor
- ci-cd-pipeline-builder
- performance-profiler
- browser-automation
- migration-architect
- mobile-release
- i18n-localization
- codebase-onboarding
- commit-craft
- focused-fix
- tech-debt-tracker
- design-qa
- landing-page-generator
- ui-design-system
- saas-scaffolder
- spec-to-repo
- senior-data-engineer
- senior-ml-engineer
- senior-prompt-engineer
- senior-computer-vision
- skill-tester

The imported content is MIT-licensed. The required copyright and license text is retained in `THIRD_PARTY_LICENSES/CLAUDE_SKILLS_MIT.txt`. Some skill packages referenced optional scripts, assets, or reference files; those files were not imported in that batch. The individual skill files include a note preventing agents from assuming those optional files exist.

## Additional independently authored workflow skills

Five new skills extend NOVA SKILLS with deeper engineering workflows:

- analysis-performance-optimization
- release-notes-engineering
- ci-test-audit
- mcp-tool-contract-design
- authorized-app-reverse-analysis

These skills include operational steps, evidence requirements, validation criteria, deliverable formats, and safety boundaries. Application analysis is limited to software the user owns or is explicitly authorized to examine.


## Skill development and frontend practice

Four independently authored skills have been added to expand learning workflows, HTML practice, and skill-library quality:

- html-dom-practice
- frontend-learning-path
- skill-quality-evaluator
- skill-improvement-cycle

These files contain original procedures, practical exercises, evaluation criteria, and validation checklists. No source directory or external reference links are included.

## Agent-skill reliability and governance

Four independently authored skills extend the library's agent workflow, evaluation, and security practices:

- agent-handoff-continuity
- agent-skill-benchmarking
- skill-corpus-curation
- skill-security-review

These skills provide repeatable handoff procedures, benchmark design, corpus maintenance, and defensive package review. They use original instructions and do not embed external source links.

## Agent skills expansion

Seven independently authored skills extend agent planning, tool orchestration, memory hygiene, recovery, structured outputs, observability, and human oversight:

- agent-task-decomposition
- agent-tool-selection
- agent-memory-management
- agent-recovery-replanning
- agent-output-contracts
- agent-observability-tracing
- agent-human-approval-gates

Each skill defines activation conditions, a repeatable workflow, operational guardrails, and verifiable completion criteria. The files contain original instructions without external source links.

## Cross-model and runtime portability

Seven new resources make the library usable beyond a single coding assistant or model vendor:

- cross-model-skill-portability
- model-agnostic-prompt-design
- agent-capability-adaptation
- runtime-compatibility-testing
- coding-agent-workflow
- context-file-engineering
- PORTABILITY.md and SKILL_COMPATIBILITY.md

The canonical skills use portable Markdown instructions, capability-based tool descriptions, and fallbacks for unavailable tools. Native discovery and direct execution remain dependent on each host's supported features and permissions. The same skill content can be supplied as ordinary context when a host does not support automatic skill loading.

## Skill discovery and catalog management

Four new skills add a complete discovery workflow:

- skill-discovery
- skill-registry-aggregation
- skill-relevance-ranking
- skill-installation-planning

The accompanying SKILL_DISCOVERY.md defines the library-wide discovery lifecycle: search accessible collections, inspect actual instructions, assess relevance and safety, deduplicate, rank candidates, and prepare installation only after approval. These capabilities are model-neutral and adapt to the tools and permissions available in each host.

## Portable agent handoff

One additional standalone skill supports controlled transfer of in-progress work between sessions, models, tools, repositories, collaborators, and parallel agents:

- handoff

The handoff workflow creates a concise temporary Markdown brief, distinguishes verified facts from assumptions, references durable artifacts without duplicating them, suggests relevant next-step skills, and redacts secrets. It is manually invoked and adapts to the filesystem and capabilities available in each host.

## Production engineering agent skills

A production-oriented engineering workflow pack has been added. It includes 25 additional skills; the existing `context-engineering` skill was already present and has been extended with cross-model guidance.

- accessibility-engineering
- api-and-interface-design
- browser-testing-with-devtools
- ci-cd-and-automation
- code-review-and-quality
- code-simplification
- constraint-driven-development
- debugging-and-error-recovery
- deprecation-and-migration
- documentation-and-adrs
- doubt-driven-development
- frontend-ui-engineering
- git-workflow-and-versioning
- idea-refine
- incremental-implementation
- interview-me
- observability-and-instrumentation
- performance-optimization
- planning-and-task-breakdown
- security-and-hardening
- shipping-and-launch
- source-driven-development
- spec-driven-development
- test-driven-development
- using-agent-skills

Five specialist personas were added under `agents/`, with shared engineering checklists under `references/`. The required MIT license is retained in the repository root. External hyperlinks were removed from the imported skill, persona, and reference text.

## Universal model compatibility

`CROSS_MODEL_COMPATIBILITY.md` defines the portability contract, while `AGENT_SKILLS_GUIDE.md` explains native and manual use. The skills use plain Markdown and capability-based fallbacks: any model that can read and follow Markdown instructions can use them. Automatic discovery, slash commands, filesystem access, browser automation, and agent delegation still depend on the host platform's actual support.


## Google product and technology skill pack

Imported 226 Google skill instruction files under `skills/google/`, preserving their category and package paths. The collection covers Google Cloud infrastructure, AI and Gemini APIs, agent development, databases and analytics, developer tooling, identity, Android-adjacent platform tooling, advertising integrations, and supporting plugin skills. The full path catalog is maintained in `GOOGLE_SKILLS_INDEX.md`.

The imported Markdown files have been adapted for model portability: external hyperlinks were removed from skill text, host-specific tool assumptions are called out, and execution safeguards require capability checks, authorization, approval for consequential operations, and evidence-based completion. The original Apache 2.0 license is retained in `THIRD_PARTY_LICENSES/GOOGLE_SKILLS_APACHE_2.0.txt`.


## Import scope and companion files

The Google pack adds 226 `SKILL.md` files. Companion references, scripts, assets, plugin manifests, marketplace configuration, and Git submodule contents were not included in this import. Consult `GOOGLE_SKILLS_IMPORT_NOTES.md` before assuming an optional companion file or runtime integration is present.


## ECC engineering system import

Added 28 portable skills: `accessibility`, `agent-architecture-audit`, `agent-eval`, `agent-harness-construction`, `agent-introspection-debugging`, `agent-security-hardening`, `agent-self-evaluation`, `agentic-engineering`, `api-design`, `architecture-decision-records`, `backend-patterns`, `coding-standards`, `change-impact`, `e2e-testing`, `docs-governance`, `frontend-patterns`, `git-workflow`, `docker-patterns`, `database-migrations`, `react-patterns`, `python-patterns`, `python-testing`, `security-review`, `security-scan`, `mcp-server-patterns`, `tdd-workflow`, `verification-loop`, `android-clean-architecture`. The workflows cover agent engineering, architecture, backend and frontend development, Android, testing, documentation, Git, containers, databases, MCP, accessibility, and defensive security. Tool-specific steps were generalized for cross-model use. Security workflows are restricted to authorized defensive assessment. Platform-specific hooks, slash commands, and runtime integrations are not assumed to work universally.
