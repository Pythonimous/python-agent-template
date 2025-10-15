---
mode: 'agent'
description: 'Initialize git and prepare project README.'
---

Assumptions:
- This scaffold might have been cloned or forked already, so a `.git/` directory and remotes may exist. Confirm the repository points to the right origin before reinitializing.

Steps:
1. Confirm project name and key goals if unclear.
2. If `.git/` exists, inspect `git status` and `git remote -v`; delete or detach the history only after saving anything you need.
3. Run `git init --initial-branch main` (or `git init`) in the repository root once the workspace is clean.
4. Create or update `README.md` with overview, setup steps, test commands, and current status.
5. Stage the initial files and commit with a descriptive message.
