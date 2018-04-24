---
layout: post
author: "Olli Järviniemi"
title: "Kiinatehtävä, osa 3"
math: true
excerpt_separator: "<!--jatkuu-->"
---


Tässä postauksessa käsitellään seuraavan tehtävän ratkaisu:

**Kiinan IMO-joukkueen valintakoe 2, 2015, tehtävä 6**

Osoita, että on olemassa äärettömän monta $n \in \mathbb{Z_+}$ joilla $n^2 + 1$ ei ole jaollinen millään alkuluvun neliöllä (engl. squarefree)

<!--jatkuu-->

**Ratkaisu**

On luonnollista tutkia, milloin väite ei päde, eli milloin pätee
$n^2 + 1 \equiv 0 \pmod{p^2}$ jollain alkuluvulla $p$. Tämä tietysti vaatii, että $n^2 + 1 \equiv 0 \pmod{p}$, eli $p \equiv 1 \pmod{4}$. Tämä ei kuitenkaan vielä anna riittävästi tietoa: ensinnäkin, onko jokaisella $p \equiv 1 \pmod{4}$ olemassa ratkaisu kongruenssiyhtälölle $x^2 + 1 \equiv 0 \pmod{p^2}$, ja toisekseen, kuinka monta (keskenään epäkongruenttia) ratkaisua yhtälöllä on? Nämä kysymykset ovat helppoja vastata:

**Lemma 1**
Kongruenssiyhtälöllä $x^2 + 1 \equiv 0 \pmod{p^2}$ on täsmälleen kaksi keskenään epäkongruenttia ratkaisua kaikilla alkuluvuilla $p \equiv 1 \pmod{4}$

**Todistus**
Kirjoitetaan $x = pk + y$, missä $0 \le k < p$ ja $0 \le y < p$ ovat muuttujia. Yhtälö muuttuu muotoon

$2pk + y^2 + 1 \equiv 0 \pmod{p^2}$

Saamme luotua kaksi ratkaisua: valitaan $y$ niin, että $y^2 \equiv -1 \pmod{p}$ (tämä on mahdollista). Kirjoitetaan $pt = y^2 + 1$ Nyt tulee enää valita $k$ niin, että $2pk + pt \equiv 0 \pmod{p^2}$, eli $k \equiv \frac{-t}{2} \pmod{p}$. Sillä $y$:lle on kaksi eri vaihtoehtoa, myös $x$:lle on kaksi eri vaihtoehtoa.

Todistetaan sitten, että useampaa ratkaisua ei ole. Olkoon $f(x) = x^2$. Oletetaan, että $f(a) \equiv f(b) \equiv -1 \pmod{p^2}$. Pyritään todistamaan, että $a \equiv \pm b \pmod{p^2}$. Lemman tulos seuraa tästä.

Pätee $0 \equiv f(a) - f(b) \equiv a^2 - b^2 \equiv (a-b)(a+b) \pmod{p^2}$

Jos $p^2 \mid a - b$, väite pätee, samoin jos $p^2 \mid a + b$. Voiko päteä $p \mid a - b$ ja $p \mid a + b$? Ei, sillä tästä seuraisi $p \mid 2a$, eli $p \mid a$. Mutta oletimme $f(a) \equiv -1 \pmod{p^2}$, joten tämä on ristiriita.

**Huomautus**
Tarvitsemme lemmasta vain osuutta "enintään kaksi ratkaisua".


Tehtävänannon väite seuraa nyt helpolla todennäköisyysargumentilla: jos valitsemme satunnaisen positiivisen kokonaisluvun $n$ (jotta tämä olisi formaalia, tulisi $n$ valita väliltä $[1, N]$, missä $N$ on suuri. Yksityiskohtainen tarkastelu sivuutetaan tässä), kuinka suurella todennäköisyydellä $n$ on jaollinen jollain alkuluvun neliöllä? Todennäköisyys on enintään
$\frac{2}{5^2} + \frac{2}{13^2} + \frac{2}{17^2} + \cdots$
missä summa käy läpi kaikki alkuluvut $p \equiv 1 \pmod {4}$. Kuinka suuri tämä summa oikein on? Summaa voi approksimoida käyttäen tunnettua yhtälöä

$$\frac{1}{1^2} + \frac{1}{2^2} + \frac{1}{3^2} + \cdots = \frac{\pi ^2}{6}$$

(Toisaalta, myös lukioanalyysin keinoin saa tehtävään tarpeeksi hyviä rajoja)
Täten, todennäköisyys sille, että satunnaisesti valittu $n$ ei toteuta tehtävänannon ehtoa on $S = \frac{2}{5^2} + \frac{2}{13^2} + \cdots < 2(\frac{\pi ^2}{6} - 1 - \frac{1}{2^2} - \frac{1}{3^2}) < 2(\frac{10}{6} - 1 - \frac{1}{4} - \frac{1}{9}) = 2(\frac{7}{12} - \frac{1}{9}) < 1$

Siis on olemassa äärettömän monta halutunlaista lukua $n$.

**Yleistys**
Tutkitaan nyt, miten seuraavan väite voidaan todistaa:

Olkoon annettu $k \in \mathbb{Z_+}$ ja $t \in \mathbb{Z}$, $t \neq 0$. On olemassa äärettömän monta positiivista kokonaislukua $n$, jolla $n^k + t$ ei ole jaollinen millään alkuluvun neliöllä.

**Ratkaisu**
Yleistys ratkeaa samankaltaisella idealla kuin alkuperäinen tehtävä. Muodostetaan ensin lemmaa 1 vastaava tulos.

**Lemma 2**
Yhtälöllä $x^k \equiv -t \pmod{p^2}$ on enintään $k$ ratkaisua, olettaen että $p \nmid k$ ja $p \nmid t$.

**Todistus**
Kirjoitetaan $x = py + z$. Binomilauseen nojalla pätee

$kpyz^{k-1} + z^k \equiv -t \pmod{p^2}$.

Tästä seuraa, että $z^k \equiv -t \pmod{p}$. Kirjoitetaan $z^k + t = pm$. Nyt,

$kpyz^{k-1} + z^k + t \equiv p(kyz^{k-1} + m) \equiv 0 \pmod{p^2}$, eli $kyz^{k-1} + m \equiv 0 \pmod{p}$. Voimme ratkaista tästä $y$:n, eli $y$:lle on täsmälleen yksi mahdollinen arvo. Tämä onnistuu niin, että vähennetään $m$ toiselle puolelle, ja jaetaan yhtälö puolittain luvulla $p$ jaottomalla luvulla $kz^{k-1}$.

Siis jokainen $z$ antaa yhden ratkaisun. Lagrangen lauseen nojalla yhtälöllä $z^k \equiv -t \pmod{p}$ on vain $k$ erisuurta ratkaisua.


Lemmasta 2 seuraa, että jos $p > k, t$, niin yhtälöllä $x^k \equiv -t \pmod{p^2}$ on enintään $k$ ratkaisua. Muutoin yhtälöllä on enintään $p^2$ ratkaisua.

Valitaan satunnaisesti positiivinen kokonaisluku $n$ (jälleen kerran pitäisi valita joltain mielivaltaisen suurelta väliltä $[1, N]$, mutta ei juututa tähän). Todennäköisyys sille, että $n^k + t$ on jaollinen jonkin alkuluvun neliöllä on enintään

$\sum\limits_{p=1}^{\max(k, t)} \frac{p^2}{p^2} + \sum\limits_{\max(k, t) + 1}^{\infty} \frac{k}{p^2}$

Oleellista tästä on havaita, että summa suppenee: summan ensimmäisessä osassa on vain äärellisen monta termiä, ja jälkimmäinen osa on varmasti alle $\frac{k \pi^2}{6}$. Summa voi kuitenkin olla suurempaa kuin $1$, joten emme ole vielä valmiit.

Voimme pienetää epävalidin $n$:n valitsemisen todennäköisyyttä kiinalaisella jäännöslauseella. Teemme seuraavasti:

Kaikille "pienille" $p$ valitsemme $n \equiv a \pmod{p^2}$, missä $a$ on sellainen, että $a^k + t$ ei ole jaollinen luvulla $p^2$. Tällainen $a$ on olemassa, miksi? Oletetaan, että tällaista $a$:ta ei olisi, tai siis, $n^k + t \equiv 0 \pmod{p^2}$ kaikilla $n$. Täten, valitsemalla $n \equiv 0 \pmod{p^2}$ saamme $t \equiv 0 \pmod{p^2}$. Mutta tällöin $1^k + t \equiv 1 \pmod{p^2}$ ei ole jaollinen luvulla $p^2$.


Olemme nyt valinneet $n \equiv A \pmod{B}$ jollain $A$ ja $B$. Valitaan $n$ satunnaisesti niin, että se toteuttaa tämän ehdon. Millä todennäköisyydellä $n$ ei toteuta tehtävänannon ehtoa? Valitsemalla $n$:n niin, että $p^2$ ei jaa lukua $n^k + t$ millään $p \le max(k, t)$ saamme epäonnistumiselle maksimitodennäköisyyden

$\sum\limits_{p=\max(k, t) + 1}^{\infty} \frac{k}{p^2}$

Voimme edelleen pienentää epäonnistumisen todennäköisyyttä: valitaan $n$ sopivasti modulo $p^2$, missä $p > \max(k, t)$. Näin voimme pienentää epäonnistumisen todennäköisyyden mielivaltaisen pieneksi (tämä on intuitiivista. Jos ei usko, voi integroida funktiota $f(x) = \frac{k}{x^2}$ väliltä $[N, \infty[$ ja huomata, että vastaus on alle $1$ kaikilla tarpeeksi suurilla $N$. Tämä todistaa väitteen).

Voimme siis valita äärettömän monta positiivista kokonaislukua $n$, jolla $n^k + t$ on neliövapaa.
