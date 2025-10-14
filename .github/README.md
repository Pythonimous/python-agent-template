# Lightweight Python Agent Template
Lean scaffold for agentic Python projects with linting, typing, layered tests, and automation-friendly user flow docs ready to run.

## Quick Start
```bash
pip install -r requirements.txt   # or the project's chosen manager
flake8
mypy .
pytest
# optional:
./scripts/run_tests.sh
./scripts/run_e2e_tests.sh
```

> Default package path is `src`. Export `SOURCE_DIR=your_module` and update `src/` if you pick a different name.

**E2E Test Configuration** (for web apps):
- Set `E2E_SERVER_COMMAND` to customize server startup (default: uvicorn)
- Set `E2E_SERVER_DISABLED=true` for non-web projects or when tests manage their own server

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

## Project Initialization
- Run `.github/prompts/make-specs.prompt.md` to generate `specification.md`.
- Run `.github/prompts/make-todo.prompt.md` to generate `TODO.md`.
- Run `.github/prompts/configure-tooling.prompt.md` to align linting/testing tools with your stack.

## User Flow Scaffolding
- Start with `docs/user_flows/UF-000-template.md` when defining project-specific journeys.
- Log each new flow in `docs/user_flows/index.md` using the `ID | Name | Path | Summary` format.
- Downstream automation can reference the index to decide when to create or update end-to-end tests.

## References
- Development workflow: `.github/instructions/development.instructions.md`
- Testing workflow: `.github/instructions/testing.instructions.md`
- Prompt library: `.github/prompts/`
- User flows: `docs/user_flows/`
