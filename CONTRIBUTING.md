# Contributing to MCP-Use

Thank you for your interest in contributing to MCP-Use! This document provides guidelines and instructions for contributing to this project.

## Table of Contents

- [Contributing to MCP-Use](#contributing-to-mcp-use)
  - [Table of Contents](#table-of-contents)
  - [Getting Started](#getting-started)
    - [Development Environment](#development-environment)
    - [Installation from Source](#installation-from-source)
  - [Development Workflow](#development-workflow)
    - [Branching Strategy](#branching-strategy)
    - [Commit Messages](#commit-messages)
    - [Code Style](#code-style)
    - [Pre-commit Hooks](#pre-commit-hooks)
  - [Testing](#testing)
    - [Running Tests](#running-tests)
    - [Adding Tests](#adding-tests)
  - [Pull Requests](#pull-requests)
    - [Creating a Pull Request](#creating-a-pull-request)
  - [Documentation](#documentation)
    - [Building Documentation](#building-documentation)
  - [Pull Request Process](#pull-request-process)
    - [1. Create a Branch](#1-create-a-branch)
    - [2. Make Your Changes](#2-make-your-changes)
    - [3. Commit Your Changes](#3-commit-your-changes)
    - [4. Push and Create PR](#4-push-and-create-pr)
    - [5. PR Review Process](#5-pr-review-process)
  - [Release Process](#release-process)
    - [Version Numbering](#version-numbering)
    - [Python Releases](#python-releases)
    - [TypeScript Releases](#typescript-releases)
      - [For Main Branch (Stable Releases)](#for-main-branch-stable-releases)
      - [For Canary Branch (Prereleases)](#for-canary-branch-prereleases)
      - [Installing Canary Versions](#installing-canary-versions)
  - [Release Process](#release-process-1)
    - [Version Numbering](#version-numbering-1)
    - [Python Releases](#python-releases-1)
    - [TypeScript Releases](#typescript-releases-1)
      - [For Main Branch (Stable Releases)](#for-main-branch-stable-releases-1)
      - [For Canary Branch (Prereleases)](#for-canary-branch-prereleases-1)
      - [Installing Canary Versions](#installing-canary-versions-1)
  - [Getting Help](#getting-help)

## Getting Started

### Development Environment

MCP-Use requires:
- Python 3.11 or later

### Installation from Source

1. Fork the repository on GitHub.
2. Clone your fork locally:
   ```bash
   git clone https://github.com/YOUR_USERNAME/mcp-use.git
   cd mcp-use
   ```
3. Install the package in development mode:
   ```bash
   pip install -e ".[dev,search,e2b]"
   ```
4. Set up pre-commit hooks:
   ```bash
   pip install pre-commit
   pre-commit install
   ```

## Development Workflow

### Branching Strategy

- `main` branch contains the latest stable code
- Create feature branches from `main` named according to the feature you're implementing: `feature/your-feature-name`
- For bug fixes, use: `fix/bug-description`

### Commit Messages

For now no commit style is enforced, try to keep your commit messages informational.
### Code Style

We use [Ruff](https://github.com/astral-sh/ruff) for code formatting and linting. The configuration is in `ruff.toml`.

Key style guidelines:
- Line length: 100 characters
- Use double quotes for strings
- Follow PEP 8 naming conventions
- Add type hints to function signatures

### Pre-commit Hooks

We use pre-commit hooks to ensure code quality before committing. The configuration is in `.pre-commit-config.yaml`.

The hooks will:
- Format code using Ruff
- Run linting checks
- Check for trailing whitespace and fix it
- Ensure files end with a newline
- Validate YAML files
- Check for large files
- Remove debug statements

## Testing

### Running Tests

Run the test suite with pytest:

```bash
pytest
```

To run specific test categories:

```bash
pytest tests/
```

### Adding Tests

- Add unit tests for new functionality in `tests/unit/`
- For slow or network-dependent tests, mark them with `@pytest.mark.slow` or `@pytest.mark.integration`
- Aim for high test coverage of new code

## Pull Requests

### Creating a Pull Request

1. Ensure your code passes all tests and pre-commit hooks
2. Push your changes to your fork
3. Submit a pull request to the main repository
4. Follow the pull request template

## Documentation

- Update docstrings for new or modified functions, classes, and methods
- Use Google-style docstrings:
  ```python
  def function_name(param1: type, param2: type) -> return_type:
      """Short description.

      Longer description if needed.

      Args:
          param1: Description of param1
          param2: Description of param2

      Returns:
          Description of return value

      Raises:
          ExceptionType: When and why this exception is raised
      """
  ```
- Update README.md for user-facing changes

### Building Documentation

```bash
# Python documentation (if using Sphinx)
cd libraries/python/docs
make html

# TypeScript documentation (if using TypeDoc)
cd libraries/typescript
pnpm docs
```

## Pull Request Process

### 1. Create a Branch

The `main` branch contains the latest stable code. Create feature or fix branches from `main`:

```bash
# Create a feature branch
git checkout -b feature/your-feature-name

# Or a fix branch
git checkout -b fix/bug-description
```

### 2. Make Your Changes

- Write clean, well-documented code
- Follow the coding standards
- Add or update tests
- Update documentation if needed

### 3. Commit Your Changes

Follow conventional commit format (recommended but not strictly enforced):

```bash
# Format: <type>(<scope>): <subject>
git commit -m "feat(python): add new MCP server connection"
git commit -m "fix(typescript): resolve memory leak in agent"
git commit -m "docs: update installation instructions"
```

Types:

- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, etc.)
- `refactor`: Code refactoring
- `test`: Test changes
- `chore`: Build process or auxiliary tool changes

**Note:** Try to keep your commit messages informational and descriptive of the changes made.

### 4. Push and Create PR

Before pushing, ensure:

- Your code passes all tests
- Pre-commit hooks pass (for Python)
- No linting errors remain

```bash
git push origin your-branch-name
```

Then create a Pull Request on GitHub with:

- Clear title and description
- Link to related issues
- Screenshots/recordings for UI changes
- Test results

### 5. PR Review Process

- PRs require at least one approval
- Address all review comments
- Keep PRs focused and atomic
- Update your branch with main if needed

## Release Process

### Version Numbering

We follow [Semantic Versioning](https://semver.org/):

- MAJOR.MINOR.PATCH (e.g., 2.1.3)
- MAJOR: Breaking changes
- MINOR: New features (backward compatible)
- PATCH: Bug fixes (backward compatible)

### Python Releases

```bash
# Update version in pyproject.toml
# Update CHANGELOG.md
# Create tag
git tag python-v1.2.3
git push origin python-v1.2.3
```

### TypeScript Releases

TypeScript releases use [Changesets](https://github.com/changesets/changesets) for version management:

#### For Main Branch (Stable Releases)

```bash
# 1. Create a changeset describing your changes
cd libraries/typescript
pnpm changeset

# 2. Commit and push your changes with the changeset
git add .
git commit -m "feat: add new feature"
git push

# 3. When merged to main:
#    - CI automatically creates/updates a "Version Packages" PR
#    - Review and merge the Version PR to publish stable versions
```

#### For Canary Branch (Prereleases)

```bash
# 1. Create a changeset for your changes
cd libraries/typescript
pnpm changeset

# 2. Push to canary branch
git add .
git commit -m "feat: experimental feature"
git push origin canary

# 3. CI automatically publishes as canary prerelease
#    - Versions: x.y.z-canary.0, x.y.z-canary.1, etc.
#    - Published with "canary" dist tag on npm
```

#### Installing Canary Versions

Users can test canary releases by installing with the canary tag:

```bash
npm install mcp-use@canary
npm install @mcp-use/cli@canary
```
>>>>>>> 1e8af4c (chore: update TypeScript release workflows and documentation (#328))

## Release Process

### Version Numbering

We follow [Semantic Versioning](https://semver.org/):

- MAJOR.MINOR.PATCH (e.g., 2.1.3)
- MAJOR: Breaking changes
- MINOR: New features (backward compatible)
- PATCH: Bug fixes (backward compatible)

### Python Releases

```bash
# Update version in pyproject.toml
# Update CHANGELOG.md
# Create tag
git tag python-v1.2.3
git push origin python-v1.2.3
```

### TypeScript Releases

TypeScript releases use [Changesets](https://github.com/changesets/changesets) for version management:

#### For Main Branch (Stable Releases)

```bash
# 1. Create a changeset describing your changes
cd libraries/typescript
pnpm changeset

# 2. Commit and push your changes with the changeset
git add .
git commit -m "feat: add new feature"
git push

# 3. When merged to main:
#    - CI automatically creates/updates a "Version Packages" PR
#    - Review and merge the Version PR to publish stable versions
```

#### For Canary Branch (Prereleases)

```bash
# 1. Create a changeset for your changes
cd libraries/typescript
pnpm changeset

# 2. Push to canary branch
git add .
git commit -m "feat: experimental feature"
git push origin canary

# 3. CI automatically publishes as canary prerelease
#    - Versions: x.y.z-canary.0, x.y.z-canary.1, etc.
#    - Published with "canary" dist tag on npm
```

#### Installing Canary Versions

Users can test canary releases by installing with the canary tag:

```bash
npm install mcp-use@canary
npm install @mcp-use/cli@canary
```

## Getting Help

If you need help with your contribution:

- Open an issue for discussion
- Reach out to the maintainers
- Check existing code for examples

Thank you for contributing to MCP-Use!
