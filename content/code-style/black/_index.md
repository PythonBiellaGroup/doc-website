---
title: "Black"
date: 2021-03-28T23:54:10+02:00
summary: ''
weight: 100
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

[https://black.now.sh/](https://black.now.sh/)

Black è un code formatter, prende i propri files e li formatta in accordo con PEP8 e PEP257 con alcune altre regole addizionali (ad esempio converte apostrofo singolo in apostrofo doppio).

Permette di essere configurato (ad esempio mettendo `--skip-string-normalization` per preservare gli apostrofi singoli).

Black è uno strumento molto discusso e a volte molto aggressivo, ma usandolo in un team consente di uniformare la scrittura del codice rendendolo comune.

Installare e usare Black

```bash
#installare black
pip install black

#tuttavia è consigliato utilizzare pipx
pipx install black
```

Formattare un progetto

```bash
black my_project #my_project = folder di progetto
```

Inoltre è possibile impostare black su vscode in modo da configurare lo styling al salvataggio 

Per farlo è necessario andare nelle impostazioni (settings) e modificare l'impostazione: format on save, in particolare: `python: formatting provider`

[https://marcobelo.medium.com/setting-up-python-black-on-visual-studio-code-5318eba4cd00](https://marcobelo.medium.com/setting-up-python-black-on-visual-studio-code-5318eba4cd00)