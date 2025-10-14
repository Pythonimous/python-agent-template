---
applyTo: "**"
---
# Development Loop

- Frame the smallest useful change before touching code.
- Call out scope creep or overengineering as soon as it appears and wait for approval before expanding the task.
- Write or update the tests that prove the change.
- Implement just enough code to satisfy the tests.
- Run the specific `pytest` slice for the area you touched.
- Spot-check style with `flake8` when rapid feedback helps.
- Run `mypy .` and resolve every type error.
- Run `pytest -m lint` to enforce the shared lint gate.
- Review docs/user_flows/index.md for affected journeys; update or add UF files when scope changes.
- Capture durable context in `memory.md` as you go.
- When adding a flow, log the identifier in the index and plan matching end-to-end coverage.
- When the work is stable, execute `.github/prompts/close-phase.prompt.md`.
- Repeat the loop until the feature is ready to hand off.
