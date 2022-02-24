---
title: "Add tails to terminal"
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

A very interesting feature of Visual Studio Code is the addition of the command `code file or folder>` to the terminal, which opens a vscode window based on either file or folder on which you want to work (for example, by doing `code`. you may open the current cartella within vscode).

To do so, open the Command Palette and execute (closely) the following command: `Shell command: Add the command 'code' to the PATH`

On Windows, you may add the functionality by flagging `Add to PATH` during the vscode installation process.