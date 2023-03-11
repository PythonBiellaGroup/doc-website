---
title : "RUFF"
date : 2023-03-10T20:10:53+02:00
# weight : 110
# chapter : true
tags : ["ruff","rust"]
draft : false
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

## RUFF

**Ruff** è un linter per python estremamente veloce, scritto in Rust:

[Progetto Ruff](https://github.com/charliermarsh/ruff "Ruff")

Oltre alla sua velocità, la sua caratteristica principale è che è in grado di analizzare il codice python e di fornire informazioni utili per migliorare la qualità del codice.
E per fare questo utilizza una serie di regole che possono essere abilitate o disabilitate a piacimento.

Ruff può sostituire altre librerie ben note per la qualità del codice come:

* Flake8 e molti dei suoi plugins
* isort
* pydocstyle
* yesqa
* eradicate
* pyupgrade
* autoflake

Si può installare Ruff in vari modi ma il più semplice è:

```
pip install ruff
```

Si consiglia comunque di fare riferimento alla sua documentazione molto completa:

[Ruff Doc](https://beta.ruff.rs/docs/ "Ruff")

Ed è anche possibile fare delle prove al seguente link:

[Ruff Playground](https://play.ruff.rs/)

### Vantaggi di Ruff

* Estremamente veloce
* Tantissime regole di controllo
* Possibilità di correggere molte segnalazioni in automatico
* Estremamente configurabile
* Integrabile negli editor principali
* In rapida espansione e molti contributor.
