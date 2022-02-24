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

Bandit is a tool to find code security issues in Python.

Bandit is actually great, but it has to be configured according to code guidelines in order to discriminate security false positives. 

With a bit of time you can set up a bandit configuration having

- secure module usage
- SQL injection disagnosis
- code which silently suppress exceptions
- many other more features

Moreover it is very useful for beginners since it pops up suggestion while you are writing code.

To use Bandit we would suggest to install the  `flake8-bandit` extension.