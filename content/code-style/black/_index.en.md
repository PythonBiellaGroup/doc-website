---
title: "Black"
date: 2021-03-28T23:54:10+02:00
summary: ''
weight: 100
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

[https://black.now.sh/](https://black.now.sh/)

Black is a code formatter which takes files and formats them acccording to PEP8 and PEP257 with some additional rules (i.e. single quote with double quote).

It allows also for custom configuration (`--skip-string-normalization` to preserve single quote) which is good since as we already stated code conventions are really not mandatory rules but _guidelines_.

Black is very opinionated and sometimes really criticized, but if you and your team mates take advatage of it is quickly coerce code to a single consistent style.

## Installation and Usage

```bash
# black installation 
pip install black

# better use with pipx
pipx install black
```

Formattina a project

```bash
black my_project # my_project = workig dir folder
```


Furthermore you can set black directly on VScode when saving files. This hopefully might save some time.

To do that it is necessary to go into VScode settings and change format on save, to `python: formatting provider`

A couple of walkthrough to get a grip on that:

[https://marcobelo.medium.com/setting-up-python-black-on-visual-studio-code-5318eba4cd00](https://marcobelo.medium.com/setting-up-python-black-on-visual-studio-code-5318eba4cd00)