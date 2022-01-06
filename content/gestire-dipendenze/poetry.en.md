---
title: "Poetry"
date: 2021-06-24T19:48:20+02:00
weight: 300
draft: false
---
[https://python-poetry.org/](https://python-poetry.org/)

Poetry is a new approach of organizing Python projects that adapts to the most popular current languages and frameworks (such as node with npm or nuget for .NET)


It is, in essence, a **package and dependency management tool**, allowing you to manage packages, dependencies, and versions by merging both python version management in a specific project with the relevant dependencies, as well as introducing much more complex notions.


The following are the most essential elements introduced by Poetry:


- Deterministic (and agile) project and library management

- Creating builds and packages for the project is made easier with customisable commands.

- rapidly publish packages on pypi

- With a single command, you may trace project dependencies.
- 
It's a young project, and there are still some bugs to work through, but the community is quite active, and they're delivering better and better solutions while also being reliable (and safe) enough to be used in production.

## How to use Poetry

The 'pyproject.toml' file, which is produced when the project is launched, is at the core of Poetry.

This file allows you to declare all project attributes and manage the entire project (as if we were using a package.json on javascript).

So, let's look at how to include poetry into a **new project**.


```bash
# init poetry on a directory
poetry init

# create a new poetry project
poetry new <app_name>

# inside the project edit the: pyproject.tml as you wish

# If you want to use virtual environments files inside the folder specify:
poetry config virtualenvs.in-project true

# If you do not specify that option venv are going to be kept inside its installation folder

# Compile the pyproject.toml file in order to source the virtual environment
poetry shell

# Add new dependencies (al pyproject.toml)
poetry add pandas

# Install new dependencies (poetry takes care of automagically populate the pyproject.toml file with newer deps)
poetry install

# launch a file
poetry run <script>

# Visualize venv path for this project (e anche l'elenco delle librerie)
poetry show -v

# exit poetry
exit
```

⚠ Attention ⚠ : When you use `poetry shell` on Windows, it automatically exits PowerShell and forces you to use cmd.

It is a known problem, but there is a way to solve it (a workaround)

[https://github.com/python-poetry/poetry/issues/2030](https://github.com/python-poetry/poetry/issues/2030)

How may poetry be included into an established project?

Perhaps it already has a `requirements.txt` file.

```bash
# initialize poetry inside an existing directory
poetry init

# maintain the .ven folder into your porject
poetry config virtualenvs.in-project true

## Import FROM requirements.txt TO poetry
poetry add $( cat requirements.txt )

# If you do not have requirements.txt go on with the standard format
```

**Generate poetry requirements.txt**

```bash
# Create a requirements.txt file form Poetry configpoetry
poetry export -f requirements.txt --output requirements.txt
```

Ezample of a pyproject.toml

```bash
[tool.poetry]
name = "poetry-tutorial-project"
version = "0.1.0"
description = "Simple python project built with poetry"
authors = ["Andrea Guzzo <andrea.guzzo92@gmail.com>"]
maintainers = ["Andrea Guzzo <andrea.guzzo92@gmail.com>"]
license = "MIT"
readme = "README.md"
homepage = "http://localhost:5000"
repository = "https://github.com/jeydi/"
documentation = "https://github.com/jeydi/"
keywords = [
	"Poetry",
	"Venv",
	"Virtual enviroments",
	"Packages",
	"Packaging"
]

[tool.poetry.dependencies]
python = "^3.7"
loguru = "*"
psutil = "*"
pandas = "*"
numpy = "*"
fastapi = "*"
typer = "^0.3.2"

[tool.poetry.dev-dependencies]
pytest = "^5.2"

[build-system]
requires = ["poetry-core>=1.0.0"]
build-backend = "poetry.core.masonry.api"

[tool.poetry.scripts]
run = "wsgi:main"

[tool.poetry.urls]
issues = "https://github.com/jeydi/"
```

##### ⚠ Attention ⚠:
Some libraries (for example, pandas) may have versioning issues with regard to dependent libraries.
In this regard, it is advised that pip be installed as a dependent and updated to the most recent version.

```bash
# Install pip 
poetry add pip

# Or, after the.venv containing poetry is produced, update pip 
# It is critical to have the.venv first 
pip install —upgrade pip

```
This is a workaround for a really long installation issues.

Poetry is undoubtedly slower than virtualenv, but it is considerably safer and more strict because it first verifies the safety of all dependencies.
