---
title: "Import relativi"
date: 2021-03-28T23:54:10+02:00
summary: ''
weight: 100
draft: false
---

Esistono due modi (principali) per importare moduli in Python

- Import **Assoluti**: `from module/models/user import get_user`
- Import **Relativi:** `from ..models/user import get_user`

Entrambi i modi hanno vantaggi e svantaggi, personalmente consiglio l'utilizzo di Import Assoluti perchè sono più facili da leggere e da utilizzare (rendendo il codice molto più pulito e compilant).

Anche perchè se si usano import relativi è possibile incappare in questo errore:

`Value Error: attempted relative import beyond top-level package`

Questo succede quando si cerca di importare qualcosa da una cartella al di fuori del progetto (Da una cartella padre al di fuori della root).

Ci sono diversi modi per sistemare questo problema, ma il consiglio è sempre lo stesso: cercate di utilizzare il più possibile import assoluti.

ATTENZIONE: NON USATE MAI LA * PER IMPORTARE FUNZIONI O MODULI