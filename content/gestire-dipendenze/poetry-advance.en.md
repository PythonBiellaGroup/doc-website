---
title: "Poetry Advance"
date: 2021-06-24T19:48:30+02:00
weight: 400
draft: false
---
Poetry is the most sofisticated Python dependency system available (up to 2020)

It allows you to go beyond simple dependency management, with functions such as: generate.lock files, allow project scaffolding with many customization possibilities, all available via CLI.

## **poetry installation & init**


It is critical to consult to the official guide that details the processes for the various operating systems before installing Poetry.

We do not intentionally disclose installation instructions because they frequently change with new updates and versions.
In this regard, the reference site is: [original documentation](https://python-poetry.org/docs/#installation)

<!-- Prima di installare poetry fare riferimento anche alla !(guida ufficiale)[https://python-poetry.org/docs/#installation] che spesso è più aggiornata, soprattutto al cambio delle varie versioni

```bash
curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python -

#aggiungere poetry alle variabili di ambiente della sessione shell corrente
source $HOME/.poetry/env

#controllare se poetry è installato correttamente
poetry --version
```

Per installare poetry usando windows è possibile lanciare lo stesso comando usando la `git bash` in modo da poter usare il comando `curl` (attenzione: conviene utilizzare git bash come amministratore)

[http://evaholmes.com/how-to-set-up-pyenv-and-poetry-on-windows-10-for-python-project-management/](http://evaholmes.com/how-to-set-up-pyenv-and-poetry-on-windows-10-for-python-project-management/)

Dopo l'installazione aggiungete la seguente variabile d'ambiente nelle variabili di percorso all'interno delle variabili di sistema

```bash
#sostituite <nomeutente> con il vostro utente
C:\Users\<nomeutente>\.poetry\bin

```

Su windows è possibile anche usare lo script di installazione di powershell

```bash
(Invoke-WebRequest -Uri https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py -UseBasicParsing).Content | python -
```

Per controllare la versione corrente di poetry installata nel sistema è possibile fare:

```bash
poetry --version
```

Di default poetry è installato nella home directory specifica del vostro utente. Se si desidera cambiare l'impostazione è possibile definire la seguente variabile d'ambiente `POETRY-HOME`

```bash
POETRY_HOME=/etc/poetry python [get-poetry.py](http://get-poetry.py/)
```

È anche possibile installare Poetry con `pip` o con `pipx`

```bash
# Install poetry with pip
pip install --user poetry

# Install poetry with pipx
pipx install poetry

# Upgrade poetry with pipx
pipx upgrade poetry

# Uninstall poetry with pipx
pipx uninstall poetry

``` -->

##  create a project in python using Poetry

```bash
poetry new poetry-tutorial-project
```

The secret formula for each poetry-based project is the establishment of a file named `pyproject.toml`. This file contains information on everything in the project, including metadata, dependencies, libraries, scripts, and much more...

If you're familiar with node.js, we may treat the pyproject.toml file as a project package.json.

**Poetry pyproject.toml details**

Documentazione: [https://python-poetry.org/docs/pyproject/](https://python-poetry.org/docs/pyproject/)

- *[tool.poetry]* = basic descriptive metadata about the package you're working on (such as package name, description, author, details, ...). Some options are only relevant if you intend to publish your package on Pypi.
- *[tool.poetry.dependencies]* = It enables you to establish application requirements that are absolutely needed for your program to run. It is also possible to provide the version of the package you wish to install (for example, Flask = "1.0.0"). If you just wish to define the most recent version, use "*." You may also define the Python version necessary to run the project and your application.
- *[tool.poetry.dev-dependencies]* = Dev dependencies are all of the libraries that developers require in order to build and program the project, but which should not be used in production. These dependencies are not required for the application to run and will not be downloaded if it is "built" by default.
- *[build-system]* = This section is rarely changed; only alter it if you intend to update Poetry.
- *[tool.poetry.scripts]* = This is where you provide the program's entry points, designating a function inside the modules required to run the application. In the example: run = "wsgi: main" indicates that we want to build a "run" command that will look in the file "[wsgi.py] (http://wsgi.py/)" for a function called: main(). With this option, the program may be launched from the CLI by typing: *'poetry run'*
- *[tool.poetry.urls]*: This parameter is optional and may be used to enter relevant links to resources, documentation, or other related to the project. It is required if you intend to release your package.

## **Depencies installation & mngmt**

**`poetry shell`** 

When you use this command in your project directory for the first time, Poetry establishes a Python virtual environment that is permanently connected with this project. Poetry provides an environment on a global system path rather than a folder holding your dependency libraries (like virtualenv does), therefore segregating the dependency source code from your project. Once this virtual environment has been built, it may be reactivated at any time by executing `poetry shell` in your project directory. To test how Poetry handles virtual environments, compare python output before and after prompting your project.

`**poetry install**` 

Install the dependencies listed in the pyproject.toml file. When a project's dependencies are installed for the first time, a.lock file is produced that stores the real version numbers of each package installed (for example, if Flask = "*" resulted in a download of Flask version 1.0.0, the actual version number would be placed in.lock). If there is a .lock file, the version numbers in .lock take precedence over those in pyproject.toml.

`**poetry update**` 

It functions similarly to install, with the distinction that version numbers in .lock will NOT be obeyed. If newer versions of the packages in pyproject.toml are available, they will be installed and .lock will be changed accordingly.

`**poetry add [package-name]**` 

A shortcut for adding a dependency in pyproject.toml. The package is installed as soon as it is added.

`**poetry remove [package-name]`** 

Removes a dependence from the project dependency list given in pyproject.toml.

`**poetry export -f requirements.txt > requirements.txt`** 

The contents of your project's.lock file should be exported to requirements.txt. This is handy for handing work to developers who, for whatever reason, _still_ use requirements.txt.

You can alternatively use the command `poetry export -f requirements.txt —output reqtest.txt —without-hashes` to export the dependencies to a separate file (reqtest.txt) and without the hashes that encrypt packets. This function might be beneficial if the standard command fails to install the requirements.txt file.

`**poetry env list --full-path`** 

Take a look at the route and environment list.

## **configs**

`**poetry config**` 

"Config" refers to environment-wide configuration, such as the virtual environment's routes or environment variables. The —list option returns the current configuration values for your environment.

`**poetry check**` 

Look for any issues in the pyproject.toml file.

`**poetry show**` 

Returns a summary of all presently installed packages in the project, including dependent dependencies.

## **Execute applications**

`**poetry run [script-name]**` 

Executes the script described in the pyproject.toml section: [tool.poetry.scripts].

## **Build & publish package (project as a package)**

`**poetry build**` 

Allows you to create a build of the source code as well as the 
wheels archive.
    
`**poetry publish**` 

Publish the build output to an external repository (such as Pypi)

## Poetry Getting Started

Let's see how to init poetry from scratch in a new project

```bash
## initialize petry in a new empty folder
poetry init

# alternatively create a new folder with app name with the command new
poetry new <app_name>

## noew you are able to edit files: pyproject.toml as you want

# If you wish to include the.venv folder in the project, follow these steps:
poetry config virtualenvs.in-project true

# You must now cpmpile poetry to make the venv.
# And then run the shell with the venv you specified.
poetry shell

# IF required update pip
python -m pip install --upgrade pip
# this might happen if you encouter problem when installing deps

# Add and install dependency
poetry add pandas

# Add and install dev dependency
poetry add -D flake8

# If you declared the libraries in the pyproject.toml file, you may install them with this command.
poetry install

# to tuna file within the pyproject.toml
poetry run <script>

# Examine the virtual env route within the project (or outside of it) also included is a list of installed libraries.
poetry show -v

# The default Python version that is presently in use is always visible.
which python

# to exit poetry and venv
exit

# remove venv with Poetry
poetry env remove <python>
```

## Add Poetry TO an existing project (with requirements.txt) 

```bash

# initialize poetry inside the directory
poetry init

# compile data with poetry

# if you wish to include the venv inside the project remember to execute
poetry config virtualenvs.in-project true

## import requirements.txt (project libraries) inside poetry
poetry add $( cat requirements.txt )

```

**Generate FROM Poetry a requirements.txt file:** 

```bash
poetry export -f requirements.txt > requirements.txt

# A more exhaustive example
poetry export -f requirements.txt --output reqtest.txt --without-hashes
# create a new file: reqtest.txt 
#without hashes (i.e. without library signature)
# is less secure because pip hashes may cause installation difficulties.
```

⚠ Attention ⚠ It is possible that you may need to update pip to install specific libraries in some cases; to do so, after you have built and activated your virtualenvironment with Python, perform the following:

```bash
# Update pip
python -m pip install --upgrade pip
```

This problem can occur as soon as you run a library installation or do `poetry install` or` poetry update`.

⚠ Attention ⚠  do not name any file or module, or your project as a name of a library that you will install using poetry.

In addition to being a bad practice in a project it will send poetry into confusion by giving you an `AssertionError`.

[https://github.com/python-poetry/poetry/issues/236](https://github.com/python-poetry/poetry/issues/236)

If you build a module, a folder, or a file with the same name as a library, the advise is to rename the offending file or folder, remove your virtualenvironment, and run again: To install a fresh version of the virtualenv, use poetry install.

## **Poetry in VSCode**

Poetry is not yet incorporated into vscode or the official Python extension, therefore you must setup it manually to use it with vscode.

To let the project to use the virtual environment, a file must be defined by entering the virtual environment's reference path produced with poetry.

- Type **`poetry env list —full-path`** at the terminal. and copy the path that belongs to poetry's virtual environment (venv).
- Within the project, make a new folder called .vscode.
- Within the folder, make a file called `settings.json`
- In the file, add the following configuration:

```bash
{
    "python.pythonPath": "<copied path>"
}
```

- Relaunch vscode, and the Python version you made with Poetry will be utilized automatically when you open a .py file.

Always remember to type `poetry shell` into the terminal to launch the environment.

Remember not to push the newly produced vscode settings to your remote git repository so that they do not override those of your colleagues (insert the .vscode folder into the `gitignore` file).

still another way

From the terminal, start the project.

```bash
# tell poetry to locally generate venv
poetry config virtualenvs.in-project true --local
poetry config virtualenvs.create true --local
poetry config settings.virtualenvs.in-project true

# then launch poetry
poetry install
```

As a result of creating a virtualenv folder within the project, vscode will recognize that this is the default virtualenv to use rather than the global one.

If you wish to stop using .venv within the project, you may do the following:

```bash
# tell poetry not to use venv inside the proj folder
poetry config virtualenvs.in-project false --local
poetry config virtualenvs.create false --local
poetry config settings.virtualenvs.in-project false
```

## Pyproject.toml example

Here's an example of a pyproject.toml file you may use in your projects (obviously with the appropriate changes and customizations)

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

## Aggiornare poetry

Updating poetry to the latest stable versione is as simple as that:

```bash
# update poetry to [latest]
poetry self update

# update poetry to [latest-dev]
poetry self update --preview
```

## Delete poetry

To remove poetry you can execute these scripts

```bash
# Uninstall poetry
python get-poetry.py --uninstall

# Another method (optional)
# Setting the POETRY_UNINSTALL env variable befor executing the installer
POETRY_UNINSTALL=1 python get-poetry.py
```

## Enable completion for bash or zsh

PùPoetry supports terminal autocomplete for a variety of command-line interfaces (CLIs) such as bash, zsh, and fish.


If you want additional information about these features, type: `poetry help completions`.

```bash
poetry completions bash > /etc/bash_completion.d/poetry.bash-completion

# Bash (Homebrew)
poetry completions bash > $(brew --prefix)/etc/bash_completion.d/poetry.bash-completion

# Zsh
poetry completions zsh > ~/.zfunc/_poetry

# Oh-My-Zsh
mkdir $ZSH_CUSTOM/plugins/poetry
poetry completions zsh > $ZSH_CUSTOM/plugins/poetry/_poetry
```


you need to restart the shell to apply changes

⚠ Attention ⚠  (some details):

For `zsh` you must add the following line into `~/.zshrc` profile before `compinit`

```bash
fpath+=~/.zfunc
```

For `oh-my-zsh` you must then enable poetry in your `~/.zshrc` plugin

```bash
plugins(
    poetry
    ...
    )
```

## Deploy

How to put poetry into production with Docker:

Here are the references:

- [https://medium.com/@harpalsahota/dockerizing-python-poetry-applications-1aa3acb76287](https://medium.com/@harpalsahota/dockerizing-python-poetry-applications-1aa3acb76287)
- docker caching: [https://pythonspeed.com/articles/poetry-vs-docker-caching/](https://pythonspeed.com/articles/poetry-vs-docker-caching/)
- Production Ready Docker packaging for python developers: [https://pythonspeed.com/docker/#articles-the-basics-of-docker-packaging](https://pythonspeed.com/docker/#articles-the-basics-of-docker-packaging)

In this regard, we provide an example `Dockerfile` that you may use as a starting point for your deployment (even for production images)

**Dockerfile**
```bash
FROM python:3.8

# Metadata
LABEL name="PBG Poetry Example"
LABEL maintainer="PBG"
LABEL version="0.1"

ARG YOUR_ENV="virtualenv"

ENV YOUR_ENV=${YOUR_ENV} \
    PYTHONFAULTHANDLER=1 \
    PYTHONUNBUFFERED=1 \
    PYTHONHASHSEED=random \
    PIP_NO_CACHE_DIR=off \
    PIP_DISABLE_PIP_VERSION_CHECK=on \
    PIP_DEFAULT_TIMEOUT=100 \
    POETRY_VERSION=1.1.6 \
    LC_ALL=C.UTF-8 \
    LANG=C.UTF-8

# System deps:
RUN DEBIAN_FRONTEND=noninteractive apt update && apt install -y libpq-dev gcc

# Install poetry
RUN pip install "poetry==$POETRY_VERSION"

# Copy only requirements to cache them in docker layer
WORKDIR /app

#Copy all the project files
COPY . .
# Install libraries 
RUN poetry config virtualenvs.create false \
    && poetry install $(test "$YOUR_ENV" = production) --no-dev --no-interaction --no-ansi

# Set the launching script exec
RUN chmod +x launch.sh

# Launch the script for cron
CMD ["bash", "launch.sh"]

# Launch main python script
# CMD ["gunicorn", "-w", "4", "-b", "0.0.0.0:8000", "core.app:app"]
```

## Documentation and  useful links


Official Documentation (really on point) **:** [https://python-poetry.org/docs/basic-usage/](https://python-poetry.org/docs/basic-usage/)

[https://hackersandslackers.com/python-poetry-package-manager/](https://hackersandslackers.com/python-poetry-package-manager/)

[https://www.youtube.com/watch?v=QX_Nhu1zhlg&ab_channel=PyGotham2019](https://www.youtube.com/watch?v=QX_Nhu1zhlg&ab_channel=PyGotham2019)

Build CLI Utilities with Poetry and Typer: [https://www.pluralsight.com/tech-blog/python-cli-utilities-with-poetry-and-typer/](https://www.pluralsight.com/tech-blog/python-cli-utilities-with-poetry-and-typer/)

Compare dependency manager: [https://towardsdatascience.com/devops-for-data-science-making-your-python-project-reproducible-f55646e110fa](https://towardsdatascience.com/devops-for-data-science-making-your-python-project-reproducible-f55646e110fa)

put Poetry into Production (with Docker): [https://stackoverflow.com/questions/53835198/integrating-python-poetry-with-docker](https://stackoverflow.com/questions/53835198/integrating-python-poetry-with-docker)

Data Science PRO with Poetry + Jupyter + VSCode: [https://medium.com/analytics-vidhya/setting-up-data-science-python-projects-with-vscode-poetry-jupyter-b96efeea24c8](https://medium.com/analytics-vidhya/setting-up-data-science-python-projects-with-vscode-poetry-jupyter-b96efeea24c8)

Poetry Configure Workspace:

 [https://zhauniarovich.com/post/2020/2020-02-configuring-python-workspace-p2/](https://zhauniarovich.com/post/2020/2020-02-configuring-python-workspace-p2/)

**To solve problems with psycopg2 and Python**

[https://blog.vince.id/installing-psycopg2-on-macos](https://blog.vince.id/installing-psycopg2-on-macos)
