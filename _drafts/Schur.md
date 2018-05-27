---
layout: post
author: "Olli Järviniemi"
title: "Kobayashin lause"
math: true
excerpt_separator: "<!--jatkuu-->"
---

Tässä postauksessa käsitellään Schurin lausetta.

<!--jatkuu-->

Puhuttaessa polynomeista tässä kirjoituksessa viitataan, ellei toisin mainita, kokonaislukukertoimisiin yhden muuttujan polynomeihin.

**Schurin lause**

Olkoon $Q$ polynomi, $Q$ ei vakio. Kongruenssiyhtälöllä

$$Q(x) \equiv 0 \pmod{p}$$

on ratkaisu äärettömän monella alkuluvulla $p$.

Lauseelle on esitetty kaksi eri todistusta postauksen lopussa, ja lisäksi yksi harjoitustehtävistä liittyy kolmanteen todistukseen. Lukijan olisi hyvä miettiä todistusta itse ennen kuin lukee eteenpäin.


**Esimerkkitehtävä (Iran 2011)**

Olkoon $P$ polynomi, joka ei ole nollapolynomi. Osoita, että on olemassa äärettömän monta alkulukua $q$, jolla

$q \mid 2^n + P(n) \ \exists \ n \in \mathbb{N}$

**Ratkaisu**
Muistetaan äärimmäisen tärkeä fakta: jos $a \equiv b \pmod{q}$, niin $P(a) \equiv P(b) \pmod{q}$ (tässä $q$:n ei tarvitsisi edes olla alkuluku).

Jos $P$ on vakio, olemme valmiit [Kobayashin lauseen](https://blog.matematiikkakilpailut.fi/2018/05/02/Kobayashi.html) nojalla. Oletetaan, että $P$ ei ole vakio.

Tehtävässä on hyvä huomata, että eksponenttifunktion $2^n$ jakso on $q-1$ ja polynomin $P$ jakso on $q$. Voimme siis kiinalaisen jäännöslauseen nojalla valita nämä "erikseen". Enää tulee vain varmistaa, että $2^n$ saa saman arvon kuin $-P(n)$ modulo $q$ jollain $n$, äärettömän monella $q$. Tämä onnistuu Schurin lauseen nojalla: on olemassa äärettömän monta $q$, jolla polynomilla $P(n) + 1$ on nollakohta modulo $q$. Olkoon $q$ tällainen, ja olkoon $P(c) \equiv -1 \pmod {q}$. Valitaan nyt $n \equiv 0 \pmod{q-1}$ ja $n \equiv c \pmod{q}$. Valinta onnistuu kiinalaisen jäännöslauseen nojalla, ja Fermat'n pienen lauseen nojalla olemme valmiit.

**Harjoitustehtäviä**

**Baltian tie 2004, T8**

Olkoon $f$ polynomi, $f$ ei vakio. Osoita, että on olemassa sellainen $n$, jolla luvulla $f(n)$ on vähintään $2004$ eri alkutekijää.

**Oma (jatkoa edelliseen)**

Määritä kaikki ne polynomit $P$, joilla pätee seuraava väite: on olemassa äärettömän monta alkulukua $q$, jolla luvulla $P(q)$ on vähintään $2004$ eri alkutekijää.

**Oma**

Olkoon $P$ polynomi, joka ei ole nollapolynomi. Osoita, että on olemassa $k \in \mathbb{N}$ sekä ääretön aidosti kasvava lukujono positiivisia kokonaislukuja $a_1, a_2, \ldots $, joilla pätee

$$syt(P(a_i), P(a_j)) \le k \ \forall i \neq j \in \mathbb{N}$$

Huomaa, että tämä todistaa Schurin lauseen (miksi? Tämä jätetään harjoitustehtäväksi).



**Schurin lauseen todistus**

Schurin lauseen voi todistaa monella tavalla, tässä kaksi niistä.


**Lauseen todistus, ensimmäinen tapa**

Tehdään vastaoletus: $Q$ on jaollinen vain alkuluvuilla $p_1, p_2, \ldots p_k$. Selvästi $Q(0) = c \neq 0$.

Olkoon suurin $p_i$:n potenssi, joka jakaa $c$:n $a_i$.

Valitaan $n = m \cdot p_1^{a_1 + 1}p_2^{a_2 + 1} \ldots p_k^{a_k + 1}$, missä $m \neq 0$ on mielivaltainen kokonaisluku. Nyt $Q(n)$ ei ole jaollinen luvulla $p_i^{a_i + 1}$ millään $i$, sillä kaikki termit paitsi vakiotermi ovat jaollisia tällä luvulla. Tämä rajoittaa luvun $Q(n)$ itseisarvoa: sen tulee olla enintään $p_1^{a_1} \ldots p_k^{a_k}$. Toisaalta, valitsemalla $m$:n ja täten $n$:n tarpeeksi suureksi saamme $Q(n)$:n itseisarvon mielivaltaisen suureksi. Vastaoletus johti ristiriitaan, ja väite on näin ollen tosi.

**Lauseen todistus, toinen tapa**

Olkoon $Q(x) = a_tx^t + a_{t-1}x^{t-1} + \ldots + a_1x + a_0$. Ilman yleisyyden menettämistä oletetaan $a_t > 0$. Tehdään vastaoletus: $Q$ on aina jaollinen vain alkuluvuilla joukosta $P = \lbrace p_1, p_2, \ldots p_k \rbrace$.

Ideana on tutkia niiden lukujen määrää (jollain välillä), jotka ovat muotoa $Q(n)$, ja niiden lukujen määrää, jotka ovat muotoa $p_1^{\alpha_1} \cdot \ldots \cdot p_k^{\alpha_k}$. Jos osoitamme, että jälkimmäisten määrä on pienempi kuin ensin mainittujen, olemme valmiit.

Tutkitaan väliä $[1, N]$, missä $N$ on mielivaltaisen suuri.

**Lemma 1**
Niiden lukujen $n$ määrä, jotka ovat muotoa $p_1^{\alpha_1} \cdot \ldots \cdot p_k^{\alpha_k}$, ja joilla $n \le N$, on enintään

$$C_1 \cdot (\log_2(N))^k$$

jollain (luvusta $k$ riippuvalla, mutta luvusta $N$ riippumattomalla) vakiolla $C_1$.

**Todistus**
Alkuluvun $p_i$ eksponentti $\alpha_i$ on enintään $\log_{p_i}(n) \le \log_{p_i}(N) \le \log_2(N)$. Siispä eksponentille on enintään $\log_2(N) + 1$ vaihtoehtoa, kaikilla $i$. Siis $n$:lle on enintään $(\log_2(N) + 1)^k \le (\log_2(N) + \log_2(N))^k = 2^k \cdot \log_2(N)^k$ vaihtoehtoa. Tämä todistaa lemman väitteen.

**Lemma 2**
Niiden lukujen $n$ määrä, missä $1 \le n \le N$, jotka ovat muotoa $Q(m)$ jollain kokonaisluvulla $m$, on vähintään

$$C_2 \cdot \sqrt[t]{N}$$

missä $t = \deg(Q)$, ja $C_2$ on jokin $Q$:sta muttei $N$:stä riippuva vakio.

**Todistus**
Kun $n$ on tarpeeksi suuri, $Q(n)$ on aidosti kasvava. Lisäksi, kun $n$ on tarpeeksi suuri, $Q(n) \le (a_t + 1)n^t$. Olkoon $n_0$ sellainen, että $Q(n+1) > Q(n)$ kaikilla $n \ge n_0$, ja aiemmin mainittu arvio $Q(n)$:lle pätee. $n_0$ ei riipu $N$:stä.

Osoitetaan, että epäyhtälö $Q(n_0 + C_2 \sqrt[t]{N}) \le N$ pätee kaikilla $N$, jollain vakiolla $C_2 > 0$. Tämä todistaa väitteen.


Merkitään $c = C_2 \sqrt[t]{N}$. Riittää osoittaa, että $(a_t + 1)(n_0 + c)^t \le N$ sopivalla $c$:n (eli $C_2$:n) valinnalla. Tähän puolestaan riittää $(a_t + 1)(2c)^t \le N$, sillä $n_0 < c$ kun $c$ on tarpeeksi suuri (eli $N$ on tarpeeksi suuri). Nyt on selvää, että voimme valita $c = C_3 \sqrt[t]{N}$ jolain vakiolla $C_3$. Luvun $C_3$ tulee vain toteuttaa ehto

$(a_t + 1)(2C_3)^t \le 1$,

ja tämä onnistuu, sillä $t$ ja $a_t$ ovat vakioita. Siispä lemma 2 pätee.

**Viimeistely**

Jotta lauseen todistus saadaan viimeisteltyä, tulee enää osoittaa, että

$C_2 \sqrt[t]{N} \ge C_1 \log_2(N)^k$

kaikilla tarpeeksi suurilla $N$, kun $C_1, C_2, k, t > 0$ ovat vakioita. Tämä on ilmiselvää (sillä juurifunktio kasvaa nopeammin kuin logaritmi), mutta sen todistus esitetään siitä huolimatta tässä.

Korotetaan yhtälö potenssiin $t$, ja jaetaan puolittain termillä $C_2^t$. Riittää todistaa

$N \ge C_3 \log_2(N)^m$

vakioilla $C_3$ ja $m$.

Tehdään sijoitus $N = M^m$. Epäyhtälö muuttuu muotoon $M \ge C_4 \log_2(M)$ Vasemman puolen derivaatta $M$:n suhteen on $1$, ja oikean puolen derivaatta on $\frac{C}{M}$ jollain vakiolla $C$. $\frac{C}{M} < \frac{1}{2}$ kaikilla tarpeeksi suurilla $M$. Täten vasen puoli kasvaa nopeammin kuin oikea puoli tarpeeksi suurilla $M$, eli se on myös suurempi kuin oikea puoli tarpeeksi suurilla $M$. Tämä todistaa tarvittavan epäyhtälön.
