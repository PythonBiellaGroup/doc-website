---
title: "cookiecutter"
date: 2021-03-28T23:54:10+02:00
summary: ''
weight: 300
draft: false

---
Returning to the initial topic of project structure in Python (and many other languages and / or frameworks), each project is unique, however some projects have certain similar aspects.

For example, they frequently include a file with a list of dependencies and some tests, a web application requires a "main" and we want our team to have a structure that drives development in order for diverse projects to conform ( or at least try to do it).

This is when the term `scaffolding` comes into play.

Scaffolding is a notion that originated in the construction industry; when we wish to build, repair, or change anything, we need scaffolding surrounding the project to help keep it stable.

This principle is comparable in computer science: before starting a project, we need a ready framework that allows us to continue in an orderly manner during development.

So here we have `cookiecutter`.

Cookiecutter is a tool that lets you construct a Python project from scratch using an existing template (similar versions exist for many other programming languages and editors).

[https://github.com/cookiecutter/cookiecutter](https://github.com/cookiecutter/cookiecutter)

Documentation: [https://cookiecutter.readthedocs.io/en/1.7.2/](https://cookiecutter.readthedocs.io/en/1.7.2/)

Cookiecutter usage:

- You choose a template to use for the project. 
- Cookiecutter is opened with the project's path, and the tool will ask you some questions to personalize the project's construction.
- Scaffolding with cookiecutter will produce the template for you.

We put in cookie cutters (better to do it with pipx in order to use it globally everywhere)

```bash
pipx install cookiecutter
```
Curated list of possible templates for your projects (you can find many online)

- [https://github.com/cookiecutter/cookiecutter#a-pantry-full-of-cookiecutters](https://github.com/cookiecutter/cookiecutter#a-pantry-full-of-cookiecutters)

```bash
#Cloniamo un progetto con cookiecutter
cookiecutter https://github.com/audreyr/cookiecutter-pypackage
```

Cookiecutter is a highly valuable tool, but you must be cautious about how you use it and which tasks you use it for. It frequently installs and downloads a large number of items that we do not require or that are redundant.

The idea is to choose projects that are appropriate for you depending on the project you intend to use (small, medium, large). Alternatively, create templates for your projects or organization so that everyone is on the same page about what you want to accomplish.

## Build a cookiecutter template from scratch

Let's have a look at how to make your own simple template with cookiecutter.

The documentation in this area is not very good and is out of current, however numerous examples may still be found online.