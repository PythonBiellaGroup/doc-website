---
title: "Make us of a Python version"
date: 2021-03-28T23:54:10+02:00
summary: ''
weight: 200
draft: false

---
When you open a.py file within a project, you will be prompted to choose a certain version of Python, which you can also see at the bottom right of vscode. It is possible to pick a Python version by pressing on the writing.

Always open the Command Palette (by hitting the `F1` key or `CTRL + SHIFT + P` or typing `View> Command Palette`) and type: `> python: Select Interpreter` to choose the best Python interpreter for you ( for example your .venv inside the folder).

You may also define the location to your interpreter in the project by creating a file called'settings.json' within the.vscode folder.

```bash
{
  "python.pythonPath": "/Users/jeydi/Progetti/mioprogetto/.venv/bin/python"
}
```