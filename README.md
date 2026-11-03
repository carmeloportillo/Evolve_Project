# Evolve_Project

📊 Data Science project focused on data analysis, exploratory data analysis (EDA), data visualization, and machine learning to extract meaningful insights and support data-driven decision-making.

## Project Objectives

- Explore and analyze datasets.
- Perform exploratory data analysis (EDA).
- Create meaningful data visualizations.
- Develop and evaluate machine learning models when appropriate.
- Promote reproducible analysis and collaborative development.

## Project Structure

    Evolve_Project/
    ├── .github/workflows/
    ├── .vscode/
    ├── data/
    │   ├── raw/
    │   └── processed/
    ├── notebooks/
    ├── src/
    ├── tests/
    ├── .gitignore
    ├── pyproject.toml
    ├── requirements.txt
    ├── SECURITY.md
    └── README.md

## Requirements

- Python 3.12
- Git
- Visual Studio Code (recommended)

## Installation

### 1. Clone the repository

    git clone https://github.com/carmeloportillo/Evolve_Project.git
    cd Evolve_Project

### 2. Create a virtual environment

macOS/Linux:

    python3.12 -m venv .venv
    source .venv/bin/activate

Windows PowerShell:

    py -3.12 -m venv .venv
    .venv\Scripts\Activate.ps1

### 3. Install dependencies

    python -m pip install --upgrade pip
    python -m pip install -r requirements.txt

## Development

### Run tests

    python -m pytest -v

### Check code style

    python -m ruff check src tests

### Work with notebooks

Jupyter notebooks are stored in `notebooks/`. Open them in Visual Studio Code and select the Python interpreter from the project's `.venv` environment.

## Data Management

- `data/raw/` is intended for original, unmodified datasets.
- `data/processed/` is intended for cleaned or transformed datasets.
- Do not commit confidential, personal, or sensitive data.
- Large datasets should be shared through an approved storage solution rather than Git.

## Collaboration Workflow

1. Synchronize your local `main` branch.
2. Create a descriptive branch for your task.
3. Make your changes and run the relevant checks.
4. Commit your work with a clear message.
5. Push your branch to GitHub.
6. Open a Pull Request targeting `main`.
7. Request a review from a teammate.
8. Merge only after the required approval and checks have passed.

Example:

    git switch main
    git pull origin main
    git switch -c feature/short-description

## Continuous Integration and Security

GitHub Actions runs automated checks for pull requests and pushes to `main`. The repository also uses CodeQL for code security analysis and Dependabot for dependency update proposals.

See [SECURITY.md](SECURITY.md) for the project's security policy.

## License

No license has been specified yet. Check the repository for licensing information before reusing or redistributing its contents.
