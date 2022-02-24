+++
title = "Code Styles"
date = 2021-03-28T20:10:53+02:00
weight = 4
chapter = true
pre = "<b>4. </b>"
tags = ["versions","code","style"]
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

### Section 4

# Code Style

When you are collaborating on a code project with teammates It is highly recommended to agree on a same code style. That would directly help to quickly grasp others code and still being on the trail when code is left behign for a while.


In Python we have two styles:

- PEP8 = Default python style guide
- PEP257 = Docstring style guide

Some coding rules according to PEP8

- indentation is made with 4 consecutive space characters
- there are specific requirements for paarenthesis indentation
- each line of code should not be longer than 79 characters & 72 characters for code documentation
- import statements should be specified with a precise structure (isort)
- and many other more

Take a look at PEP8 guidelines https://pep8.org, https://www.python.org/dev/peps/

However PEP8 guidelines are not bible and many things are questionable. The span of flexibility sometimes might create some confusion, so be aware that rules are up there but do not expect to follow them religiously.
