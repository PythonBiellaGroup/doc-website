---
title: "Pyenv Advanced"
date: 2021-03-28T23:54:10+02:00
summary: ''
weight: 200
draft: false

---
 
In this advanced section, you'll find tips, best practices, and guides to help you learn everything there is to know about Pyenv.

## Useful documentation


[https://realpython.com/intro-to-pyenv/](https://realpython.com/intro-to-pyenv/)

Pyenv with poetry

[https://blog.jayway.com/2019/12/28/pyenv-poetry-saviours-in-the-python-chaos/](https://blog.jayway.com/2019/12/28/pyenv-salvatori-nel-caos-pitone/)


Instructions for configuring Pyenv on a Mac.

[https://opensource.com/article/20/4/pyenv](https://opensource.com/article/20/4/pyenv)

Take note of a Github Gist.

[https://gist.github.com/Geoyi/f55ed54d24cc9ff1c14bd95fac21c042](https://gist.github.com/Geoyi/f55ed54d24cc9ff1c14bd95fac21c042)

Pyenv is a Python installation manager. Allow and execute other Python installations on the same machine.

Pyenv manages the many Python versions for you, avoiding the chaos of dependencies, versions, and installations seen in the first image.

**Why don't you use Python, which is installed by default on your operating system?**

- Because they might cause problems in projects, each has their own version, and there may be migration and reproducibility issues when they are used in production.

**What does pyenv allow us to do? (operational flow)**

1. Do not use Python in your own user space.
2. Install multiple Python versions.
3. Specify which Python version will be used for a project.
4. Easily switch between different versions of the software.


![PythonPyramid](./images/python-pyramid.png)

## Pyenv installation

To install Pyenv, please refer to the official documentation on Github. This is due to the fact that installation methods might change accordingly to your operating system and between its versions.

More advanced Pyenv usage may be found forward in this guide.

You may get the installation reference guide at: [here](https://github.com/pyenv/pyenv#installation).


**Pyenv installation verification**

Once installed and properly configured on your terminal, perform the following:

```bash
pyenv --version
```

### Install Python

Visualize python versions (here gets the 3.* ones only)

```bash
pyenv install --list | grep " 3\.[678]"
```

```bash
pyenv install -v 3.7.2
```
Visualize where Python versions are installed

```bash
ls ~/.pyenv/versions/
```
Disinstall a version of Pyhton

```bash
pyenv uninstall <version>
```
Every time a new version of Python with pyenv is installed on Windows (or other operating systems), it is vital to rehash.

```bash
# rehash to update shims
pyenv rehash
```

Disinstall vesrion of Python

```bash
# See all Python installation
# visualizzare le versioni di pyenv installate

pyenv versions

#disinstallare una determinata versione
pyenv uninstall <versione>
```

## Use a specific version of Pyenv

```bash
# Visualize the installed (available) versions
pyenv versions

# Visualize the active version of python with pyenv
pyenv which python

# Set a global Python version with pyenv
pyenv global <version>

# If you want to come back to the system default
pyenv global system
```
You can also specify a local python pyenv version for each project within the project folder by performing the following:

```bash
pyenv local <version>
```

Or set the version of a particular Python shell

```bash
pyenv shell <version>
```

### ⚠ Attention ⚠  IN WINDOWS 10   
After installing the Python global version of pyenv, remove any references to the basic Python that were previously installed from the environment variable **PATH**.

## Using pyenv to create virtualenvs

Pyenv offers a wonderful plugin called `pyenv-virtualenv` that allows you to easily manage the numerous virtualenvs.

A virtualenv can be managed in a variety of ways (pyenv allows you to manage all 3 in a very simple and convenient way)
- **pyenv** manages multiple versions of Python itself.
- **virtualenv/venv** manages virtual environments for a specific Python version.
- **pyenv-virtualenv** manages virtual environments for across varying versions of Python.

create a virtualenv

```bash
pyenv virtualenv <python_version> <environment_name>

#<pythonversion> is optional
```

Activate a virtualenv

```bash
pyenv local myproject

#verify python version
pyenv which python

#verify pip version
pyenv which pip
```
Then you may activate or deactivate a specific virtualenv (a bit like what happens with anaconda)

```bash
pyenv activate <environment_name>

pyenv deactivate
```

Con pyenv is even possible to use concurrently different pyhton versions at the same time...

## Pyenv with Poetry

[https://blog.jayway.com/2019/12/28/pyenv-poetry-saviours-in-the-python-chaos/](https://blog.jayway.com/2019/12/28/pyenv-poetry-saviours-in-the-python-chaos/)

### Bonus: utilizzare oh-my-zsh

You may use pyenv as a plugin on oh-my-zsh by adding `pyenv` inside the plugins section of the configuration file.

**Info:** Prevent conda from starting by default

`conda config --set auto_activate_base false`

# base libraries to install

Installed base libraries list (you need to create base project to configure these libraries)

- Bandit
- Black
- Poetry
- Flake8
- Mypy
- Isort
- Pylint
- Pytest

Fot this purpose, we recommend that you use Poetry on your projects to manage the necessary dependencies and libraries (both development and production).
