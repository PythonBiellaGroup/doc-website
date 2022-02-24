---
title: "Pyenv-virtualenv"
date: 2021-06-24T19:48:12+02:00
weight: 200
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

Pyenv, in conjunction with a `pyenv-virtualenv` module, provides an even more powerful tool for creating virtual environments.

```bash
# Create virtual env
pyenv virtualenv 3.7.4 my-project

# List virtual venvs
pyenv virtualenvs

# Activate venvs
pyenv activate my-project

# deactivate venvs
pyenv deactivate
```
Other helpful and interesting utilities than virtualenv and pyenv-virtualenv include:


- conda (which also includes the 'conda' package manager), which is quite intrusive.
- the virtualfish
virtualenvwrapper
- pipenv: featured in many tutorials, but it is very badly maintained (the current version dates back to 2018 with 300+ outstanding issues) and can create various difficulties in a project (along with several debates associated to the project: [https://github.com/pypa/pipenv/issues/4058](https://github.com/pypa/pipenv/issues/4058))
- pipx: to consolidate and centralize dependencies (sometimes called central dispatchement)