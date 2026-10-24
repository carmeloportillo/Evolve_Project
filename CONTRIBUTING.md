# Contributing to Evolve_Project

Thank you for contributing to Evolve_Project!

These guidelines help the team collaborate consistently and maintain
reliable, reproducible Data Science work.

## Getting Started

1. Read the project [README](README.md).
2. Install Python 3.12 and Git.
3. Follow the installation instructions in the README.
4. Activate your virtual environment before running project commands.

## Branching Strategy

Create a separate branch for each task. Use a descriptive name and an
appropriate prefix.

Examples:

- `feature/data-cleaning`
- `feature/model-evaluation`
- `fix/notebook-error`
- `docs/update-readme`
- `test/add-data-validation`

Start from the latest `main` branch when possible:

    git switch main
    git pull origin main
    git switch -c feature/short-description

## Development Guidelines

- Keep changes focused on one task.
- Write readable, maintainable Python code.
- Use clear and descriptive names.
- Avoid committing generated files, virtual environments, credentials,
  confidential information, or private datasets.
- Do not commit changes to unrelated files.

## Dependencies

Install the project dependencies with:

    python -m pip install -r requirements.txt

If a dependency changes, update `requirements.txt` when appropriate and
explain the reason in the Pull Request.

## Testing and Code Quality

Before opening a Pull Request, run the available checks:

    python -m pytest -v
    python -m ruff check src tests

Resolve any failures introduced by your changes before requesting review.

## Commit Messages

Use short, descriptive commit messages written in English.

Examples:

- `Add data validation utilities`
- `Fix missing-value handling`
- `Update project documentation`
- `Add tests for preprocessing`

Commits should follow the repository's commit-signing requirements.

## Pull Request Process

1. Push your branch to GitHub.
2. Open a Pull Request targeting `main`.
3. Explain the purpose of the change and summarize what changed.
4. Describe the tests or checks you performed.
5. Request a review from a teammate.
6. Resolve review comments and conversations.
7. Wait for the required approval and passing status checks.
8. Use the repository's permitted merge method.

Do not merge a Pull Request until all required checks and review rules
have been satisfied.

## Issues

Use GitHub Issues to report bugs, propose improvements, or discuss tasks.
Include enough context to help the team understand and reproduce the issue.
Do not publish credentials, private data, or sensitive information.

## Data and Security

- Do not commit passwords, API keys, access tokens, or other secrets.
- Do not upload confidential or personal data.
- Keep raw and processed datasets in their designated directories.
- Follow the repository's [Security Policy](SECURITY.md) when reporting
  potential vulnerabilities.
