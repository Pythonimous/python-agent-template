---
applyTo: "**"
---
# Testing Checklist

- Run `flake8` early or rely on `pytest -m lint` for the gate.
- Run `mypy .` and clear every reported issue.
- Use `pytest` for the full suite when confidence is needed.
- Scope to unit work with `pytest -m unit`; keep tests isolated and fast.
- Cover integrations via `pytest -m integration`; mock external services.
- Combine coverage with `pytest -m "unit or integration"` when reviewing.
- Execute `pytest -m e2e` only when end-to-end behavior must be proven.
- Prefer `./scripts/run_tests.sh` for repeatable local runs.
- Launch `./scripts/run_e2e_tests.sh` when browser flows are required.
- Share fixtures through `tests/conftest.py` to avoid duplication.
