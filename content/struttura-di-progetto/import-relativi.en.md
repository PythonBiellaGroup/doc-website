---
title: "Relative Imports"
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

There exist mainly a couple of ways to import Python modules

- **Absolutes** Import : `from module/models/user import get_user`
- **Relative** Import : `from ..models/user import get_user`

Both methods have pros and cons; nevertheless, I prefer Absolute Import since it is easier to understand and apply (making the code much cleaner and compliant).

Also, if you utilize relative imports, you may see the following error:

`Value Error: attempted relative import beyond top-level package`

This occurs when attempting to import something from a folder other than the project's (From a parent folder outside the root.

There are numerous solutions to this problem, but the suggestion remains consistent: utilize absolute imports as much as feasible.

⚠ Attention ⚠  NEVER USE THE * TO IMPORT FUNCTIONS OR MODULES.