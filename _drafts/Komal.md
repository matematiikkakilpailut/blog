---
layout: post
author: "Olli Järviniemi"
title: "KöMaL ja ositusongelma"
math: true
excerpt_separator: "<!--jatkuu-->"

---

KöMaL on unkarilainen "matematiikkalehti". KöMaLin sivuilta [löytyy](https://www.komal.hu/verseny/feladatok.e.shtml) lisäksi paljon kilpailumatematiikan tehtäviä, vaihdellen helpohkoista hyvin haastaviin. Tässä postauksessa käydään läpi yksi näistä tehtävistä:

[Tehtävä (KöMaL, A647)](https://www.komal.hu/feladat?a=honap&h=201509&t=mat&l=en)

Olkoon $k$ epänegatiivinen kokonaisluku. Osoita, että vain äärellisen monella positiivisella kokonaisluvulla $n$ on olemassa joukot $A$ ja $B$, joilla $A \cup B = \lbrace 1, 2, \ldots , n \rbrace $, $A \cap B = \emptyset$ ja

$$\Big | \prod_{a \in A} a - \prod_{b \in B} b \Big | = k$$


<!--jatkuu-->

**Ratkaisu**

Tehtävän ratkaisu perustuu oleellisesti ottaen seuraavaan huomioon: jos $p$ on alkuluku, jolla $p \nmid k$, niin joukosta $\lbrace 1, 2, \ldots , n \rbrace $ jokaisen $p$:llä jaollisen termin tulee kuulua joko joukkoon $A$, tai jokaisen tulee kuulua joukkoon $B$.

Tätä ideaa on kuitenkin mahdoton soveltaa tapauksessa $k = 0$. Tämä tapaus on kuitenkin helppo ns. Bertrandin postulaatin avulla.

**Bertrandin postulaatti**

Kaikilla $n > 1$ lukujen $n$ ja $2n$ välillä on alkuluku.

Väitteen todistus (ja lukuisia yleistyksiä) löytyy netistä, esimerkiksi [Wikipediasta](https://en.wikipedia.org/wiki/Proof_of_Bertrand%27s_postulate).

Nyt, tapaus $k = 0$ todistuu sillä huomiolla, että $n!$ ei ole neliöluku millään $n > 1$, koska luvulla $n!$ on jokin alkutekijä, jonka eksponetti on $1$ Bertrandin postulaatin nojalla (lukujen $\frac{n}{2}$ ja $n$ välillä on olemassa alkuluku). Nimittäin, oletetaan että ositus toimii. Tällöin pätee

$$n! = \prod_{a \in A} a \prod_{b \in B} b= \Big( \prod_{a \in A} a \Big)^2$$

eli $n!$ on neliöluku, mikä on ristiriita.

Tutkitaan sitten tapaus $k > 0$. Olkoon $P$ kaikkien alkulukujen joukko, ja olkoon $k$:n alkutekijöiden joukko $K$ (huomaa, että $K$ voi olla tyhjä).

Valitaan $n$ hyvin suureksi, ja osoitetaan, ettei ositus onnistu (tulemme myöhemmin toteamaan, että tietyt osituksen mahdottomaksi todistavat epäyhtälöt pätevät tarpeeksi suurilla $n$). Tehdään vastaoletus: ositus onnistuu, eli on olemassa halutut $A$ ja $B$. Olkoon joukon $P \setminus K$ pienin alkio $p$. Ilman yleisyyden menettämistä voimme olettaa, että $p \in A$. Aiemmin esitetyn huomion nojalla kaikki $p$:n monikerrat, jotka ovat eninitään $n$, kuuluvat myös joukkoon $A$.

