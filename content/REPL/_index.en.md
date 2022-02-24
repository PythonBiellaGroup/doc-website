+++
title = "REPL"
date = 2021-03-28T20:10:53+02:00
weight = 6
chapter = true
pre = "<b>6. </b>"
tags = ["REPL","ipython"]
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

### Sezione 6

# REPL
REPL stands for: READ - EVAL - PRINT - LOOP.

It refers to all of the tools that allow you to open a terminal version of Python and run code in real time, as well as see the results in real time.

The Python REPL, which is installed by default together with the Python version, is useful, but it is sometimes too rudimentary and inconvenient to use for more complex tasks.

There are other alternatives, the most common and popular of which being `iPython`, which is the same REPL that runs behind Jupyter Notebooks and allows you to use notebook-style writing.

It is possible to install and use iPython.

```bash
pip install ipython
# better with pipx
pipx install ipython
```
It is encouraged to utilize pipx since it is one of those tools that you should use all the time because it is mostly used to check out some functions or run some tests on the code before writing it.

### iPython Benefits

- Tab Autocompletion
- syntax highlighting
- automatic Indentation
- Magic commands
- many many other more