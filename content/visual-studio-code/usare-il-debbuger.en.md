---
title: "debugger usage"
date: 2021-03-28T23:54:10+02:00
summary: ''
weight: 400
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

It is possible to create a specific configuration of debugger settings for each project in order to debug on vscode and so launch different files.

Furthermore, while you are in the debug section, VSCode provides a tool that allows you to generate a specific configuration based on the framework or functionality that you are attempting to use via a template.

Using this procedure, a file called `launch.json` will be created within the project's directory: `.vscode`, which may be corrupted.

An example of configuration (con flask e con un file singolo)

```bash
{
  // Use IntelliSense to learn about possible attributes.
  // Hover to view descriptions of existing attributes.
  // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Python: Current File",
      "type": "python",
      "request": "launch",
      "program": "${file}",
      "console": "integratedTerminal"
    },
    {
      "name": "Flask Backend",
      "type": "python",
      "request": "launch",
      "port": 8000,
      "host": "localhost",
      "program": "${workspaceFolder}/server.py",
      "console": "integratedTerminal",
      "env": {
        "API_ENDPOINT_PORT": "8000",
        "VERBOSITY": "debug",
        "PLANT": "demo"
      }
    }
  ]
} 
```