+++
title = "Visual Studio Code"
date = 2021-03-28T20:10:53+02:00
weight = 5
chapter = true
pre = "<b>5. </b>"
tags = ["vscode","ide", "settings", "estensioni"]
+++
# Visual Studio Code

A code editor is an essential tool for every programmer and the tool with which we spend the majority of our time.

The choice of an editor with which to write code is frequently a sensitive matter that sparks heated debate among programmers.

As you are aware, there are other editors available, and you are free to use whatever you like, but after several years of using Sublime Text and Pycharm, I highly advise you to use Visual Studio Code. (I don't want to open the EMACS or Vim brackets since it would mean the end...

## Why Visual Studio Code?

In recent years, Visual Studio Code has become the most popular and undoubtedly the most well-known editor for creating code.

2019 Stack Overflow poll (in 2020 it was not done)

So, let's look at some of the benefits of utilizing vscode together.


- It is open source.
- It is compatible with any operating system (even via the web as a server)
- You are free to use whatever language you choose.
- It's straightforward, yet quite effective.
- It's quick.
- It is highly configurable owing to a plethora of addons.
- It is employed in a variety of professional settings.
- It's extensively utilized and well-documented.
- Remote development is possible.
- Even at a distance, live coding and pairwise coding are feasible.
- You can synchronize your extensions and settings between devices.

These are some of my concerns; clearly, I have no benchmark against other editors to compare it to, but I still urge you to use and experiment with it.

However, there is one thing that I miss a lot during development when compared to Pycharm, and that is the ability to restructure the code in a really sensible way, as it does with Pycharm. Unfortunately, the refactoring process on vscode is still frequently tied to manual tasks, and not all of the essential automatisms are present.

The thing I appreciate best about VSCode is the proper blend of productivity and ease of use, especially for those who are just beginning out with coding.

Suggested extensions to be installed and their ids for VScode store
- bookmarks: (alefragnani.bookmarks)
- code spell checkers (streetsidesoftware.code-spell-checker)
- docker (ms-azuretools.vscode-docker)
- docs-markdown (docsmsft.docs-markdown)
- docs-preview (docsmsft.docs-preview)
- docs-yaml (docsmsft.docs-yaml)
- git graph (mhutchie.git-graph)
- git history (donjayamanne.githistory)
- git lens (eamodio.gitlens)
- indent-rainbow (oderwat.indent-rainbow)
- italian-code spell checker (streetsidesoftware.code-spell-checker-italian)
- jupyter (ms-toolsai.jupyter)
- jupyter keymap (ms-toolsai.jupyter-keymap)
- live-share (ms-vsliveshare.vsliveshare)
- markdown all in one (yzhang.markdown-all-in-one)
- material icon theme (pkief.material-icon-theme)
- postgreSQL (ms-ossdata.vscode-postgresql)
- pylance (ms-python.vscode-pylance)
- python (ms-python.python)
- python docstring generator (njpwerner.autodocstring)
- python indent (kevinrose.vsc-python-indent)
- rainbow brackets (2gua.rainbow-brackets)
- rainbow csv (mechatroner.rainbow-csv)
- remote development (bundle) (ms-vscode-remote.vscode-remote-extensionpack)
- render line endings (medo64.render-crlf)
- sqltools (mtxr.sqltools)
- swagger viewer (arjun.swagger-viewer)
- todo highlight (wayou.vscode-todo-highlight)
- todo tree (gruntfuggly.todo-tree)
- visual studio intellicode (visualstudioexptteam.vscodeintellicode)
- webhint (webhint.vscode-webhint)
- yaml (redhat.vscode-yaml)

On VScode we also highlight other useful configurations that are going to be covered in the following sections like:
- automated file saving -
-  use flake8 as a linter
-  black as a tool for automatically formatting the code at save
- Bandit for security checks.
- development containers
- Migration of the debugger
- virtual environment configuration
- Remote development
