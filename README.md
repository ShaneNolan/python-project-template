# Python Project Template

## Prerequisites

- Python installed (_Preferably pyenv_).
- [Poetry](https://python-poetry.org/) installed.

## Usage

Rename `RENAME_ME` to the name of your project.

```bash
PROJECT_NAME="RENAME_ME" &&
python -m pip install cookiecutter &&
python -m cookiecutter --no-input gh:ShaneNolan/python-project-template \
project_name=$PROJECT_NAME &&
(cd $PROJECT_NAME && git init &&
poetry init --no-interaction --name $PROJECT_NAME &&
poetry add mypy pytest pytest-cov safety wemake-python-styleguide pre-commit nitpick --dev &&
poetry run nitpick fix &&
poetry run pre-commit install)
```

## Validate Setup

To validate your setup you can execute the following commands from inside the project directory (_where pyproject.toml exists_).

```bash
poetry run nitpick check
> No violations found. ✨ 🍰 ✨ # Confirms a successful setup.

poetry run pre-commit run --all-files
> Check for added large files..........................(no files to check)Skipped
> Trim Trailing Whitespace.............................(no files to check)Skipped
> Fix End of Files.....................................(no files to check)Skipped
> Check for merge conflicts............................(no files to check)Skipped
> Check for case conflicts.............................(no files to check)Skipped
> Check JSON...........................................(no files to check)Skipped
> Check Toml...........................................(no files to check)Skipped
> Check Yaml...........................................(no files to check)Skipped
> Pretty format JSON...................................(no files to check)Skipped
> Check python ast.....................................(no files to check)Skipped
> Debug Statements (Python)............................(no files to check)Skipped
> Check docstring is first.............................(no files to check)Skipped
> local flake8.........................................(no files to check)Skipped
> local mypy...........................................(no files to check)Skipped
> local pytest coverage................................(no files to check)Skipped
> local safety.........................................(no files to check)Skipped
# Having no files to check is normal for a new project 😉 .
```
