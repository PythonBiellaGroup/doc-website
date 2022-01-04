---
title: "Flake8"
date: 2021-03-28T23:54:10+02:00
summary: ''
weight: 200
draft: false
---

Besides formatting tools there are also **linters**, whose aim is static code analysis.

The most popular on Python is `Flake8`.

Flake8 does not change any code, it suggests warnings and caveats in **real time**

Flake8 is the result og 3 projects:

- pyflakes [https://github.com/pycqa/pyflakes](https://github.com/pycqa/pyflakes), which warns about both unused modules and declared variables
- pycodestyle [https://pycodestyle.pycqa.org/en/latest/](https://pycodestyle.pycqa.org/en/latest/) PEP8 violations
- McCabe [https://github.com/pycqa/mccabe](https://github.com/pycqa/mccabe) (default is off) warns if functions are really too long or complex

One other advatage of Flake8 is the vast amount of extensions and plugins which can be integrated into your worflow and best practices (we have already seen _Bandit_). Extensions are really useful when coding mates are prone to use different style guidelines or conventions since the only this needed to be aligned is to download the corresponding extension.

full list of extensions: [https://github.com/DmytroLitvinov/awesome-flake8-extensions](https://github.com/DmytroLitvinov/awesome-flake8-extensions)

Some other recommended extensions:

- [flake8-builtins](https://github.com/gforcada/flake8-builtins) - makes sure you don’t use Python builtins as variables or parameters
- [flake8-bugbear](https://github.com/PyCQA/flake8-bugbear) - an additional set of checks (some are opinionated) that will complain when you, for example:
    - Use `except:` instead of `except Exception:`
    - Use `++n`
    - Use `.strip()` on a multiline string
    - Use a length-one tuple
- [flake8-comprehensions](https://github.com/adamchainz/flake8-comprehensions) - helps you write better list/set/dictionary comprehensions
- [flake8-docstrings](https://pypi.org/project/flake8-docstrings/) - enforces PEP257
- [flake8-eradicate](https://github.com/sobolevn/flake8-eradicate) - reports commented out code (“dead code”)
- [flake8-isort](https://pypi.org/project/flake8-isort/) - check if your import statements are sorted according to the [isort](https://pypi.org/project/isort/) recommendations
- [flake8-broken-line](https://github.com/sobolevn/flake8-broken-line) - complains you use backslash for line breaks (try using parenthesis or tripple quotes instead)
- [flake8-quotes](https://github.com/zheller/flake8-quotes) - if you prefer single quotes over double quotes (or the other way around), this plugin can help you enforce them
- [flake8-rst-docstrings](https://github.com/peterjc/flake8-rst-docstrings) - looks for problems in your documentation (usefull if you are using Sphinx that we will talk about later)
- [darglint](https://github.com/terrencepreilly/darglint) - checks if your docstrings are matching functions definitions (for example, if you remembered to describe all the parameters and the return value)
- [flake8-mutable](https://github.com/ebeweber/flake8-mutable) - checks that you don’t use mutable default arguments
- flake8-bandit - introduce the capabilities of bandit inside flake8

## Flake8 installation

```bash
pip install flake8

# still pipx is preferred for a consistent workflow
pipx install flake8

# install extensions
pip install flake8-docstrings flake8-isort
# still pipx is preferred for a consistent workflow also for extension
pipx inject flake8 flake8-docstrings flake8-isort flake8-bandit

# If you run into a path error
pipx ensurepath

# .. then reboot terminal
```

Run Flake8

```bash
flake8 my_project #my_project = workdir
```


To make the best use of Flake8 it is highly encouraged the VScode integration by launching `Python: Select Linter`

Managing big projects with Flake8 and its plugins and extensions could be a mess sometimes. However it comes to help the helpful library `FlakeHell`. Flakehell is wrapper around Flake which allows us to specify flake8 configuration directly inside the `pyproject.toml` (poetry library management file).

⚠ Attention ⚠. flakehell is no longer maintained (2019), however you can still use it at your risk (compatibility issues).

- FlakeHell: [https://github.com/life4/flakehell](https://github.com/life4/flakehell)
- Example: [https://dev.to/bowmanjd/using-flake8-and-pyproject-toml-with-flakehell-1cn1](https://dev.to/bowmanjd/using-flake8-and-pyproject-toml-with-flakehell-1cn1)


There are a number of other tools that help supervise code and bugs while you are typing.

- pylint
- pydocstyle
- bandit
- vulture
- wemake-python-style guide
- prospector

Still `Bandit` is the most common and the best partner to Flake8