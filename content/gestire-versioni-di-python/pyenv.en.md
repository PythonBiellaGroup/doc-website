---
    title: "Pyenv Beginner"
date: 2021-03-28T23:54:10+02:00
summary: ''
weight: 100
draft: false

---
Pyenv allows you to handle several versions of Python installed on your PC in a very simple and fast manner.

It's basic and unobtrusive, and it works on any operating system.

- Allows you to modify the ** global version of Python ** or the ** local version of Python ** for each project or user.
- Enables you to maintain a local version of each project with its own Python version.
- Allows you to ** override ** the Python version as environment variables (no more manually managing them).
- Allows you to search for and manage different Python versions (with tox)

Some critical considerations
- There is no bootstrap problem because it is built entirely of shell scripts.
-  It is not necessary to load it inside your shell; simply enter its directory in the environment variables and it works "on its own." 
- It also allows (and possibly requires) more efficient management of virtual environments.

Very good documentation with a lot of internet support.
- [https://github.com/pyenv/pyenv](https://github.com/pyenv/pyenv)

main commands

```bash
# list all pyhton versions available
pyenv install --list

# Install a specific Python version
pyenv install 3.7.4

# Visualize where Python versions are installed
pyenv versions

# Set a global Python version with pyenv ( used by all the OS)
pyenv global 3.7.4

# Set a local Python version (used for this specific project)
pyenv local 3.7.4 # it creates .python-version file

# By deleting the file you also delete the local .python-version installation
rm .python-version

# change Pyhton shell for the current session
pyenv shell system
```

We addressed the problem of rapidly and efficiently changing the version of Python installed on your PC with pyenv.

There is still the issue of managing dependencies (libraries) across several projects.

Python has a major limitation: **you cannot install several versions of the same library (package)** in the same version of Python.

The **virtualenvironments** have arrived.

It is critical to utilize different virtualenvs for each Python project, beginning with the simplest.