# Lightweight Python Agent Template
Lean scaffold for agentic Python projects with linting, typing, layered tests, and automation-friendly user flow docs ready to run.

## Quick Start
1. Clone this template or fork it to create your project workspace.
2. Run `.github/prompts/git-init.prompt.md` to detach from the template history and prime the README.
3. Run `.github/prompts/make-specs.prompt.md` to capture `specification.md`.
4. Run `.github/prompts/make-todo.prompt.md` to seed the backlog.
5. Resume work with `.github/prompts/continue-development.prompt.md` and follow the loop below; when code lands, run `./scripts/run_tests.sh` (or the individual `flake8`, `mypy`, `pytest` commands) before closing a phase.

> Default package path is `src`. Export `SOURCE_DIR=your_module` and update `src/` if you pick a different name.

**E2E Test Configuration** (for web apps):
- Set `E2E_SERVER_COMMAND` to customize server startup (default: uvicorn)
- Set `E2E_SERVER_DISABLED=true` for non-web projects or when tests manage their own server

## Workflow Overview
1. `.github/prompts/git-init.prompt.md` — initialize git and capture the starter README when bootstrapping a fresh clone.
2. `.github/prompts/make-specs.prompt.md` — align on scope and produce `specification.md`.
3. `.github/prompts/make-todo.prompt.md` — translate the spec into a phase-ordered `TODO.md` backlog.
4. `.github/prompts/configure-tooling.prompt.md` *(optional)* — swap linters, test runners, or typing tools before deep work begins.
5. `.github/prompts/continue-development.prompt.md` — pull the next TODO item and deliver it using `.github/instructions/development.instructions.md`.
6. `.github/prompts/architecture-audit.prompt.md` — spot-check major structural changes against `docs/architecture.md` before review.
7. `.github/prompts/close-phase.prompt.md` — run tests, update docs, and commit when a milestone wraps.

See `docs/prompt_index.md` for detailed prompts and triggers.

## User Flow Scaffolding
- Start with `docs/user_flows/UF-000-template.md` when defining project-specific journeys.
- Log each new flow in `docs/user_flows/index.md` using the `ID | Name | Path | Summary | Status` format.
- Downstream automation can reference the index to decide when to create or update end-to-end tests.

## Architecture Guardrails
- Follow `docs/architecture.md` to keep modules small, cohesive, and testable.
- Keep boundary layers (HTTP/CLI/UI) thin and delegate to services/utilities.
- Prefer pure functions and explicit contracts so logic can be exercised in isolation.
- Flake8 (via `max-complexity=10`) fails builds when functions grow too complex—tune via `.github/prompts/configure-tooling.prompt.md`.
- Run `.github/prompts/architecture-audit.prompt.md` when you need a focused review of modularity decisions.

## ML Project Jumpstart
1. Run `.github/prompts/ml-eda.prompt.md` to capture the EDA plan; it adds checks, charts, and follow-ups into `TODO.md`.
2. Use `.github/prompts/continue-development.prompt.md` to work through the new TODO items with the standard development loop.
3. When modeling is next, run `.github/prompts/ml-training.prompt.md` to outline baselines, splits, and tracking—again syncing actions into `TODO.md`.
4. Continue cycling via `.github/prompts/continue-development.prompt.md` and close out with `.github/prompts/close-phase.prompt.md` once the milestone lands.

## Repo Glance
```
.
├── .github/
│   ├── instructions/      # Development + testing guardrails
│   └── prompts/           # Workflow automation prompts
├── docs/
│   └── user_flows/
│       ├── UF-000-template.md
│       └── index.md       # ID/Name/Path/Summary table for downstream flows
├── scripts/
│   ├── run_e2e_tests.sh
│   └── run_tests.sh
├── src/
├── tests/
│   ├── integration/
│   ├── lint/
│   └── unit/
├── memory.md
├── mypy.ini
└── pytest.ini
```

## References
- Development workflow: `.github/instructions/development.instructions.md`
- Testing workflow: `.github/instructions/testing.instructions.md`
- Prompt library: `.github/prompts/`
- Prompt index: `docs/prompt_index.md`
- User flows: `docs/user_flows/`