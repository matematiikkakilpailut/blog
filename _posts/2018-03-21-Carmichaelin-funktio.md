---
layout: post
title: "Carmichaelin funktio"
author: "Olli Järviniemi"
math: true
excerpt: >
  Carmichaelin funktio $\lambda$ määritellään niin, että $\lambda (p^k) = \phi(p^k)$ kaikilla parittomilla alkuluvuilla $p$ ja $k \ge 0$,
  $\lambda (2^k) = 2^{k-2}$ kaikilla $k > 2$.
---

<div class="hidden">
$\newcommand{\pyj}{\mathop{\rm pyj}}\newcommand{\syt}{\mathop{\rm syt}}$
</div>

Tämä on kirjoitettu harjoituksen vuoksi.

**Teoria**
Carmichaelin funktio $\lambda$ määritellään niin, että $\lambda (p^k) = \phi(p^k)$ kaikilla parittomilla alkuluvuilla $p$ ja $k \ge 0$, $\lambda (2^k) = 2^{k-2}$ kaikilla $k > 2$. Lisäksi $\lambda (2) = 1$, $\lambda (4) = 2$. Lambdafunktiolle pätee lisäksi $\lambda (ab) = \pyj(\lambda (a), \lambda (b))$, kun $\syt(a, b) = 1$.

$\lambda (n)$ on pienin kokonaisluku, jolla pätee ehto $a^{\lambda(n)} \equiv 1 \pmod{n}$ kaikilla $\syt(a, n) = 1$.

**Tehtävä**
Osoita, että seuraavat ehdot ovat ekvivalentit.
1. $ x^6 \equiv 1 \pmod{n}$ kaikilla $\syt(x, n) = 1$
2. $n$ jakaa luvun $504$

