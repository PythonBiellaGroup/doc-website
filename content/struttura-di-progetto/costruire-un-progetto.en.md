---
title: "Build a project"
date: 2021-05-10T23:54:10+02:00
summary: ''
weight: 400
draft: false

---

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

# How to set up project with acquired tools?

Let's go through all of the procedures required to create a Python project using the tools shown in this article.

This tutorial is intended to assist people who are approaching this new technique of carrying out projects using Python for the first time in order to develop a first version of the project that is up and running.

It also intends to readily bring other members of the team to use these tools in order for them to become acquainted with them as soon as possible, therefore creating a legitimate reference for the project.

If you find any difficulties, mistakes, or inaccuracies in this guide, please let us know by posting bugs on gitlab or writing to us directly.

## Install requirements

The first step is to install all of the required tools.

Obviously, we presume that you all have a Linux, Windows, or MacOS system with a Python version installed that is at least equivalent (or better) than Python 3.6.X.

### Install Pyenv

While not required, but strongly encouraged, the first step is to install pyenv to make it easier to use and install a specific version of Python for a project.

### Install Poetry


##  Initial config of Poetry for a project


## Install libraries

**DevelopmentL libraries**

The development libraries include all of the libraries required to create source code, such as a linter, debugger, code normalization, syntax check, and so on.

`poetry add -D flake8 flake8-isort flake8-builtins autopep8 pylint bandit black`

**EDA Python libraries**

If Jupyter is not an essential necessity for using the project in production, it is advised to install data exploration libraries (such as Jupyter) in development mode.

`poetry add -D jupyter jupyterlab`

## Flake8 config