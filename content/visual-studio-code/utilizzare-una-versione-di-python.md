---
title: "Utilizzare una versione di Python"
date: 2021-03-28T23:54:10+02:00
summary: ''
weight: 200
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

Quando siete all'interno di un progetto e aprite un file .py vi verrà chiesto di utilizzare una particolare versione di python che potete anche visualizzarla in basso a destra su vscode (ovviamente dovete installare almeno l'estensione Python prima). Premendo sulla scritta potrete selezionare una determinata versione di Python.

Aprendo sempre la Command Palette (premendo il tasto `F1` oppure `CTRL + SHIFT + P` o facendo `View > Command Palette` ) potete scrivere : `> python: Select Interpreter` per selezionare l'interprete python che più vi aggrada (ad esempio il vostro .venv all'interno della cartella).

All'interno del progetto potete anche creare un file: `settings.json` all'interno della cartella `.vscode` in modo da specificare il path del vostro interprete

```bash
{
  "python.pythonPath": "/Users/jeydi/Progetti/mioprogetto/.venv/bin/python"
}
```