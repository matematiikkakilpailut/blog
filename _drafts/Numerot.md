---
layout: post
author: "Olli Järviniemi"
title: "Numeroiden summa"
math: true
excerpt_separator: "<!--jatkuu-->"

---

Tässä postauksessa käsitellään numeroiden summan ominaisuuksia.

<!--jatkuu-->

Olkoon koko tämän postauksen ajan $S(n)$ luvun $n \in \mathbb{N}$ numeroiden summa kymmenjärjestelmäesityksessä (huomautettakoon, että muille kannoille löytyy samanlaisia ominaisuuksia kuin 10-kannalle).

Ensiksi esitellään kaksi suhteellisen yleistä tulosta numeroiden summasta.


**Lause 1**
Kaikilla $a, b \in \mathbb{N}$ pätee $$S(a+b) \le S(a) + S(b)$$

**Lause 2**
Kaikilla $a, b \in \mathbb{N}$ pätee $$S(ab) \le S(a)S(b)$$

Tulokset ovat varsin intuitiivisia. Todistetaan ensin lause 1.

**Todistus (lause 1)**

Lauseen todistus ei vaadi kovin ihmeellisiä temppuja, mutta jossain määrin kertoo, miten funktio $S$ käyttäytyy. Todistukseen ei kannata juuttua liian pitkäksi aikaa.

Todistetaan ensin, että väite pätee, kun $0 < a \le 9$, kaikilla $b$. Tutkitaan mitä tapahtuu, kun $a+b$ lasketaan allekkain. Mahdollisesti jossain kohdissa yli menevä numero lisätään seuraavan kymmenen potenssin kohdalle. Näin käy esimerkiksi tapauksessa $a = 9, b = 123$. Tapauksessa $0 < a \le 9$ voidaan todistaa epäyhtälö $S(a+b) \le S(a) + S(b)$ tutkimalla kahta eri tapausta:

Tapaus 1. Yhteenlaskussa numerot eivät mene seuraavan kymmenen potenssin kohdalle. Tämä tapaus on selvä, tällöin luvun $a+b$ viimeinen numero on sama kuin $b$:n viimeinen numero + $a$. Tässä tapauksessa $S(a+b) = S(a) + S(b)$.

Tapaus 2. Yhteenlaskussa numeroita menee vähintään kerran seuraavaan kymmenen potenssiin. Tällöin summan $a+b$ viimeinen numero on aidosti pienempi kuin $a$:n ja $b:$n viimeisten numeroiden summa. Toisaalta, yli menevä numero voi kasvattaa summaa enää vain maksimissaan yhdellä (miksi?), minkä vuoksi epäyhtälö $S(a+b) \le S(a) + S(b)$ pätee myös tässä tapauksessa.

Siis tapaus $0 < a \le 9$ on selvä.

Yleinen tapaus todistetaan induktiolla luvun $a$ numeroiden määrän suhteen. Käytetään seuraavia faktoja:
1. $S(b_010^k + b') = S(b_0) + S(b')$, jos $b' < 10^k$.
2. $S(n) = S(n10^t)$ kaikilla $n, t \in \mathbb{N}$.

Lisäksi käytetään yllä todistettua tiulosta $S(a+b) \le S(a) + S(b)$, kun $a \le 9$.

Oletetaan, että väite pätee kaikilla $b$, kun $a$:n numeroiden määrä on $\le k$. Todistetaan nyt väite kaikille $b$, kun $a$ sisältää $k+1$ numeroa. Kirjoitetaan $a = a_k10^k + a'$, missä $0 \le a' < 10^k$ ja $0 < a_k \le 9$. Nyt,

$$S(a+b) = S(a' + a_k10^k + b) \le S(a') + S(a_k10^k + b)$$

induktio-oletuksen nojalla. Kirjoitetaan $b = b' + 10^kb_k$, missä $b' < 10^k$, tavoitteena jakaa $S(a_k10^k + b)$ pienempiin palasiin. Käyttämällä jälleen induktio-oletusta saamme

$$S(a_k10^k + b) = S(a_k10^k + b_k10^k + b') \le S_(a_k10^k + b_k10^k) + S(b')$$

Voimme arvioida lukua $S(a_k10^k + b_k10^k) = S(a_k + b_k)$ ylöspäin luvuksi $S(a_k) + S(b_k)$, sillä tiedämme lauseen pätevän, kun $a \le 9$.

Yhdistämällä tehdyt havainnot saadaan

$$S(a+b) \le S(a') + S(a_k) + S(b') + S(b_k) = S(a') + S(a_k10^k) + S(b') + S(b_k10^k)$$ $$= S(a' + a_k10^k) + S(b_k10^k) = S(a) + S(b)$$

Väite on näin ollen todistettu, kun $a$ sisältää $k+1$ numeroa. Induktioaskel on otettu, ja väite $S(a+b) \le S(a) + S(b)$ pätee kaikilla $a, b$.

**Korollaari**

$$S(c_1 + c_2 + \ldots + c_k) \le S(c_1) + S(c_2) + \ldots + S(c_k)$$

kaikilla $k, c_i \in \mathbb{N}$


Todistetaan sitten lause 2.

**Todistus (lause 2)**

Todistetaan väite induktiolla $a$:n numeroiden suhteen. Jos $0 < a \le 9$, voimme käyttää yllä esitettyä korollaaria:

$$S(ab) = S(b + b + \ldots + b) \le S(b) + S(b) + \ldots + S(b) = aS(b)$$

missä summattavia on $a$ kappaletta.

Oletetaan, että väite pätee kaikilla $a$, joilla on enintään $k$ numeroa. Osoitetaan väite, kun $a$:lla on $k+1$ numeroa. Olkoon $a = a_k10^k + a'$, missä $0 < a_k \le 9$ ja $0 \le a' < 10^k$. Käyttäen induktio-oletusta ja lausetta 1 saamme

$$S(ab) = S(a_k10^kb + a'b) \le S(a_k10^kb) + S(a'b) \le S(a_kb) + S(a')S(b)
\le $$

$$S(a_k)S(b) + S(a')S(b) = (S(a_k10^k) + S(a'))S(b) = S(a_k10^k + a')S(b) = S(a)S(b) $$

Induktioaskel on otettu ja täten lause 2 pätee.

**Esimerkkitehtävä (Venäjä, 1999)**

$S(n) = 100$ ja $S(44n) = 800$. Määritä $S(3n)$

**Ratkaisu**

Käyttäen lauseita 1 ja 2, sekä faktaa $S(10k) = S(k)$:

$S(44n) \le S(4n) + S(40n) = 2S(4n) \le 2S(3n) + 2S(n) \le 8S(n)$

Kuitenkin $S(44n) = 8S(n)$. Täten jokaisessa epäyhtälössä pätee yhtäsuuruus, joten $2S(3n) + 2S(n) = 8S(n)$, eli $S(3n) = 300$.

Seuraava esimerkkitehtävä on jonkin verran vaikeampi kuin edellinen.

**Esimerkkitehtävä (Baltian tie 2008, T10)**

Määritä lausekkeen

$$\frac{S(n)}{S(16n)}$$

suurin mahdollinen arvo.

**Ratkaisu**

Intuitiivisesti maksimin saavuttamiseksi kannattaisi valita sellainen $n$, jolla $S(16n)$ on mahdollisimman pieni. Tähän sopii hyvin $n = 5^4 = 625$, jolloin $S(16n) = S(10^4) = 1$. Lausekkeen arvo on tällöin $S(n) = 13$. Pyritään sitten osoittamaan, että tämä todella on maksimi.

Näemme heti, että $S(16n) \le S(16)S(n) = 7S(n)$ lauseen 2 nojalla. Tässä arvio menee kuitenkin väärään suuntaan, haluaisimme arvioida lukua $S(16n)$ alhaalta päin. Tämän vuoksi on luonnollista kirjoittaa seuraava epäyhtälö:

$$S(k)S(16n) \ge S(16nk)$$

kaikilla $k \in \mathbb{N}$. Enää tulee valita hyvä $k$:n arvo. Tähän käy $k = 5^4$, jolloin saamme $13S(16n) \ge S(10^4n) = S(n)$. Tämä todistaa, että $13$ todella on maksimi.


Numeroiden summalla on lauseiden 1 ja 2 ohella muitakin tärkeitä ominaisuuksia. $S(n)$ on maksimissaan noin $\log(n)$ (tarkemmin enintään $9* \lfloor \log_{10}(n) \rfloor + 9$, ja tätäkin rajaa lienee mahdollista parantaa). Tätä kautta muodostetut epäyhtälöt voivat olla kriittisiä tehtävän ratkaisemiseksi.

**Esimerkkitehtävä (IMO-lyhytlista 2016, N1)**

Määritä kaikki kokonaislukukertoimiset polynomit $P$, joilla on seuraava ominaisuus: kaikilla $n \ge 2016$ luku $P(n)$ on positiivinen ja

$$S(P(n)) = P(S(n))$$

**Ratkaisuhahmotelma**

Jos $P$ on vakio, tulee olla $P(x) = c$ kaikilla $x$, missä $1 \le c \le 9$ on kokonaisluku. Tämä perustuu melko helposti todistettavaan epäyhtälöön $S(c) < c$ kaikilla $c \ge 10$.

Jos $P$ on lineaarinen, on ainoa ratkaisu $P(n) = n$. Tämän todistaminen jätetään lukijalle.

Oletetaan nyt, että $d = \deg(P) \ge 2$. Valitaan $n = 10^k - 1$. Tällä $n$ pätee

$P(S(n)) = P(9k)$

$P(9k)$ on kokoluokaltaan suunnilleen $(9k)^d$

Tutkitaan sitten lukua $S(P(n))$

$P(n)$ on enintään kokoluokkaa $n^d$, eli noin $10^{kd}$, joten $S(P(n))$ on enintään kokoluokkaa $\log(10^{kd}) = kd \log(10)$.

Sillä $(9k)^d > kd \log(10)$ tarpeeksi suurilla $k$ (ottaen huomioon $d \ge 2$), tehtävällä ei ole ratkaisuja, joissa $\deg(P) \ge 2$.

Täten kaikki ratkaisut ovat aiemmin mainitut vakiofunktiot ja polynomi $P(n) = n$.

Ratkaisuhahmotelman laskut eivät olleet kovin tarkkoja, mutta ideana ratkaisu toimii kuten yllä on esitetty.

Lopuksi mainitaan vielä varsin tunnettu ja helposti todistettava fakta: $n \equiv S(n) \pmod{9}$ kaikilla $n$.

**Harjoitustehtäviä**

Osoita, että kaikilla $c > 9$ pätee $S(c) < c$.

**IMO 1975, T4**

Määritä $S(S(S(4444^{4444})))$

**Baltian Tie, 2005, T1**

Olkoon $a_0$ positiivinen kokonaisluku. Määritellänä jono $\lbrace a_n \rbrace_{n \ge 0}$ seuraavasti: Jos


$$a_n = \sum\limits_{i=0}^j c_i10^i$$

missä $c_i$:t ovat kokonaislukuja ja $0 \le c_i \le 9$, niin

$$a_{n+1} = c_0^{2005} + c_1^{2005} + \ldots + c_j^{2005}$$

Voidaanko $a_0$ valita siten, että kaikki termit jonossa ovat erisuuria?

**Harshad-luvut (?)**

Olkoon $k$ positiivinen kokonaisluku. Osoita, että on olemassa sellainen $n \in \mathbb{N}$, jolla $S(n) = k$, ja $k \mid n$.
