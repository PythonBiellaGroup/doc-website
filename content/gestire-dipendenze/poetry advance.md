---
title: "Poetry Advance"
date: 2021-03-28T23:54:10+02:00
summary: ''
weight: 25
draft: false

---
Poetry è l'opzione di gestione delle dipendenze più sofisticata disponibile oggi (2020).

Va ben oltre le dipendenze, con funzionalità come la generazione di file .lock, la generazione di scaffolding del progetto e un sacco di opzioni di configurazione, tutte gestite tramite una semplice CLI. Se non sei sicuro di come strutturare e gestire in modo pulito ed efficace i tuoi progetti Python, fatti un favore e usa Poetry.

## **Installa poetry e includi l'installazione**

```bash
curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python3

#add poetry to env variables to your current shell
source $HOME/.poetry/env

#check if poetry is installed correctly
poetry --version
```

To install poetry using windows it's possible to launch the same command using the `git bash` so you can use the `curl` command (Be careful: use git bash as admin on your system)

[http://evaholmes.com/how-to-set-up-pyenv-and-poetry-on-windows-10-for-python-project-management/](http://evaholmes.com/how-to-set-up-pyenv-and-poetry-on-windows-10-for-python-project-management/)

After the installation add the following environment variable into the `path` variables inside the system variables

```bash
C:\Users\Anguz\.poetry\bin
```

On windows you can also use the powershell install script

```bash
(Invoke-WebRequest -Uri https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py -UseBasicParsing).Content | python -
```

Check the poetry version by doing:

```bash
poetry --version
```

By default poetry is installed into the user's platform-specific home directory. If you wish to change this, you may define the `POETRY-HOME` environment variable 

```bash
POETRY_HOME=/etc/poetry python [get-poetry.py](http://get-poetry.py/)
```

It's also possible to install Poetry with `pip` or with `pipx`

```bash
# Install poetry with pip
pip install --user poetry

# Install poetry with pipx
pipx install poetry

# Upgrade poetry with pipx
pipx upgrade poetry

# Uninstall poetry with pipx
pipx uninstall poetry

```

## **Create a python project via Poetry CLI**

```bash
poetry new poetry-tutorial-project
```

The secret sauce of every Poetry project is contained in a file called **pyproject.toml**. This is where we define everything from our project's metadata, dependencies, scripts, and more. If you're familiar with Node, think of pyproject.toml as the Python equivalent of package.json.

**Composition of poetry (toml file)**

Documentation: [https://python-poetry.org/docs/pyproject/](https://python-poetry.org/docs/pyproject/)

- *[tool.poetry]* = simply informational metadata about our package, such as the package name, description, author details, etc. Most of the config values here are optional unless you're planning on publishing this project as an official PyPi package
- *[tool.poetry.dependencies]* = This is where we define dependencies our application absolutely must download to run. You may specify specific version numbers for required packages (such as Flask = "1.0.0"), or if you simply want to grab the latest version, setting the version to "*" will do just that. You can also specify the project python version required to use and launch the app
- *[tool.poetry.dev-dependencies]* = Dev dependencies are packages that contributing developers should download to iterate on this project. Dev dependencies are not required to run the app, and won't be downloaded when the app is built by default.
- *[build-system]* = This is rarely a section you'll need to touch unless you upgrade your version of Poetry.
- *[tool.poetry.scripts]* = This is where we specify where our app entry point(s) is by assigning function within modules to the name of a script to be run. The example run = "wsgi:main" is specifying that we want to create a command called "run," which will look in [wsgi.py](http://wsgi.py/) for a function called main(). With this set, we can then launch our app via the Poetry CLI by typing *`poetry run`*
- *[tool.poetry.urls]*: This is a completely optional section where you can add any number of helpful links or resources that somebody downloading this package might find useful.

## **Installing and managing dependencies**

**`poetry shell`** The first time this command is run in your project directory, Poetry **creates** a Python **virtual environment** which will forever be associated with this project. Instead of creating a folder containing your dependency libraries (as virtualenv does), **Poetry creates an environment on a global system path**, therefore separating dependency source code from your project. Once this virtual environment is created, it **can be activated again at any time** by simply *running poetry* shell in your project directory in the future. Try comparing the output which python before and after activating your project shell to see how Poetry handles virtual environments.

`**poetry install**` Installs the dependencies specified in pyproject.toml. The first time a project's dependencies are installed, a **.lock file is created**, which **contains the actual version numbers of each package that was installed** (i.e.: if Flask = "*" resulted in downloading Flask version 1.0.0, the actual version number would be stored in .lock). If a .lock file is present, the version numbers in .lock will always be prioritized over what is in pyproject.toml.

`**poetry update**` Mimics the functionality of install, with the exception that **version numbers in .lock will NOT be respected**. If newer versions exist for packages in pyproject.toml, newer versions will be installed, and .lock will be updated accordingly.

`**poetry add [package-name]**` A shortcut for adding a dependency to pyproject.toml. The package is installed immediately upon being added.

`**poetry remove [package-name]`** 

`**poetry export -f requirements.txt > requirements.txt`** Exports the contents of your project's .lock file to requirements.txt. It comes in handy when handing work off to developers who still use requirements.txt for some reason.

`**poetry env list --full-path`** Visualize poetry environment path and list

## **Configurations**

`**poetry config**` "Config" refers to environment-level configuration, such as the paths of the current virtual environment, or environment variables. Passing the --list option will return your environment's current config values.

`**poetry check**` Checks pyproject.toml for errors.

`**poetry show**` Returns a breakdown of all packages currently installed to the project, including dependencies of dependencies.

## **Exec applications**

`**poetry run [script-name]**` Executes a script defined in the [tool.poetry.scripts] section of pyproject.toml.

## **Building and publishing**

`**poetry build**` Builds the source and wheels archives.

`**poetry publish**` Publishes the output of the previous build to the project's external repository (likely PyPi).

## Poetry Getting Started

```bash
##Initialize poetry inside a folder
poetry init

#Or Create a new project
poetry new <app_name>

##Modify the pyproject.toml as u wish

#if you want poetry venv inside the project folder do:
poetry config virtualenvs.in-project true

#compile poetry and create the venv
poetry shell

#Add dependencies
poetry add pandas

#Install dependencies
poetry install

#launch a file
poetry run <script>

#Visualize where the env is inside a project (and also the list of libraries)
poetry show -v

# You can also use the default python check command to see your currently python version
which python

#Exit from poetry shell and environment
exit

#To remove a Poetry venv
poetry env remove <python>
```

## **Add poetry to existing project (with existing requirements.txt)**

```bash
#initialize poetry inside directory
#move to directory and
poetry init

#compile the informations

## Import requirements.txt libraries to poetry
cat requirements.txt|xargs poetry add

#if you want poetry venv inside the project folder do:
poetry config virtualenvs.in-project true
```

**Generate poetry requirements.txt**

```bash
poetry export -f requirements.txt > requirements.txt
```

## **Poetry in VSCode**

Poetry is not yet integrated inside the vscode official python extension, so you have to manual tricky the configs.

- run in terminal: `**poetry env list --full-path`** and copy the path of the poetry venv path
- In the project folder create a new folder called: .vscode
- Inside the folder create a file called: settings.json
- Inside the file add this config:

```bash
{
    "python.pythonPath": "<path to your venv copied>"
}
```

- Restart vscode and by default python will use that config

Remember also to launch in terminal: poetry shell to activate the environment.

Remember not to push into your git config your vscode configurations!

Another method

Launch in your project terminal

```bash
#tell poetry to generate the .venv
poetry config virtualenvs.in-project true --local
poetry config virtualenvs.create true --local
poetry config settings.virtualenvs.in-project true

#then launch
poetry install
```

To generate a virtualenv folder inside the project folder, so VSCode can understand that this is the default virtualenv to use instead the global one.

If you want to stop using the .venv inside the project folder is possibile to do:

```bash
#tell poetry not to use venv inside the proj folder
poetry config virtualenvs.in-project true --local
poetry config virtualenvs.create true --local
poetry config settings.virtualenvs.in-project true
```

## Toml Example

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

# Update poetry

Updating poetry to the latest stable version is simple

```bash
#update poetry to the last stable version
poetry self update

#if you want to install pre-release versions
poetry self update --preview
```

# Delete Poetry

To uninstall poetry you can use this commands

```bash
#Uninstall poetry
python get-poetry.py --uninstall

# Another method (optional)
# Setting the POETRY_UNINSTALL env variable befor executing the installer
POETRY_UNINSTALL=1 python get-poetry.py
```

# Enable tab completion for bash or zsh

Poetry supports generating completion scripts for bash, zsh or fish.

If you want some help about this functionality please check: `poetry help completions`

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

You may need to restart your shell to see the changes.

Caution:

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

# Deploy

Using Poetry with Docker for Deploy

- [https://medium.com/@harpalsahota/dockerizing-python-poetry-applications-1aa3acb76287](https://medium.com/@harpalsahota/dockerizing-python-poetry-applications-1aa3acb76287)
- docker caching: [https://pythonspeed.com/articles/poetry-vs-docker-caching/](https://pythonspeed.com/articles/poetry-vs-docker-caching/)
- Production Ready Docker packaging for python developers: [https://pythonspeed.com/docker/#articles-the-basics-of-docker-packaging](https://pythonspeed.com/docker/#articles-the-basics-of-docker-packaging)

# Documentation and useful links

Official Documentation (very very useful) **:** [https://python-poetry.org/docs/basic-usage/](https://python-poetry.org/docs/basic-usage/)

[https://hackersandslackers.com/python-poetry-package-manager/](https://hackersandslackers.com/python-poetry-package-manager/)

[https://www.youtube.com/watch?v=QX_Nhu1zhlg&ab_channel=PyGotham2019](https://www.youtube.com/watch?v=QX_Nhu1zhlg&ab_channel=PyGotham2019)

Build CLI Utilities with Poetry and Typer: [https://www.pluralsight.com/tech-blog/python-cli-utilities-with-poetry-and-typer/](https://www.pluralsight.com/tech-blog/python-cli-utilities-with-poetry-and-typer/)

Confronto con altre librerie: [https://towardsdatascience.com/devops-for-data-science-making-your-python-project-reproducible-f55646e110fa](https://towardsdatascience.com/devops-for-data-science-making-your-python-project-reproducible-f55646e110fa)

Use Poetry in Production (with Docker): [https://stackoverflow.com/questions/53835198/integrating-python-poetry-with-docker](https://stackoverflow.com/questions/53835198/integrating-python-poetry-with-docker)

Data Science PRO with Poetry + Jupyter + VSCode: [https://medium.com/analytics-vidhya/setting-up-data-science-python-projects-with-vscode-poetry-jupyter-b96efeea24c8](https://medium.com/analytics-vidhya/setting-up-data-science-python-projects-with-vscode-poetry-jupyter-b96efeea24c8)

Poetry Configure Workspace:

 [https://zhauniarovich.com/post/2020/2020-02-configuring-python-workspace-p2/](https://zhauniarovich.com/post/2020/2020-02-configuring-python-workspace-p2/)

**To solve problems with psycopg2 and Python**

[https://blog.vince.id/installing-psycopg2-on-macos](https://blog.vince.id/installing-psycopg2-on-macos)
