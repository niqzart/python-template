# Python Template
## Basics
A template repository for python projects with:
- Poetry
- Linters (flake8, wemake-style-guide, mypy)
- Formatters (black, autoflake)
- Pre-commit
- Pytest

### How to use
Click "use this template" on the top right of the main repository page and create a new repository from this one. After that you can work on your new repository as usual. I'd recommend searching all `TODO` comments in the resulting repository and completing them

### Install
```
# TODO set to your poetry version
pip install poetry
poetry install
pre-commit install
```

## Additions
### Docker
Here is a template dockerfile for python /w poetry:
```dockerfile
FROM python:3.12-alpine

# TODO change to any directory
WORKDIR /app
RUN pip install --upgrade pip

# TODO set to your poetry version
RUN pip install poetry==1.8.0
RUN poetry config virtualenvs.create false

COPY pyproject.toml poetry.lock ./
RUN poetry install --no-interaction --no-ansi --only main

# TODO `COPY` your project files

# TODO set the ENTRYPOINT and/or CMD
```

### Docker Compose
And a template docker-compose file:
```yaml
services:
  app:
    # depends_on:
    #   - database
    build:
      context: .
      dockerfile: Dockerfile
    # image:
    restart: always
    # command: ...
    # ports:
    #   - "8000:8000"
    # volumes:
    #   - ./<SOURCE>:/<WORKDIR>  # pass your files for quik-reload
    # environment:
    #   SECRET: local
```
