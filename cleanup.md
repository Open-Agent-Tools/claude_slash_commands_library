---
description: Run complete code quality checks and fix all issues
allowed-tools:
  - bash
  - read
  - edit
  - grep
  - glob
  - task
---

Please perform a complete code cleanup by following these steps:

**Output Format**: Use clear section headers, timestamps for each step, and progress indicators for long-running operations.

**Tool Validation**: First verify that required tools are installed (uv, ruff, mypy) and the project structure is valid (pyproject.toml exists).

1. **Run ruff linting and formatting (parallel)**: Execute `uv run ruff check . --fix` and `uv run ruff format .` in parallel to automatically fix linting issues and format code
2. **Run mypy type checking**: Execute `uv run mypy .` and fix any type errors found
3. **Review and update**: Check all TODO.md files for recent changes and update them
4. **Commit changes**: Create a detailed commit message summarizing all fixes
5. **Push Commit**: Push to the current branch
6. **Run Claude's compact function**: Execute Claude's compact function to optimize the codebase

**Error Handling**: If any step fails, attempt to fix the issue automatically. If unable to fix, report the specific error details and suggest manual fixes.

Make sure to fix any issues found during each step before proceeding to the next.