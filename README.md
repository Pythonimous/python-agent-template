# Lightweight Python Agent Template

A lean scaffold for agentic Python projects with linting, typing, and layered tests ready to run.

## Overview

This template provides a minimal but complete foundation for building Python-based AI agents and similar projects. It includes:

- **Source structure**: Clean `src/` package layout
- **Testing framework**: Unit, integration, and end-to-end test layers with pytest
- **Code quality**: flake8 linting and mypy type checking configured
- **Development workflow**: Clear instructions and automation scripts
- **Extensible design**: Ready for customization while maintaining best practices

## Setup

1. **Install dependencies**:
   ```bash
   pip install -r requirements.txt   # or use your preferred package manager
   ```

2. **Verify installation**:
   ```bash
   flake8
   mypy .
   pytest
   ```

3. **Optional automation**:
   ```bash
   ./scripts/run_tests.sh        # Run full test suite
   ./scripts/run_e2e_tests.sh    # Run end-to-end tests
   ```

> **Note**: Default package path is `src/`. Export `SOURCE_DIR=your_module` and update the `src/` directory if you choose a different module name.

## Test Commands

- **Linting**: `flake8` or `pytest -m lint`
- **Type checking**: `mypy .`
- **Unit tests**: `pytest -m unit`
- **Integration tests**: `pytest -m integration`
- **End-to-end tests**: `pytest -m e2e`
- **Full suite**: `pytest` or `./scripts/run_tests.sh`

## Project Structure

```
.
├── .github/
│   ├── instructions/          # Development and testing guidelines
│   └── prompts/              # Automation prompts for project setup
├── scripts/
│   ├── run_e2e_tests.sh      # End-to-end test runner
│   └── run_tests.sh          # Full test suite runner
├── src/                      # Main package source code
├── tests/
│   ├── integration/          # Integration test layer
│   ├── lint/                 # Linting tests
│   └── unit/                 # Unit test layer
├── memory.md                 # Project context and decisions
├── mypy.ini                  # Type checker configuration
├── pytest.ini               # Test framework configuration
└── README.md                 # This file
```

## Current Status

- ✅ Git repository initialized
- ✅ Project structure established
- ✅ Testing framework configured
- ✅ Code quality tools ready
- 🔄 Ready for project-specific development

## Next Steps

1. **Define specifications**: Run `.github/prompts/make-specs.prompt.md` to generate `specification.md`
2. **Create task list**: Run `.github/prompts/make-todo.prompt.md` to generate `TODO.md`
3. **Start development**: Follow the workflow in `.github/instructions/development.instructions.md`

## References

- **Development workflow**: `.github/instructions/development.instructions.md`
- **Testing guidelines**: `.github/instructions/testing.instructions.md`
- **Prompt library**: `.github/prompts/`

---

*Generated on October 14, 2025*