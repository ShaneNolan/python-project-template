# Python Project Template

Usage:
Rename `RENAME_ME` to the name of your project.

```bash
PROJECT_NAME="RENAME_ME" &&
cookiecutter --no-input \
gh:ShaneNolan/python-project-template project_name=$PROJECT_NAME &&
(cd $PROJECT_NAME &&
poetry init --no-interaction --name $PROJECT_NAME &&
poetry add mypy pytest pytest-cov safety wemake-python-styleguide pre-commit --dev &&
poetry run pre-commit install)
```
