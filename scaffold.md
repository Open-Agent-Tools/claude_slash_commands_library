---
description: Create a new project from templates with full setup
allowed-tools:
  - bash
  - read
  - edit
  - grep
  - glob
  - task
---

Create a new project using the specified template: $ARGUMENTS

**Output Format**: Use clear section headers, timestamps for each step, and progress indicators for setup operations.

**Tool Validation**: First verify that required tools are installed (git, uv, gh) and the target directory is valid.

**Python Project Defaults**: All Python projects use UV for virtual environment management and package installation. Never use pip, pipenv, or conda.

**Template Options**:
- `python-lib` - Python library with pyproject.toml, tests, CI/CD
- `python-cli` - Python CLI application with Click/Typer
- `python-web` - FastAPI web application
- `python-data` - Data science project with Jupyter notebooks
- `node-lib` - Node.js library with TypeScript
- `node-web` - React/Next.js web application
- `rust-lib` - Rust library with Cargo.toml
- `go-cli` - Go CLI application
- `custom` - Interactive template selection

**Project Setup Steps**:

1. **Template Selection**: Determine template from argument or prompt interactively
2. **Directory Creation**: Create project directory with proper naming conventions
3. **Template Scaffolding**: 
   - Clone or copy base template files
   - Replace template variables (project name, author, etc.)
   - Setup proper directory structure
4. **Dependency Management**:
   - For Python: Use `uv init` and `uv add` exclusively for all dependencies
   - For Python: Create virtual environment with `uv venv` and activate with `uv run`
   - For other languages: Install language-specific dependencies
   - Configure package manager files
5. **Git Initialization**:
   - Initialize git repository
   - Create initial commit
   - Setup .gitignore for language/framework
   - Configure git hooks if available
6. **CI/CD Setup**:
   - Create GitHub Actions workflows
   - Setup testing and linting pipelines
   - Configure release automation
7. **Development Environment**:
   - Setup IDE configuration files (.vscode, etc.)
   - Create development scripts
   - Configure debugging setup
8. **Documentation**:
   - Generate README with project info
   - Create CONTRIBUTING.md
   - Setup documentation framework
9. **Testing Framework**:
   - Setup test directory structure
   - Create sample tests
   - Configure test runners
10. **Quality Tools**:
    - Configure linting tools
    - Setup formatters
    - Configure type checking
11. **Final Validation**:
    - For Python: Run `uv run python -m pytest` to test setup
    - For Python: Run `uv build` to verify package builds
    - For other languages: Run initial build/compile
    - Execute basic tests
    - Verify all tools work correctly

**Interactive Prompts**:
- Project name (default: directory name)
- Author name and email
- License type (MIT, Apache, etc.)
- Description
- Python version (for Python projects)
- Additional features (database, API, etc.)

**Template Variables**:
- `{{PROJECT_NAME}}` - Project name
- `{{AUTHOR_NAME}}` - Author name
- `{{AUTHOR_EMAIL}}` - Author email
- `{{DESCRIPTION}}` - Project description
- `{{LICENSE}}` - License type
- `{{YEAR}}` - Current year
- `{{PYTHON_VERSION}}` - Python version

**Error Handling**: If any step fails, attempt to fix the issue automatically. If unable to fix, report the specific error and provide cleanup instructions.

**Post-Setup Instructions**:
- Display next steps for development
- Show available commands (test, build, etc.)
- Provide quick start guide
- Suggest development workflow

The template type provided is: $ARGUMENTS