+++
title = "REPL"
date = 2021-03-28T20:10:53+02:00
weight = 6
chapter = true
pre = "<b>6. </b>"
tags = ["REPL","ipython"]
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

### Sezione 6

# REPL
REPL vuol dire: READ - EVAL - PRINT - LOOP.

Si riferisce a tutti gli strumenti che consentono di aprire una versione di Python daterminale e in modo dinamico provare codice e vederne subito il risultato in modo interattivo.

Python REPL che viene installato di default insieme alla versione di python è carino, ma spesso molto basico e non conveniente da utilizzare per cose complicate.

Ci sono alcune alternative, la più comune e popolare è certamente: `iPython` che è lo stesso REPL che gira dietro a Jupyter Notebooks e consente di utilizzare appunto la scrittura a Notebook.

Per installare e usare iPython è possibile fare

```bash
pip install ipython
#Oppure utilizzando pipx
pipx install ipython
```

Si raccomanda di utilizzare pipx perchè è uno di quelli strumenti che si vuole utilizzare globalmente perchè serve principalmente per provare alcune funzioni o per fare alcuni test sul codice prima di scriverlo.

### Vantaggi di iPython

- Autocompletamento tramite tab
- highlight della sintassi
- Indentazione automatica
- Magic commands
- Tanto tanto altro