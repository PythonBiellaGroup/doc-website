+++
title = "Code Style"
date = 2021-03-28T20:10:53+02:00
weight = 4
chapter = true
pre = "<b>4. </b>"
tags = ["versions","code","style"]
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

### Sezione 4

# Code Style

Quando si lavora su progetti e si conivide il codice con un team di lavoro è importante cercare di mantenere uno stesso stile di scrittura del codice in modo da uniformarsi ed evitare di fraintendersi.

In Python esistono

- PEP8 = Default python style guide
- PEP257 = Docstring style guide

Alcuni esempi di PEP8:

- Quando spazi si usano per l'indentazione = 4 spazi
- Come indentare le parentesi
- Lunghezza della linea di codice predefinita (79 caratteri per il codice e 72 caratteri per i commenti e docstrings)
- Come configurare gli import
- ...

Tuttavia nonostante le linee guida di PEP8 ci sono molte cose su cui di può discutere e che non sono chiare, lasciando spesso anche troppa libertà.

Ecco che entrano in gioco alcune librerie che aiutano nella gestione della qualità del codice.

### Documentazione
- https://pep8.org
- https://www.python.org/dev/peps/