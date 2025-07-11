---
description: Quick status check of git, commits, workflows, and build
allowed-tools:
  - bash
  - read
  - edit
  - grep
  - glob
  - task
---

Please perform a quick status check:

**Output Format**: Use clear section headers and timestamps for each check.

**Tool Validation**: First verify that required tools are installed (git, gh, uv) and the project is in a valid git repository.

1. **Git and workflow status (parallel)**: Execute `git status`, `git log --oneline -3`, and `gh run list --limit=3` in parallel to check current state
2. **Package status**: Check if package builds successfully with `uv build`

**Error Handling**: If any command fails, attempt to diagnose and fix the issue. If unable to fix, report the specific error and suggest potential solutions.

Provide a concise summary of the project's current state.