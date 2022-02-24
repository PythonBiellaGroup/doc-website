---
title: "Circular Imports"
date: 2021-03-28T23:54:10+02:00
summary: ''
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

## Circular Imports

This is a severe issue in a project, and the error arises when you try to import one module from another, and vice versa (creating a circularity in the imports).

```python
# file_a.py
from file_b import hello_world

def hello():
    return "hello"

def first_program():
    return hello_world()

first_program()
```

```python
# file_b.py
from file_a import hello

def hello_world():

    return hello() + " world"
```

When you are lunching `python file_a.py` you will encounter the following error:

```bash
Traceback (most recent call last):
  File "file_a.py", line 1, in <module>
    from file_b import hello_world
  File "/my_module/file_b.py", line 2, in <module>
    from file_a import hello
  File "/my_module/file_a.py", line 1, in <module>
    from file_b import hello_world
ImportError: cannot import name 'hello_world'
```

There are numerous solutions to address these circular import difficulties here, but be careful while developing your code to avoid these issues.