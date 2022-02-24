# Modern Python Development

Sito web della community PythonBiellaGroup che ha l'obiettivo di raccogliere la conoscenza e tutto quello che viene raccolto dalla community legato a librerie, metodi e tecnologie sempre legate a Python all'interno di uno strumento fruibile online da tutti e tradotto in Italiano.

Il Sito web è disponibile online a questo indirizzo:
- https://pythonbiellagroup.it

Il sito è stato costruito utilizzando **Hugo** che è uno static site generator dove gli articoli presenti sul sito vengono creati utilizzando dei file markdown.

Per segnalare modifiche, problematiche o qualsiasi altra informazione consigliamo di interagire con le **Github Issue** di questa repository.

Per qualsiasi altra modifica legata al tema e al funzionamento generale di Hugo (framework su cui si basa il sito web) è consigliato leggere la documentazione di riferimento dello strumento:
- https://gohugo.io/documentation/

## Features già implementate

- costruzione e deploy del sito su un dominio custom
- code-styling
- come gestire le dipendenze su python (poetry, pip, pipenv, pipx, virtualenv)
- come gestire differenti versioni di python (pyenv)
- materiale utile di approfondimento
- Python REPL
- come strutturare un progetto
- visual studio code

## Prossime features che verranno implementate

- costruire un make file
- come creare un pacchetto python
- miglioramento sezione vscode
- aggiunta dev container su vscode
- traduzioni in inglese
- nuova sezione python base con guide e suggerimenti per iniziare
- documentare il codice (con mkdocs e sphinx)
- template di python (python-skeleton)
- miglioramento della sezione su cookiecutter
- come strutturare il codice python (aggiunta a come strutturare un progetto)
- migliorare sezione di code styling
- docker containers e compose con python
- ci/cd con python (gitlab e github)
- creare test con pytest
- type checking
- come usare python su r (esempio con librerie sui dati)

- miglioramento url e indicizzazione (con aggiunta di google analytics)
- miglioramento traduzione in inglese
- miglioramento del readme

## Come collaborare?

Se vuoi aiutarci nel mantenere questo sito consigliamo di guardare le issue aperte su github e contribuire nella loro risoluzione, oltre a segnalare nuove issue.

**Per fare delle modifiche**
- Controlla di avere hugo installato: https://gohugo.io/getting-started/installing/
- Clona il progetto
- Fai le modifiche (i file markdown corrispondono al contenuto)
- Testa le tue modifiche lanciando il server in locale facendo: `hugo serve -D`
- Builda il sito lanciando il comando: `hugo` verranno creati gli statici che andranno poi utilizzati da Github Pages per visualizzare il sito
- Crea una pull request (o se sei un amministratore pusha il codice sulla repository)
- Non dimenticare di notificare il tuo lavoro sul nostro canale telegram


Grazie mille!


## Ringraziamenti

Per questo progetto ringraziamo tutta la community di Python Biella Group, in particolare:
- Andrea Guzzo: per il supporto nell'organizzazione
- Mario Nardi: per il supporto nell'organizzazione
- Maria Teresa Panunzio: per il supporto nell'organizzazione
- Calogero Galipò: per l'aiuto nella costruzione del sito
- Andrea Biancini: per la revisione di alcune sezioni
- Niccolo Salvini: per le traduzioni in inglese