---
title: "Import circolari"
date: 2021-03-28T23:54:10+02:00
summary: ''
weight: 20
draft: false

---

## Import circolari

Questo è un problema molto grave in un progetto e l'errore accade quando a partire da un modulo si cerca di importare l'altro e viceversa (crendo appunto una circolarità negli import).

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

Quando si lancia `python file_a.py` si avrà il seguente errore:

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

Ci sono anche qui molti modi per fixare questi problemi di import circolari, fate attenzione però a quando scrivete il codice in modo tale che non si verifichino questi problemi.