---
title: "Pyenv"
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

Pyenv consente di gestire diverse versioni di python installate nella vostra macchina, consentendo di gestirle in modo molto semplice e veloce. 

È semplice e non troppo intrusivo, inoltre potete utilizzarlo su qualsiasi sistema operativo

- Consente di cambiare la **versione globale di python** oppure locale per ogni progetto o utente
- Consente di gestire una versione locale di ogni progetto con la propria specifica versione di python
- Permette di fare **override** della versione di Python come variabili d'ambiente (non dovete più gestirle a mano
- Consente di ricercare diverse versioni di python e gestirle (con tox)

Alcuni aspetti molto importanti

- Non ci sono problemi di bootstrap, è costruito utilizzando script shell puri
- Non è necessario caricarlo all'interno della propria shell, basta inserire la sua directory nelle variabili di ambiente e funziona "da solo"
- Consente inoltre (ed eventualmente) di gestire in moldo più efficiente i virtualenviroments

Documentazione fatta molto bene con moltissimo supporto online

- [https://github.com/pyenv/pyenv](https://github.com/pyenv/pyenv)

Comandi da far vedere

```bash
# Lista di tutte le versioni disponibili
pyenv install --list

# Installare una specifica versione di python
pyenv install 3.7.4

# Visualizzare tutte le versioni installate (di pyenv)
pyenv versions

# Impostare una determinata versione di python globale (usata da tutto il sistema operativo)
pyenv global 3.7.4

# Impostare una versione di python locale
pyenv local 3.7.4 #viene creato un .python-version file
# Cancellando il file .python-version si cancella la versione locale
rm .python-version

#Cambiare la versione solamente per la sessione di shell esistente
pyenv shell system
```

Con pyenv abbiamo risolto il problema di cambiare velocemente e in modo efficace la versione di python installata sulla propria macchina.

Rimane il problema di gestire le dipendenze (le librerie) all'interno di progetti diversi.

Python ha un grande problema: **non si possono avere versioni multiple della stessa libreria (package)** installata in una determinata versione di Python.

Ecco che entrano in gioco i **virtualenvironments** 

È importante utilizzare separati virtualenvs per ogni progetto che si fa su python, iniziando ad esercitarsi da quelli più semplici.