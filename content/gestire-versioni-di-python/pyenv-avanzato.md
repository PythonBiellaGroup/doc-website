---
title: "Pyenv avanzato"
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

In questa sezione avanzata sono presenti appunti, best practice e guide per approfondire tutto ciò che riguarda Pyenv

## Documentazione utile

[https://realpython.com/intro-to-pyenv/](https://realpython.com/intro-to-pyenv/)

Pyenv con poetry

[https://blog.jayway.com/2019/12/28/pyenv-poetry-saviours-in-the-python-chaos/](https://blog.jayway.com/2019/12/28/pyenv-poetry-saviours-in-the-python-chaos/)

Guida per configurare pyenv su Mac

[https://opensource.com/article/20/4/pyenv](https://opensource.com/article/20/4/pyenv)

Notes su un Github Gist

[https://gist.github.com/Geoyi/f55ed54d24cc9ff1c14bd95fac21c042](https://gist.github.com/Geoyi/f55ed54d24cc9ff1c14bd95fac21c042)

Pyenv è un gestore di installazione di python. Permette di installare e eseguire più installazioni di python sulla stessa macchina.

Pyenv gestisce le differenti versioni di python per te, in modo da evitare il chaos di dipendenze, versioni e installazioni illustrato nell'immagine iniziale.

**Perchè non utilizzare python installato di default nel proprio sistema operativo?**
- Perchè possono creare problemi nei progetti, ognuno ha la propria versione e ci possono essere problemi di migrazione e riproducibilità quando si usano in contesti di produzione.

**Cosa ci consente di fare pyenv? (flusso operativo)**

1. installare Python nel proprio user space
2. installare versioni multiple di python
3. specificare quale esatta versione di python utilizzare per un progetto e/o attività
4. cambiare tra le diverse versioni installate facilmente

![PythonPyramid](./images/python-pyramid.png)

## Installare Pyenv

Per installare Pyenv vi rimandiamo alla documentazione ufficiale su Github.  
Questo perchè le modalità di installazione cambiano a seconda della versione e del sistema operativo e stare al passo con gli aggiornamenti è sempre complicato.

Più avanti in questa guida trovate esempi di utilizzo con Pyenv più avanzati.

La guida di riferimento per l'installazione la potete trovare: [qui](https://github.com/pyenv/pyenv#installation)

**Verificare installazione di Pyenv**

Una volta installato e configurato correttamente sul vostro terminale terminale fare:

```bash
pyenv --version
```

### Install Python

Visualize python versions

```bash
pyenv install --list | grep " 3\.[678]"
```

```bash
pyenv install -v 3.7.2
```

Visualizzare dove vengono installate le varie versioni su Python

```bash
ls ~/.pyenv/versions/
```

Disinstallare una versione di Python

```bash
pyenv uninstall <version>
```

Ogni volta che su windows (e altri sistemi operativi) si installa una nuova versione di Python con pyenv è importante anche fare rehash

```bash
#rehash to update shims
pyenv rehash
```

Disinstallare una versione di python

```bash
#visualizzare le versioni di pyenv installate
pyenv versions

#disinstallare una determinata versione
pyenv uninstall <versione>
```

## Usare una versione di Pyenv

```bash
#Visualize the installed (available) versions
pyenv versions

#Visualize the active version of python with pyenv
pyenv which python

#Set a global pyenv version
pyenv global <version>

#If you want to come back to the system default
pyenv global system
```

È anche possibile impostare una versione di pyenv python locale per ogni progetto facendo all'interno della cartella di progetto:

```bash
pyenv local <version>
```

Oppure impostare la versione di una determinata shell

```bash
pyenv shell <version>
```

### IMPORTANTE IN WINDOWS 10   
Dopo aver installato la versione di Python global di pyenv è necessario eliminare dalla variabile di ambiente **PATH** i riferimenti al Python base installato inizialmente.  

## Virtualenvs with pyenv

Pyenv ha un bellissimo plugin chiamato: `pyenv-virtualenv` che consente di gestire appunto i vari virtualenv in modo semplice.

Ci sono diversi modi per gestire un virtualenv (pyenv consente di gestirli tutti e 3 in modo molto semplice e comodo)

- **pyenv** manages multiple versions of Python itself.
- **virtualenv/venv** manages virtual environments for a specific Python version.
- **pyenv-virtualenv** manages virtual environments for across varying versions of Python.

Creare un virtualenv

```bash
pyenv virtualenv <python_version> <environment_name>

#<pythonversion> is optional
```

Attivare un virtualenv

```bash
pyenv local myproject

#verify python version
pyenv which python

#verify pip version
pyenv which pip
```

È quindi possibile attivare o disattivare un particolare ambiente (virtualenv) (un po' come succede con anaconda)

```bash
pyenv activate <environment_name>

pyenv deactivate
```

Con pyenv è anche possibile utilizzare più versioni di python contemporaneamente...

## Pyenv with Poetry

[https://blog.jayway.com/2019/12/28/pyenv-poetry-saviours-in-the-python-chaos/](https://blog.jayway.com/2019/12/28/pyenv-poetry-saviours-in-the-python-chaos/)

### Bonus: utilizzare oh-my-zsh

È possibile utilizzare pyenv come plugin su oh-my-zsh in modo molto comodo inserendo `pyenv` all'interno dei plugin nel file di configurazione.

**Informazione:** Impedire a conda di partire di default

`conda config --set auto_activate_base false`

# Librerie base da installare

Elenco delle librerie base da installare (necessario creare progetto base per configurare queste librerie)

- Bandit
- Black
- Poetry
- Flake8
- Mypy
- Isort
- Pylint
- Pytest

A tal proposito sui vostri progetti suggeriamo di utilizzare Poetry per gestire le dipendenze e le librerie necessarie (sia di sviluppo che di produzione.
