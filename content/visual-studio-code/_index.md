+++
title = "Visual Studio Code"
date = 2021-03-28T20:10:53+02:00
weight = 5
chapter = true
pre = "<b>5. </b>"
tags = ["vscode","ide", "settings", "estensioni"]
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

# Visual Studio Code

Un code editor è lo strumento essenziale per ogni programmatore e lo strumento con cui spendiamo la maggior parte del tempo.

La scelta di un editor con il quale scrivere codice è spesso un tema molto sensibile che suscita spesso molte diatribe tra i programmatori.

Come sapete ci sono moltissimi editor e siete liberi di utilizzare quello che più vi piace, ma dopo diversi anni passati ad utilizzare Sublime Text e Pycharm vi suggerisco vivamente di utilizzare Visual Studio Code. (Non voglio aprire la parantesi EMACS o Vim altrimenti è la fine..)

## Perchè Visual Studio Code?

Visual Studio Code è negli ultimi anni l'editor per la scrittura di codice più utilizzato e sicuramente più famoso

Survey del 2019 di Stack Overflow (nel 2020 non è stata fatta)

Vediamo quindi assieme alcuni vantaggi nell'usare vscode

- È OpenSource
- Si può usare su qualsiasi sistema operativo (anche via web come server)
- Potete usare tutti i linguaggi che volete
- È semplice, ma altamente performante
- È veloce
- È estremamente customizzabile grazie a tantissime estensioni
- Viene impiegato in tantissimi contesti lavorativi
- È largamente utilizzato e molto ben documentato
- Possibile fare sviluppo remoto
- È possibile fare live coding e pairwase coding anche a distanza
- Le vostre estensioni e impostazioni possono essere sincronizzate tra diversi dispositivi

Questi sono alcune delle mie considerazioni, ovviamente non ho benchmark rispetto altri editor sotto mano, vi invito comunque ad utilizzarlo e provarlo.

Rispetto a Pycharm c'è però una feature che mi manca moltissimo durante lo sviluppo, ovvero la possibilità di fare refactoring del codice in molto smart come succede appunto su Pycharm. Pur troppo la fase di refactoring su vscode è ancora spesso legata molto ad attività manuali e non ci sono tutti gli automatismi necessari.

La cosa che mi piace di più di VSCode è il giusto bilanciamento tra produttività e facilità, anche per chi inizia a scrivere codice.

Estensioni suggerite da installare con il loro ID di Visual Studio Store
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


Su VSCode segnaliamo anche altre configurazioni utili (che verranno discusse nelle sezioni precedenti) come: 
- autosalvataggio automatico dei file
- uso flake8 come linter
- black come strumento per formattare automaticamente il codice al salvataggio
- bandit per controlli sulla sicurezza.
- devcontainers
- configurazioni del debugger
- configurazione dei virtual environments
- configurazioni per lo sviluppo remoto

