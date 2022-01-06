---
title: "Pyenv-virtualenv"
date: 2021-06-24T19:48:12+02:00
weight: 200
draft: false
---
Pyenv, in conjunction with a `pyenv-virtualenv` module, provides an even more powerful tool for creating virtual environments.

```bash
# Create virtual env
pyenv virtualenv 3.7.4 my-project

# List virtual venvs
pyenv virtualenvs

# Activate venvs
pyenv activate my-project

# deactivate venvs
pyenv deactivate
```
Other helpful and interesting utilities than virtualenv and pyenv-virtualenv include:


- conda (which also includes the 'conda' package manager), which is quite intrusive.
- the virtualfish
virtualenvwrapper
- pipenv: featured in many tutorials, but it is very badly maintained (the current version dates back to 2018 with 300+ outstanding issues) and can create various difficulties in a project (along with several debates associated to the project: [https://github.com/pypa/pipenv/issues/4058](https://github.com/pypa/pipenv/issues/4058))
- pipx: to consolidate and centralize dependencies (sometimes called central dispatchement)