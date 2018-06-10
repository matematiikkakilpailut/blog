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

Tutkitaan niitä muotoa $pm$ olevia lukuja, jossa $pm \le n$. Luku $m$ käy läpi eri arvoja, jotka ovat jaollisia jollakin joukon $P \setminus K$ luvuilla, kun $n$ on tarpeeksi suuri. Itse asiassa $m$:n käydessä läpi eri arvoja se on jaollinen täsmälleen niillä joukon $P \setminus K$ luvuilla, jotka ovat enintään $\frac{n}{p}$. Siispä joukossa $A$ tulee olla kaikki ne luvut, joilla on tällaisia "pieniä" alkutekijöitä joukosta $P \setminus K$.

Osoitetaan nyt, että tarpeeksi suurilla $n$ joukon $A$ alkioiden tulo on paljon suurempi kuin joukon $B$ alkioiden tulo. Intuitiivisesti tämä pätee, sillä $B$:n alkioiden alkutekijät on rajoitettu joukkoon $K$ tai suuriin lukua $\frac{n}{p}$ isompiin alkulukuihin. Formaali todistus vaatii hieman laskemista, muttei ole sinänsä vaikea.

**Lemma 1**

Epäyhtälö

$$\mid B \mid \le C \frac{n}{\log_2(n)}$$

pätee kaikilla $n > 1$, jostain $n$:stä riippumattomalla vakiolla $C$. $C$ voi riippua $k$:sta.

**Todistus**

Todistus on analoginen Schurin lauseen todistuksessa käytetyn lemman todistuksen kanssa. Lemma sanoo, että niitä lukuja, jotka ovat jaollisia vain joukon $S$ alkuluvuilla ja ovat enintään $N$, on enintään

$C_1 \log_2(N)^{\mid S \mid}$

Tämän nojalla niitä $B$:n alkioita, jotka ovat jaollisia vain lukua $\frac{n}{p}$ pienemmillä alkuluvuilla on enintään $C_2 \log_2(N)^{| K |}$. Tämä kasvaa hitaammin kuin $\frac{n}{\log_2(n)}$, joten arvio on tältä osin kunnossa. Enää tulee huolehtia siitä, ettei $B$:ssä voi olla liian montaa lukua, jotka ovat jaollisia lukua $\frac{n}{p}$ suuremmalla alkuluvulla.

Valitaan jokin lukua $\frac{n}{p}$ suurempi alkuluku $q$. Luvun $q$ monikertoja on $B$:ssä enintään $pq$. $p$ on vakio, joka riippuu vain $k$:sta. Nyt otetaan avuksi järeämpää kalustoa, jolla saamme tarpeeksi hyvän rajan lukujen $q$ määrälle:

**Alkulukulause (Prime number theorem, PNT)**

Olkoon $\pi(x)$ lukua $x$ pienempien alkulukujen määrä. Suhde

$$\frac{\pi(x)\ln(x)}{x}$$

lähestyy ykköstä luvun $x$ lähestyessä ääretöntä. Tämä siis tarkoittaa sitä, että esimerkiksi kaikilla tarpeeksi suurilla $x$ arviot

$$\frac{1}{2} \le \frac{\pi(x)\ln(x)}{x} \le 2$$

pätevät.

Lauseen todistus vaatii analyyttistä lukuteoriaa ja jonkin verran esitietoja, minkä vuoksi sitä ei esitetä tässä. Lause on kuitenkin (hyvin) tunnettu, eli sitä lienee sallittua käyttää esimerkiksi IMOssa, mutta varmahan asiasta ei voi olla.

Tämän nojalla niitä $B$:n alkioita, jotka ovat jaollisia jollain suurella alkuluvulla, on enintään $C_3 \frac{n}{\log_2(n)}$ kaikilla tarpeeksi suurilla $n$, missä $C_3$ on jokin vakio. $C_3$ riippuu $k$:sta, ja lisäksi sen kokoluokka vaikuttaa siihen, kuinka suurilla $n$ väite pätee. Tärkeintä on kuitenkin jonkin tällaisen vakion $C$ olemassaolo, eikä niinkän sen suuruus.

Tämän nojalla

$$ \mid B \mid  \le C_2 \log_2(N)^{ \mid K \mid } + C_3 \frac{n}{\log_2(n)} \le C \frac{n}{\log_2(n)}$$

jollain $k$:sta, $C_2$:sta ja $C_3$:sta riippuvalla vakiolla $C$, kaikilla tarpeeksi suurilla $n$. Lisäksi kasvattamalla $C$:tä arvion saa pätemään myös pienillä $n$:n arvioilla. Lemman väite siis pätee.

Pidetään loppuratkaisun ajan lemman 1 muuttuja $C$ vakiona.

Lemmasta 1 seuraa, että joukon $B$ alkioiden tulo on enintään

$$n^{ \mid B \mid } \le n^{ C \frac{n}{\log_2(n)} }$$

Koska $$ \mid A \mid  = n -  \mid B \mid  \ge n - C \frac{n}{\log_2(n)}$$

