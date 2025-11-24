<!--
Sync Impact Report
- Version change: 0.1.0 → 1.0.0 (major – first concrete constitution, replaces template placeholders)
- Modified principles:
	- [template] → Explorative Learning & Safe Experimentation
	- [template] → Modular, Composable Components
	- [template] → Automation-First Workflows
	- [template] → Simple, Readable Codebases
	- [template] → Documentation & Pattern Consistency
- Added sections:
	- Delivery Workflow & Reviews
- Removed sections:
	- Generic placeholder sections [SECTION_2_NAME], [SECTION_3_NAME]
- Templates requiring updates:
	- ✅ .specify/templates/plan-template.md (Constitution Check references updated principles implicitly)
	- ✅ .specify/templates/spec-template.md (no explicit principle references – structurally aligned)
	- ✅ .specify/templates/tasks-template.md (emphasizes independence and incremental delivery consistent with principles)
	- ⚠ No commands templates directory found at .specify/templates/commands – nothing to sync, but create future commands to respect this constitution.
- Deferred TODOs:
	- TODO(RATIFICATION_DATE): Fill with actual initial ratification date once agreed by maintainers.
-->

# Frontier Agents Workshop Constitution

## Core Principles

### I. Explorative Learning & Safe Experimentation

- The project MUST encourage fast, low-cost experimentation for new ideas,
	patterns, and agent behaviors.
- Experiments MUST be isolated (feature branches, sample scripts, or playground
	folders) so failures do not destabilize core examples.
- Every significant experiment (new pattern, tool, or architecture) MUST record
	key learnings in a short markdown note (e.g., `stories.md`, `docs/`, or a
	feature-specific `research.md`).
- Breaking changes in experiments are ALLOWED until promoted into the
	"stable" set of samples or scenarios.

Rationale: This workshop exists to explore frontier agent patterns. Learning is
maximized when experiments are cheap, reversible, and documented.

### II. Modular, Composable Components

- Agent capabilities, tools, and workflows MUST be structured as small,
	composable modules (e.g., separate functions, classes, or files) rather than
	monolithic scripts.
- Shared behaviors (e.g., logging, common MCP client setup, A2A utilities)
	SHOULD live in reusable helpers or libraries rather than being copy-pasted
	across samples.
- Each module MUST have a single, clear responsibility and a stable interface
	(function signature, class API, or simple CLI) to support reuse in new
	experiments.
- New scenarios SHOULD be assembled primarily by recombining existing modules
	before introducing new abstractions.

Rationale: Modular components make it easier to mix, match, and compare agent
patterns without rewriting large amounts of code.

### III. Automation-First Workflows

- Repetitive tasks (environment setup, formatting, linting, running examples,
	tests) SHOULD be automated via scripts (`make`, shell scripts, or Python
	entrypoints) rather than manual step lists only.
- Where feasible, runnable examples MUST be executable with a single clear
	command documented in `README.md` or a scenario-specific quickstart.
- Any non-obvious manual steps (special env vars, external services, or
	credentials) MUST be captured in documentation next to the code that
	requires them.
- CI, pre-commit hooks, or other automation MAY be introduced, but MUST remain
	simple and transparent so workshop participants can understand and modify
	them.

Rationale: Automation reduces friction, supports repeatable learning, and makes
complex scenarios approachable for new contributors.

### IV. Simple, Readable Codebases

- Code MUST prioritize clarity over cleverness; explicit, straightforward
	implementations are preferred to deeply abstract or "smart" solutions.
- Naming (files, functions, variables) MUST be descriptive enough that a new
	reader can understand intent without deep context.
- Control flow in examples SHOULD remain shallow (limited nesting, short
	functions) and favor linear, narrative-style code where possible.
- Dependencies SHOULD be kept minimal and justified by clear learning value;
	avoid introducing heavy frameworks if standard libraries or small utilities
	suffice.

Rationale: This repository is a teaching tool. Simple, readable code best
serves practitioners who are learning agent patterns for the first time.

### V. Documentation & Pattern Consistency

- Every non-trivial example (new scenario, workflow, or server) MUST have
	accompanying documentation: at minimum, a short description and run steps,
	either in the main `README.md` or a local `README.md` / `quickstart.md`.
- When introducing a new pattern (e.g., human-in-the-loop, A2A, MCP tooling),
	the documentation MUST explicitly name it and explain its intent and
	trade-offs.
- Similar problems SHOULD be solved using consistent patterns and structure
	(e.g., similar folder layout, naming conventions, and entrypoints across
	scenarios) unless there is a deliberate reason to diverge.
- Any intentional deviation from existing patterns MUST be called out in
	comments or docs with a short explanation of why the variation exists.

Rationale: Clear documentation and consistent patterns lower cognitive load and
help participants transfer learning from one scenario to another.

## Delivery Workflow & Reviews

- New contributions MUST state which principles they exemplify (e.g., in PR
	descriptions or commit messages).
- Before merging, reviewers MUST verify that new or changed code:
	- Keeps examples runnable with documented commands.
	- Preserves or improves readability and modularity.
	- Adds or updates documentation when behavior or patterns change.
- Experiments that graduate to "canonical" examples (referenced from the root
	`README.md` or workshop materials) MUST be stabilized: interfaces clarified,
	docs updated, and any experimental flags or hacks removed.

Rationale: A lightweight but explicit workflow ensures that the repository
remains approachable while evolving quickly.

## Governance

- This constitution defines non-negotiable expectations for samples, scenarios,
	and supporting tooling in this repository.
- Amendments MUST:
	- Be documented as a version bump in the constitution footer.
	- Include a short Sync Impact Report comment at the top of this file.
	- Be reviewed by at least one maintainer familiar with the agent workshop
		goals.
- Versioning follows semantic rules:
	- MAJOR: Remove or fundamentally redefine a principle or governance rule.
	- MINOR: Add a new principle, section, or materially expand guidance.
	- PATCH: Clarify wording, fix typos, or adjust examples without changing
		meaning.
- All PRs touching core samples, scenarios, or templates SHOULD include a brief
	"Constitution Check" note confirming alignment or explaining intentional
	deviations.

Rationale: Explicit governance keeps the workshop coherent as more patterns and
contributors are added over time.

**Version**: 1.0.0 | **Ratified**: TODO(RATIFICATION_DATE): set by maintainers | **Last Amended**: 2025-11-24
