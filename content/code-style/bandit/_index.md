---
title: "Bandit"
date: 2021-06-25T19:55:25+02:00
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

Bandit è uno strumento per trovare problemi di sicurezza più comuni all'interno del codice Python.

Utilizzandolo così com'è però, senza un'adeguata configurazione, fornisce anche un po' di falsi positivi.

Spendendo un po' di tempo a configurarlo correttamente per i vostri progetti è possibile avere informazioni utili riguardo:

- utilizzo insicuro di alcuni moduli
- possibili SQL Injection
- se il codice ignora silenziosamente alcune eccezioni
- e molto altro

È un utilissimo strumento soprattutto per principianti per revisionare il proprio codice.

Per usare bandit il consiglio è quello di installare l'estensione di Flake8 `flake8-bandit` in modo da non dover installare e usare bandit separatamente, ma integrandolo direttamente nel vostro progetto.