---
title: "Utilizzare una versione di Python"
date: 2021-03-28T23:54:10+02:00
summary: ''
weight: 200
draft: false

---
Quando siete all'interno di un progetto e aprite un file .py vi verrà chiesto di utilizzare una particolare versione di python che potete anche visualizzarla in basso a destra su vscode (ovviamente dovete installare almeno l'estensione Python prima). Premendo sulla scritta potrete selezionare una determinata versione di Python.

Aprendo sempre la Command Palette (premendo il tasto `F1` oppure `CTRL + SHIFT + P` o facendo `View > Command Palette` ) potete scrivere : `> python: Select Interpreter` per selezionare l'interprete python che più vi aggrada (ad esempio il vostro .venv all'interno della cartella).

All'interno del progetto potete anche creare un file: `settings.json` all'interno della cartella `.vscode` in modo da specificare il path del vostro interprete

```bash
{
  "python.pythonPath": "/Users/jeydi/Progetti/mioprogetto/.venv/bin/python"
}
```