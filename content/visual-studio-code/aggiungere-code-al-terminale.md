---
title: "Aggiungere code al terminale"
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

Una feature molto interessante di visual studio code è l'aggiunta del comando `code <file_or_folder>`  all'interno del terminale che vi aprirà una finestra di vscode in base al file o alla cartella su cui volete lavorare (ad esempio facendo `code .` potrete aprire la cartella corrente all'interno di vscode).

Per farlo aprite la Command Palette e lanciate (cercando) il seguente comando: `Shell command: Install ‘code’ command in the PATH`

Su windows è possibile installare la funzionalità anche flaggando `Add to PATH` durante la fase di installazione di vscode.