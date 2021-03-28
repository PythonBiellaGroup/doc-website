---
title: "Usare il debugger"
date: 2021-03-28T23:54:10+02:00
summary: ''
weight: 4
draft: false

---
Per usare il debugger su vscode e quindi lanciare diversi file è possibile creare per ogni progetto una particolare configurazione di impostazioni che verranno utilizzate dal debugger.

Inoltre VSCode quando andate sulla sezione di debug mette a disposizione uno strumento che consente di generare una particolare configurazione in base al framework o funzionalità che state cercando di usare tramite un template

Con questa procedura verrà costruito un file: `launch.json` all'interno della directory di progetto: `.vscode` che potrebbe essere nascosta.

Un esempio di configurazione (con flask e con un file singolo)

```bash
{
  // Use IntelliSense to learn about possible attributes.
  // Hover to view descriptions of existing attributes.
  // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Python: Current File",
      "type": "python",
      "request": "launch",
      "program": "${file}",
      "console": "integratedTerminal"
    },
    {
      "name": "Flask Backend",
      "type": "python",
      "request": "launch",
      "port": 8000,
      "host": "localhost",
      "program": "${workspaceFolder}/server.py",
      "console": "integratedTerminal",
      "env": {
        "API_ENDPOINT_PORT": "8000",
        "VERBOSITY": "debug",
        "PLANT": "demo"
      }
    }
  ]
} 
```