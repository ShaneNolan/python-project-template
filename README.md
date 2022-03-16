# Python Project Template

## Prerequisites

- Python installed (_preferably pyenv_).
- [Poetry](https://python-poetry.org/) installed.
- [EditorConfig](https://editorconfig.org/) installed.

## Usage

Rename `MY_PROJECT_NAME` to the name of your project.

```bash
# Specify the Python version you want to use with pyenv.
# Ignore this command if you don't use pyenv.
pyenv shell 3.9.0

---------------------------------------------
# Mac OS: Specify the name of the project.
export PROJECT_NAME="MY_PROJECT_NAME"

# Windows: Specifcy the name of the project.
set PROJECT_NAME="MY_PROJECT_NAME"
---------------------------------------------

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

tree -a
>
├── .editorconfig
├── .gitignore
├── .nitpick.toml
├── .pre-commit-config.yaml
├── CHANGELOG.md
├── README.md
├── PROJECT_NAME
│   └── __init__.py
├── poetry.lock
├── pyproject.toml
├── setup.cfg
└── tests
    └── __init__.py

2 directories, 11 files
# Your project structure should look like this.
```

## Connect project to remote repository.

For a new project you will likely need to conect it with a remote repository.

```bash
git remote add origin REPOSITORY_URL
```

**Congratulations, you've successfully setup and configured your Python environment 🎉 .**
