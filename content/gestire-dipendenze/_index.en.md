+++
title = "Manage Dependecies"
date = 2021-03-28T20:10:53+02:00
weight = 2
chapter = true
tags = ["versions","venv","dipendenze"]
+++

<!-- Hotjar Tracking Code for https://pythonbiellagroup.it -->
<script>
    (function(h,o,t,j,a,r){
        h.hj=h.hj||function(){(h.hj.q=h.hj.q||[]).push(arguments)};
        h._hjSettings={hjid:2847436,hjsv:6};
        a=o.getElementsByTagName('head')[0];
        r=o.createElement('script');r.async=1;
        r.src=t+h._hjSettings.hjid+j+h._hjSettings.hjsv;
        a.appendChild(r);
    })(window,document,'https://static.hotjar.com/c/hotjar-','.js?sv=');
</script>

# Manage Dependencies

In order to correctly manage dependecies from python 3.3 there exist a module named **venv** which is able to create a virtual environemnt inside your project.

This is actually old school, still many people is using that nowadays.

```bash
python -m venv my-virtualenv
```

The command inits a directory `my-virtualenv` whose files are:

- python binary
- pip/easy_install/wheel binary
- activation script
- binary files utilizzate da Python

Then you are required to activate the virtual envirnoment:

```bash
# On Linux and Mac
source ./my-virtualenv/bin/activate

# On Windows
my-virtualenv\Scripts\activate.bat

# Deactivate virtualenv
deactivate
```

Virtual ENVinonments are software abstractions that make your analysis portable and reproducible. As a matter of fact with venvs you are able to produce  `requirements.txt` files which contains the steps to install dependencies on your machine.

This is for sure one of the easiest way to deal with dependencies, but there are some alternatives that allows you to have more control and supervise you while you are setting up your project.

## pyenv-virtualenv

Pyenv is a nice tool to build even more easily virtual environments though its plugin `pyenv-virtualenv`.

```bash
# create a virtualenv
pyenv virtualenv 3.7.4 my-project

# list all venvs
pyenv virtualenvs

# activate virtualenv
pyenv activate my-project

# deactivate virtualenv
pyenv deactivate
```


Beside virtualenv and pyenv-virtualenv there are also other interesting dependecy management tools, these are:

- conda (`conda` package manager) invasive AF
- virtualfish
- virtualenvwrapper
- pipenv: super common in many tutorials, still the last contribution dated back to 2018 with more than 300k opened issues. pipenv is highly opnionated, take a look at [https://github.com/pypa/pipenv/issues/4058](https://github.com/pypa/pipenv/issues/4058))
- pipx: central dependency dispatchement