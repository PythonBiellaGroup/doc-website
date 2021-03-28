---
title: "Pyenv-virtualenv"
date: 2021-03-28T23:54:10+02:00
summary : ''
weight: 10
draft: false

---
Pyenv mette a disposizione uno strumento ancora più efficace per costruire ambienti virtuali attraverso un plugin `pyenv-virtualenv`

```bash
#Creare un virtualenv
pyenv virtualenv 3.7.4 my-project

#lista di tutti i virtual environments
pyenv virtualenvs

#attivare un virtualenv
pyenv activate my-project

#disattivare un virtualenv
pyenv deactivate
```

Oltre a virtualenv e pyenv-virtualenv ci sono altri strumenti molto utili e interessanti come:

- conda (che introduce anche il `conda` package manager) che è molto invasivo
- virtualfish
- virtualenvwrapper
- pipenv: molto citato in tantissimi tutorial, ma è veramente poco mantenuto (l'ultima versione risale al 2018 con 300+ issue aperte) e può causare diversi problemi in un progetto (oltre ad esserci diverse controversie legate al progetto: [https://github.com/pypa/pipenv/issues/4058](https://github.com/pypa/pipenv/issues/4058))
- pipx: per centralizzare alcune dipendenze