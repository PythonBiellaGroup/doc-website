+++
title = "Project Structure"
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

# Project Structure

How should a Python project be organized?

This is certainly a fairly common question, but it is also extremely difficult to answer because there is no proper answer.

Python does not require the adoption of a certain structure, but there are some best practices to bear in mind and considerations you may (and frequently should) make.

In Python, a **Module** is a container that houses all of the functions or classes that you need to import elsewhere in order to reuse what you've written.

When dealing with modules and other libraries or code, the most important thing to remember is to keep two mistakes in mind inside a project.

- `ModuleNotFoundError` : That is, when the file (module) you want to import does not exist or is not accessible.
- `ImportError` when there are bug knows as **circular imports**

When you import a module in Python, Python will seek for dependencies (the modules you wish to import) in three places:

1. Installation and dependencies: this refers to all of the default directories associated with the installed pip packages.
2. Additional pathways defined in the environment variable: `PYTHONPATH`
3. In the directory containing the **scripts needed to launch the interpreter**. In other words, if you execute `python ~/ module/scripts/server.py,` Python will search for modules to import within `~/ module/scripts/`.
4. If you use the `python` or `ipython` command to start an interactive session with Python, the directory where you were at the time the command was started will be utilized.
1. 
To examine the paths where Python will seek for modules, perform the following:

```bash
import sys
print(sys.path)
```
Whether you receive a `ModuleNotFoundError`, try executing the command above to see if it contains the folders you wish to use and which should be present.

In such instance, try doing imports on the `PYTHONPATH` to include your folders, or try `sys.path.append ("/module/scripts")` (it's a bit of a trick, but it could help to fix the problem).