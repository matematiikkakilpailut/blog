---
layout: post
author: "Olli Järviniemi"
title: "Polynomien yhteiset alkutekijät, osa 4: motivaatio"
math: true
excerpt_separator: "<!--jatkuu-->"

---

Tässä postauksessa esitetään motivaatio lauseen 1 todistuksen takana.

<!--jatkuu-->

**Sisällysluettelo**

1. [Osa 1 - johdanto](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAjohdanto.html)
2. [Osa 2 - esitiedot](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAesitiedot.html)
3. [Osa 3 - tulokset](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAtulokset.html)
4. Osa 4 - motivaatio
5. [Osa 5 - heikko versio](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAheikko.html)
6. [Osa 6 - yleinen tapaus](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAyleinen.html)
7. [Osa 7 - lause 2](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAlause2.html)
8. [Osa 8 - lause 3](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAlause3.html)
9. [Osa 9 - lause 4](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAlause4.html)
10. [Osa 10 - sovelluksia](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAsovelluksia.html)
11. [Osa 11 - lisäaiheita](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAlisaaiheita.html)

### Kysymys 2

Kysymyksenä 2 oli siis: onko $S(A) \cap S(B)$ ääretön kaikilla $A, B \in \mathbb{Z_c}[x]$? Esitetään tälle väitteelle todistus. Todistus ei ole minun, vaan voidaan löytää esimerkiksi artikkelista [On the prime divisors of polynomials](www.jstor.org/stable/2317521)

**Todistus**

Olkoot $\alpha, \beta$ jotkin $A$:n ja $B$:n juuret. Olkoon $\gamma$ sellainen, että $\mathbb{Q}(\alpha, \beta) = \mathbb{Q}(\gamma)$ (mahdollista Primitive element theoremin nojalla, kts. esitiedot). Olkoon $D$ luvun $\gamma$ minimaalinen polynomi. Osoitetaan, että $D$:llä on seuraava ominaisuus:

Kaikki paitsi äärellisen moni $D$:n alkutekijä on sekä $A$:n että $B$:n alkutekijä.
