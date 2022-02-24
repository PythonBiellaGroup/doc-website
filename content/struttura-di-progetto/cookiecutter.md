---
title: "cookiecutter"
date: 2021-03-28T23:54:10+02:00
summary: ''
weight: 300
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

Tornando al discorso originale di struttura di progetto in python (e in tanti altri linguaggi e/o framework) ogni progetto è differente, ma alcuni progetti condividono tra di loro alcuni elementi comuni.

Ad esempio spesso hanno un file con una lista di dipendenze e alcuni test, un'applicazione web ha bisogno di un "main", oppure abbiamo bisogno per il nostro team di avere una struttura che guidi lo sviluppo in modo da uniformarci tra diversi progetti (o almeno cercare di farlo).

Ecco qui che entra in gioco lo `scaffolding` .

Scaffolding (in italiano: **impalcatura**) è un concetto che arriva appunto dal settore delle costruzioni, quando vogliamo costruire qualcosa, ripararlo o modificarlo, abbiamo bisogno di un'impalcatura attorno al progetto che aiuti a tenerlo.

In Informatica questo concetto è simile: prima di costruire un progetto abbiamo bisogno di una struttura pronta che ci consenta di procedere in modo ordinato durante lo sviluppo.

Ecco quindi che entra in gioco: `cookiecutter`

Cookiecutter è uno strumento che consente di creare un progetto Python a partire da un template esistente (esistono versioni simili anche in tanti altri linguaggi di programmazione ed editor).

[https://github.com/cookiecutter/cookiecutter](https://github.com/cookiecutter/cookiecutter)

Documentation: [https://cookiecutter.readthedocs.io/en/1.7.2/](https://cookiecutter.readthedocs.io/en/1.7.2/)

Per utilizzarlo:

- Si seleziona un template da utilizzare per il progetto
- Si lancia cookiecutter con l'indirizzo del progetto e verranno chieste dal tool alcune domande per personalizzare la creazione del progetto
- Scaffolding con cookiecutter genererà il template per voi

Installiamo cookiecutter (meglio farlo con pipx in modo da usarlo globalmente dappertutto)

```bash
pipx install cookiecutter
```

Elenco curato di possibili templates per i vostri progetti (ne trovate molti online)

- [https://github.com/cookiecutter/cookiecutter#a-pantry-full-of-cookiecutters](https://github.com/cookiecutter/cookiecutter#a-pantry-full-of-cookiecutters)

```bash
#Cloniamo un progetto con cookiecutter
cookiecutter https://github.com/audreyr/cookiecutter-pypackage
```

Cookiecutter è uno strumento molto utile, ma bisogna fare attenzione a come lo si usa e a quali progetti si utilizzano. Spesso può installare e scaricare tantissime cose di cui non abbiamo bisogno o che sono ridondanti.

Il consiglio è di selezionare dei progetti che fanno per voi in base al progetto che state pensando di utilizzare (piccolo, medio, grande). Oppure scrivere dei template per i vostri progetti o organizzazione in modo da essere tutti d'accordo su quello che volete fare. 

## Costruire un proprio cookiecutter template

Vediamo alcuni passi per costruire un proprio template semplice con cookiecutter.

La documentazione a tal proposito non è fatta benissimo e manca di aggiornamenti, ma è comunque possibile trovare molti esempi online.