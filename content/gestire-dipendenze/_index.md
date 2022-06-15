+++
title = "Gestire Dipendenze"
date = 2021-03-28T20:10:53+02:00
weight = 2
chapter = true
tags = ["versions","venv","dipendenze"]
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

# Gestione delle dipendenze

Per gestire le dipendenze da Python 3.3 esiste un built-in module chiamato **venv** che consente di creare dei virtualenv all'interno del vostro progetto.

Questa ovviamente è la "vecchia maniera" però è sempre funzionante

```bash
python -m venv my-virtualenv
```

Il comando consente di creare una directory `my-virtualenv` che contiene:

- python binary
- pip/easy_install/wheel binary
- activation script
- binary files utilizzate da Python

Per attivare un virtualenv si può fare:

```bash
#Su Linux o Mac
source ./my-virtualenv/bin/activate

#Su windows
my-virtualenv\Scripts\activate.bat

#Disattivare virtualenv
deactivate
```

I virtualenv sono molto comodi e si possono usare in combinazione con i file `requirements.txt`

Certamente è un metodo molto comodo, tuttavia ci sono degli strumenti più potenti ed efficaci per gestire il proprio ambiente.

## pyenv-virtualenv

Pyenv mette a disposizione uno strumento ancora più efficace per costruire ambienti virtuali attraverso un plugin `pyenv-virtualenv`

```bash
#Creare un virtualenv
pyenv virtualenv 3.7.4 my-project

#lista di tutti i virtual environments
pyenv virtualenvs

#attivare un virtualenv
pyenv activate my-project

#disattivare un virtualenv
pyenv deactivate
```

Oltre a virtualenv e pyenv-virtualenv ci sono altri strumenti molto utili e interessanti come:

- conda (che introduce anche il `conda` package manager) che è molto invasivo
- virtualfish
- virtualenvwrapper
- pipenv: molto citato in tantissimi tutorial, ma è veramente poco mantenuto (l'ultima versione risale al 2018 con 300+ issue aperte) e può causare diversi problemi in un progetto (oltre ad esserci diverse controversie legate al progetto: [https://github.com/pypa/pipenv/issues/4058](https://github.com/pypa/pipenv/issues/4058))
- pipx: per centralizzare alcune dipendenze