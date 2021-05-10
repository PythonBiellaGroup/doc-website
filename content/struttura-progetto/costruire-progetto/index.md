---
title: "Costruire un progetto"
date: 2021-05-10T23:54:10+02:00
summary: ''
weight: 40
draft: false

---

# Come costruire un progetto con questi nuovi strumenti?

Vediamo assieme tutti i passi necessari per costruire un progetto con Python utilizzando gli strumenti visti in questa guida.

Questa guida ha come obiettivo quello di accompagnare persone che si approcciano per la prima volta a queste nuovo modo di realizzare progetti con python a realizzare una prima versione del progetto up and running.

Inoltre ha come obiettivo quello di portare facilmente altre persone del team ad utilizzare questi strumenti in modo da familiarizzare il più velocemente possibile, costituendo una valida reference per il progetto.

Qual ora ci fossero dei problemi, refusi o errori in questa guida non esitate a contattarci aprendo delle issue su gitlab o scrivendoci direttamente.

## Installare i requisiti

La prima cosa da fare è installare tutti gli strumenti necessari.

Ovviamente diamo per scontato che tutti voi abbiate una macchina Linux, Windows, MacOS con sopra installata una versione di Python, possibilmente uguale (o meglio superiore) a Python 3.6.X

### Installare Pyenv

Sebbene non indispensabile, ma estremamente consigliato, la prima cosa da fare è certamente installare pyenv in modo da rendere facile l'utilizzo e l'installazione di una particolare versione di python per un progetto.

### Installare Poetry


## Configurazione iniziale di Poetry nel progetto


## Installare le librerie
**Librerie di Development**
Le librerie di development sono tutte quelle librerie necessarie a sviluppare il codice sorgente, come ad esempio: linter, debugger, normalizzazione del codice, controllo di sintassi, ...

`poetry add -D flake8 flake8-isort flake8-builtins autopep8 pylint bandit black`

**Librerie di esplorazione dei dati**

È consigliato installare librerie di esplorazione dei dati (come ad esempio Jupyter) in modalità development se Jupyter non è un requisito fondamentale per utilizzare il progetto in produzione

`poetry add -D jupyter jupyterlab`

## Configurazione di Flake8



