---
title: "Pipx"
date: 2021-06-24T19:48:38+02:00
weight: 500
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

"A project should have its own dependencies and should rest on its own legs, it should be atomic."

Well, that is certainly true, but it is even truer that there are some libraries that are pretty always used thoroughout your projects. In this case these libraries should be somewhat global to you system instead of local. 

An example could be linter and code formatters e.g. `black` or `flake8`

Thankfully there is `pipx` which creates a "global version" of the library you are installing, making it available at any time in any venv.

[https://github.com/pipxproject/pipx](https://github.com/pipxproject/pipx)

For the most part when you are installing libraries that you are willing to share for almost any project you are jumping into you should consider running `pipx install my_package`  instead of  `pip install my_package`


```bash
# list all libraries
pipx list

# remove a package
pipx uninstall my_package

# launch a library installed
pipx run black my_file

# you can also run a specific version
pipx run --spec black==18.3a1 black --version
```

Whenever you are launching `pipx run my_package` what happens is a venv is created, the command proptly executed and then immeditately destroyed.

On VScode there a _una tantum_ setting to make pipx working

```bash
# install falke
pipx install flake8

# path where flake is installed in
which flake8
<path>

# copy the bin path and pass to VScode settings.json
"python.linting.flake8Path": "/Users/YOUR_USERNAME/.local/bin/flake8"
```