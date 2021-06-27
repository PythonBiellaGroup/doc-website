---
title: "Pyenv avanzato"
date: 2021-03-28T23:54:10+02:00
summary: ''
weight: 200
draft: false

---

In questa sezione avanzata sono presenti appunti, best practice e guide per approfondire tutto ciò che riguarda Pyenv

## Documentazione utile

[https://realpython.com/intro-to-pyenv/](https://realpython.com/intro-to-pyenv/)

Pyenv with Poetry

[https://blog.jayway.com/2019/12/28/pyenv-poetry-saviours-in-the-python-chaos/](https://blog.jayway.com/2019/12/28/pyenv-poetry-saviours-in-the-python-chaos/)

Guida per configurare pyenv on Mac

[https://opensource.com/article/20/4/pyenv](https://opensource.com/article/20/4/pyenv)

Notes on a Github Gist

[https://gist.github.com/Geoyi/f55ed54d24cc9ff1c14bd95fac21c042](https://gist.github.com/Geoyi/f55ed54d24cc9ff1c14bd95fac21c042)

Pyenv is a python installation manager. It allows you to install and run multiple python installations, on the same machine.

Pyenv manages the different versions for you, so that you will avoid the chaos illustrated in the above picture. Don't ever again install a python version any other way!

Perchè non utilizzare python installato di default nel proprio sistema operativo? 

Perchè possono creare problemi nei progetti, ognuno ha la propria versione e ci possono essere problemi di migrazione e riproducibilità quando si usano in contesti di produzione.

Cosa ci consente di fare pyenv? (flusso operativo)

1. installare Python nel proprio user space
2. installare versioni multiple di python
3. specificare quale esatta versione di python utilizzare per un progetto e/o attività
4. cambiare tra le diverse versioni installate facilmente

![PythonPyramid](./images/python-pyramid.png)

## Installare Pyenv

Pyenv builds Python from source, which means you’ll need build dependencies to actually use pyenv. The build dependencies vary by platform

Il modo migliore per installare pyenv è quello di clonare direttamente il progetto dalla repository ufficiale e inserire all'interno delle variabili di ambiente il path dove avete clonato il progetto.

Questa modalità di installazione si può applicare su tutti i sistemi operativi.

Su windows si può comunque utilizzare choco oppure si può utilizzare brew per installarlo su mac.

Su Linux il modo migliore è sempre quello di passare tramite git.

**Ubuntu/Debian**

[https://www.liquidweb.com/kb/how-to-install-pyenv-on-ubuntu-18-04/](https://www.liquidweb.com/kb/how-to-install-pyenv-on-ubuntu-18-04/)

Installare pyenv su WSL: [https://www.techtronic.us/install-python-pyenv-on-wsl-ubuntu/](https://www.techtronic.us/install-python-pyenv-on-wsl-ubuntu/)

Installare i requisiti (se non già stato fatto)

```bash
#before it's important to update
sudo apt install update -y

#then install packages and other infos
sudo apt-get install -y git gcc make openssl libssl-dev libbz2-dev libreadline-dev libsqlite3-dev zlib1g-dev libncursesw5-dev libgdbm-dev libc6-dev zlib1g-dev libsqlite3-dev tk-dev libssl-dev openssl libffi-dev
```

Clonare la repository Git e inserire all'interno delle variabili di ambiente della shell i path relativi a pyenv.

```bash
#Clone the repository
git clone https://github.com/pyenv/pyenv.git ~/.pyenv

#or use the pyenv official installer (it's ok, simpler, but you can have problems)
curl https://pyenv.run | bash

##--BASH--
#Launch the following commands to add into env variables the installation
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n eval "$(pyenv init -)"\nfi' >> ~/.bashrc

##---ZSH----
#If you are using zsh
#You can use the bash commands also with zsh
echo 'PATH=$(pyenv root)/shims:$PATH' >> ~/.zshrc

#Reactivate the shell
#For bash
source ~/.bashrc
#For zsh
source ~/.zshrc

##Verify the installation
pyenv install --list

```

This will install `pyenv` along with a few plugins that are useful:

1. **`pyenv`**: The actual `pyenv` application
2. **`pyenv-virtualenv`**: Plugin for `pyenv` and virtual environments
3. **`pyenv-update`**: Plugin for updating `pyenv`
4. **`pyenv-doctor`**: Plugin to verify that `pyenv` and build dependencies are installed
5. **`pyenv-which-ext`**: Plugin to automatically lookup system commands

**Mac** 

```bash
#Required Homebrew
# Install pyenv.
brew install pyenv

#Now it's important to set the pyenv with the bash o zsh

##---BASH---
# Add pyenv initializer to shell startup script.
echo -e '\nif command -v pyenv 1>/dev/null 2>&1; then
  eval "$(pyenv init -)"
fi' >> ~/.bash_profile

# Reload your profile.
source ~/.bash_profile

##---ZSH----
#If you are using zsh
echo 'PATH=$(pyenv root)/shims:$PATH' >> ~/.zshrc

```

**Windows** (consigliato utilizzare una WSL - windows subsystem linux)

Attenzione: utilizzare Powershell in modalità amministratore per non avere problemi di compatibilità

Pur troppo bisogna utilizzare una versione diversa, non quella originale. È stato realizzata una distribuzione apposta sempre dai creatori di pyenv.

[http://evaholmes.com/how-to-set-up-pyenv-and-poetry-on-windows-10-for-python-project-management/](http://evaholmes.com/how-to-set-up-pyenv-and-poetry-on-windows-10-for-python-project-management/)

[https://github.com/pyenv-win/pyenv-win](https://github.com/pyenv-win/pyenv-win)

```bash
# Step 1: choose one of the two types of installations

# 1 - With chocolatey
choco install pyenv-win

# 2 - Install using Git (need to install git first)

#with powershell
git clone https://github.com/pyenv-win/pyenv-win.git "$HOME/.pyenv"

#with cmd
git clone https://github.com/pyenv-win/pyenv-win.git "%USERPROFILE%\.pyenv"
```

```bash
# Step 2

#Add this to Path System Environment Variables
C:\Users\Anguz\.pyenv\pyenv-win\bin
C:\Users\Anguz\.pyenv\pyenv-win\shims

####OLD STUFF NOT WORKING#####
#Add path to environment variables
[System.Environment]::SetEnvironmentVariable('PYENV',$env:USERPROFILE + "\.pyenv\pyenv-win\","User")
[System.Environment]::SetEnvironmentVariable('PYENV_HOME',$env:USERPROFILE + "\.pyenv\pyenv-win\","User")

#Add the possibility to launch the commands with the terminal
[System.Environment]::SetEnvironmentVariable('PYENV_HOME',$env:USERPROFILE + "\.pyenv\pyenv-win\","User")

#Remember to relaunch the terminal after this commands
```

**Verificare installazione di Pyenv**

Da terminale fare

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