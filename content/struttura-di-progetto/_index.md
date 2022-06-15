+++
title = "Struttura di progetto"
date = 2021-03-28T20:10:53+02:00
weight = 3
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

# Struttura di progetto
Come strutturare un progetto in Python? 

Questa ovviamente è una domanda molto comune, ma allo stesso tempo molto difficile, non esiste una risposta corretta.

Python non forza l'utilizzo di una determinata struttura, tuttavia ci sono alcune best practice che è possibile tenere a mente e alcune considerazioni che si possono (e spesso devono) fare.

Un **Modulo** in Python è un contenitore che racchiude tutte le vostre funzioni o classe che vi serve importare da un'altra parte in modo da riciclare quello che avete scritto.

Quando si lavora con i moduli e con altre librerie o codice la cosa più importante è prestare attenzione a due errori all'interno di un progetto

- `ModuleNotFoundError` : ovvero quando il file (modulo) che si cerca i importare non esiste o non è raggiungibile
- `ImportError` quando ci sono errori di **circular imports**

Una cosa importante con Python è che quando si importa un modulo Python cercherà le dipendenze (i moduli che si vuole importare) in 3 posti:

1. Installazione e dipendenze: ovvero tutte le default folders legate ai pacchetti pip installati
2. Alcuni path addizionali specificati nella variabile d'ambiente: `PYTHONPATH`
3. Nella directory contenente gli **script che si usano per invocare l'interprete**. In altre parole se si lancia `python ~/modulo/scripts/server.py` Python cercherà i moduli da importare all'interno di `~/modulo/scripts/` .
4. Se si lancia una sessione interattiva con python (lanciando il comando `python` o `ipython` ) verrà utilizzata la directory dove ci si trova al momento del lancio del comando.

Un modo efficace per verificare i path dove python cercherà gli eventuali moduli è fare:

```bash
import sys
print(sys.path)
```

Se si ottiene `ModuleNotFoundError` la prima cosa è provare a lanciare il comando sopra per verificare se contiene le directory che si vuole utilizzare e che dovrebbero essere lì.

In quel caso bisogna cercare di agire sugli import, sul `PYTHONPATH` per includere le proprie directory oppure provare a fare `sys.path.append("/module/scripts")` (è un po' un trick, ma potrebbe aiutare a risolvere la soluzione).