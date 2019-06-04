---
layout: post
author: "Olli Järviniemi"
title: "Polynomien yhteiset alkutekijät, osa 7: lause 2"
math: true
excerpt_separator: "<!--jatkuu-->"

---

Tässä postauksessa todistetaan tutkielma lause 2, eli Schurin lauseelle yleistys. Todistus perustuu Frobeniuksen lauseeseen.


<!--jatkuu-->

**Sisällysluettelo**

1. [Osa 1 - johdanto](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAjohdanto.html)
2. [Osa 2 - esitiedot](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAesitiedot.html)
3. [Osa 3 - tulokset](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAtulokset.html)
4. [Osa 4 - motivaatio](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAmotivaatio.html)
5. [Osa 5 - heikko versio](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAheikko.html)
6. [Osa 6 - yleinen tapaus](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAyleinen.html)
7. Osa 7 - lause 2
8. [Osa 8 - lause 3](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAlause3.html)
9. [Osa 9 - lause 4](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAlause4.html)
10. [Osa 10 - sovelluksia](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAsovelluksia.html)
11. [Osa 11 - lisäaiheita](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAlisaaiheita.html)


Tavoitteena on siis osoittaa seuraava lause:

Olkoot $P_1, P_2, \ldots , P_n \in \mathbb{Z_*}[x]$. Pätee

$$\delta(S_v(P_1) \cap \ldots \cap S_v(P_n)) \ge \frac{1}{\deg(P_1) \ldots \deg(P_n)}$$


Lauseen 1 ja lemman 2 nojalla riittää osoittaa, että $\delta(S(D)) \ge \frac{1}{\deg(D)}$ kaikilla $D \in \mathbb{Z_*}[x]$.

Väite on osoitettu artikkelissa [Prime factors of $a^{f(n)} - 1$ with an irreducible polynomial $f(x)$](https://www.researchgate.net/publication/268860079_Prime_factors_of_a_fn_-1_with_an_irreducible_polynomial_fx) (Christian Ballot, Florian Luca). Mutta miten?

Todistus perustuu Frobeniuksen lauseeseen sekä pienen määrään ryhmänteoriaan. Ensimmäisen ymmärrän ja pystyn selittämään, mutta toisesta minulle ei ole tietoa (mutta ilmeisesti käytetty ryhmäteoria on hyvin standardia).

Väite on oikeastaan osoitettu viitteessä vain jaottomille pääpolynomeille, mutta lemman 8 nojalla väite pätee kaikilla jaottomilla polynomeilla. Väite pätee täten tietysti myös jakautuvilla polynomeilla.

### Galois'n ryhmä

Frobeniuksen lausetta varten määritellään Galois'n ryhmä.

**Määritelmä - Galois'n ryhmä**

Olkoon $P \in \mathbb{Z_*}[x]$, ja olkoon $F$ sen juurikunta. Olkoon $G$ isomorfismien $\sigma : F \to F$ joukko. $G$:tä kutsutaan kunnan $F$ tai polynomin $P$ Galois'n ryhmäksi.

**Rakenne**

Millaisia ovat isomorfismit $\sigma : F \to F$? Olkoon $P(x) = a_dx^d + a_{d-1}x^{d-1} + \ldots + a_0$, missä $a_i \in \mathbb{Z}$ (tai $a_i \in \mathbb{Q}$, ei väliä). Olkoon $\alpha$ jokin $P$:n juuri. Käytetään isomorfismien seuraavia ominaisuuksia:

1. $\sigma(xy) = \sigma(x)\sigma(y)$
2. $\sigma(x + y) = \sigma(x) + \sigma(y)$
3. $\sigma(1) = 1$.
4. $\sigma(q) = q$ kaikilla $q \in \mathbb{Q}$ (seuraa ehdoista 1-3).

Saamme

$$0 = \sigma(0) = \sigma(P(\alpha)) = \sigma(a_d\alpha^d + \ldots + a_0) $$

$$= \sigma(a_d\alpha^d) + \sigma(a_{d-1}\alpha^{d-1}) + \ldots + \sigma(a_0)$$

$$= a_d\sigma(\alpha)^d + a_{d-1}\sigma(\alpha)^{d-1} + \ldots + a_0$$

$$= P(\sigma(\alpha))$$



Huomaamme siis, että $\sigma(\alpha)$ on jokin $P$:n juuri. $\sigma$ siis vain kuvaa $P$:n juuria toisikseen. Huomaa, että $\sigma$ on permutaatio, koska isomorfismin tulee olla bijektiivinen. $\sigma$ siis **permutoi** $P$:n juuria. Tämän vuoksi Galois'n ryhmästä puhuttaessa puhutaan usein permutaatioista: Galois'n ryhmän voidaan ajatella olevan joukko permutaatioita.

Tämä osoittaa, että $G$ on äärellinen, ja sen koko on enintään $\deg(P)!$.

Huomataan vielä, että arvot $\sigma(\alpha_1), \sigma(\alpha_2), \ldots , \sigma(\alpha_d)$ määrittävät Galois'n ryhmän alkion $\sigma$ yksikäsitteisesti. Tämä johtuu siitä, että jokainen juurikunnan $F$ alkio voidaan kirjoittaa polynomina muuttujista $\alpha_i$.

**Huomautus**

Galois'n ryhmä toteuttaa [ryhmän](https://en.wikipedia.org/wiki/Group_(mathematics)) vaatimukset.

**Esimerkki**

Tutkitaan polynomin $P(x) = x^2 - 2$ Galois'n ryhmää. Galois'n ryhmän kuvaukset permutoivat juuria $\lbrace \sqrt{2}, -\sqrt{2} \rbrace$. On siis kaksi eri vaihtoehtoa:

1. $\sigma_1(\sqrt{2}) = \sqrt{2}$. Tällöin $\sigma_1(-\sqrt{2}) = -\sigma_1(\sqrt{2}) =  -\sqrt{2}$.

2. $\sigma_2(\sqrt{2}) = -\sqrt{2}$. Tällöin $\sigma_2(-\sqrt{2}) = -\sigma_2(\sqrt{2}) = \sqrt{2}$.

Ensimmäisen kuvauksen tapauksessa $\sigma(a + b\sqrt{2}) = a + b\sigma(\sqrt{2}) = a + b\sqrt{2}$ kaikilla $a, b \in \mathbb{Q}$. Siis kyseessä on identiteettikuvaus.

Toisen kuvauksen tapauksessa $\sigma(a + b\sqrt{2}) = a + b\sigma(\sqrt{2}) = a - b\sqrt{2}$ kaikilla $a, b \in \mathbb{Q}$. Kyseessä on konjugaatio.


### Frobeniuksen lause

**Permutaation komponenttijako**

Olkoon $\sigma$ jokin $P$:n Galois'n ryhmän alkio. $\sigma$ voidaan ajatella permutaationa, joka permutoi joukkoa $\lbrace 1, 2, \ldots , n \rbrace$, missä $n = \deg(P)$. Nämä permutaatiot voivat sisältää pienempiä syklejä. Yllä olevassa esimerkissä $\sigma_1$ muodostaa kaksi yhden pituista sykliä, kun taas $\sigma_2$ muodostaa yhden ison syklin.

Yleisesti permutaatio voidaan jakaa komponentteihin $H_1, H_2, \ldots , H_k$ niin, että $\sigma(h_i) \in H_i$ kaikilla $h_i \in H_i$. Määritelmä on vielä puutteellinen: voisimme aina valita $H_1 = \lbrace 1, 2, \ldots , n \rbrace$. Valitaan siis se jako, joka maksimoi komponenttien määrän $k$. Olkoon komponentin $H_i$ koko $s_i$.

Käytän pian komponenttijakoa Frobeniuksen lauseen yhteydessä, joten merkitään kuvauksen $\sigma$ komponenttien kokoa joukolla $S(\sigma) = \lbrace s_1, s_2, \ldots , s_k \rbrace$. Muodostetaan tämä joukko niin, että poikkeuksellisesti siellä saa olla sama alkio useampaan kertaan.

Esimerkiksi polynomin $x^2 - 2$ juurikunnan tapauksessa $S(\sigma_1) = \lbrace 1, 1 \rbrace$ ja $S(\sigma_2) = \lbrace 2 \rbrace$.

**Frobeniuksen lause**

Olkoon $P \in \mathbb{Z_*}[x]$, ja olkoon $G$ sen Galois'n ryhmä, ja $g$ Galois'n ryhmän koko. Olkoot $s_1, s_2, \ldots , s_k$ positiivisia kokonaislukuja, joiden summa on $\deg(P)$. Olkoon $N(s_1, s_2, \ldots , s_k)$ niiden $\sigma \in G$ määrä, joilla $S(\sigma) = \lbrace s_1, s_2, \ldots , s_k \rbrace$.

Olkoon $S$ niiden $p$ joukko, joilla $P$ jakautuu täsmälleen $k$ polynomiksi modulo $p$, joiden asteet ovat $s_1, s_2, \ldots , s_k$. Tällöin $\delta(S)$ on olemassa, ja

$$\delta(S) = \frac{N(s_1, s_2, \ldots , s_k)}{g}$$

**Esimerkki**

Määritetään polynomin $P(x) = x^2 - 2$ alkutekijöiden tiheys. Galois'n ryhmän koko tässä tapauksessa on $2$, ja komponenttijaot Galois'n ryhmän alkioille ovat $\lbrace 1, 1 \rbrace$ ja $\lbrace 2 \rbrace$. Niiden $p$ tiheys, joilla $P$ ei jakaudu modulo $p$ on Frobeniuksen lauseen nojalla

$$\frac{N(2)}{g} = \frac{1}{2}$$

Ja niiden $p$ tiheys, joilla $P$ jakautuu on vastaavasti $\frac{1}{2}$.


**Esimerkki**

Olkoon $P \in \mathbb{Z}[x]$ mielivaltainen toisen asteen polynomi. Sen juuret ovat muotoa $a \pm \sqrt{b}$, missä $a, b \in \mathbb{Q}$. Jos $b$ on rationaaliluvun neliö, ovat $P$:n juuret rationaalisia, ja $\delta(S(P)) = 1$. Jos taas $b$ ei ole rationaaliluvun neliö, $P$:n juuret eivät ole rationaalisia. Tällöin $P$:n Galois'n ryhmän koko on $2$: yksi kuvaus on $\sigma_1(a + \sqrt{b}) = a + \sqrt{b}$ (identiteettikuvaus), ja toinen kuvaus on $\sigma_2(a + \sqrt{b}) = a - \sqrt{b}$ (konjugaatio).

Frobeniuksen lauseen nojalla $P$:n alkutekijöiden tiheys on puolet, ja puolet alkuluvuista ovat sellaisia, joilla $P$ ei jakaudu.


**Esimerkki**

Olkoon $P \in \mathbb{Z_*}[x]$ mielivaltainen. $P$:n Galois'n ryhmän koko on enintään $\deg(P)!$. $P$:n Galois'n ryhmään kuuluu varmasti identiteettikuvaus. Siispä

$$\delta(S(P)) \ge \frac{1}{n!}$$

Raja ei tietenkään ole paras mahdollinen, koska myös raja $\delta(S(P)) \ge \frac{1}{n}$ pätee.

**Huomautus**

Aina ei päde, että $P$:n Galois'n ryhmä on $\deg(P)!$. Esimerkki: olkoon $P(x) = x^4 + 1$. Tällöin $P$:n juuret ovat $\zeta_8, \zeta_8^3, \zeta_8^5$ ja $\zeta_8^7$, missä $\zeta_8$ on jokin 8. primitiivinen ykkösjuuri. Siispä $P$:n juurikunta on $\mathbb{Q}(\zeta_8)$, ja mikä tahansa isomorfismi $\sigma : \mathbb{Q}(\zeta_8) \to \mathbb{Q}(\zeta_8)$ määräytyy sen mukaan, mihin se kuvaa luvun $\zeta_8$. Täten $P$:n Galois'n ryhmä on maksimissaan $4$ (ja voidaan osoittaa, että tasan $4$).

### Frobeniuksen lauseen todistus

Rehellisesti sanottuna minulla ei ole harmainta aavistustakaan siitä, miten lause osoitetaan. Tässä on muodon vuoksi viite todistukselle:

[Franz Lemmermeyer, Class Field Theory, 2007](http://www.fen.bilkent.edu.tr/~franz/cft/cfb.pdf) (sivut 165-166).

Väite on osoitettu Dirichlet'n tiheydelle eikä luonnolliselle tiheydelle. Frobeniuksen lause on heikompi versio vaikeammasta (ja paljon tunnetummasta) lauseesta nimeltä Chebotarev Density Theorem, jonka todistus luonnolliselle tiheydelle löytyy nopealla etsimisellä netistä. Olen pitkään koittanut ymmärtää, mikä Chebotarevin lauseen sisältö on, miksi se on parempi kuin Frobeniuksen lause ja miten se liittyy polynomien alkutekijöihin (lause esitetään usein tavalla, joka on näennäisesti hyvin kaukana polynomien alkutekijöistä. Tästä lisää viimeisessä postauksessa). Kovan työn jälkeen pääsin jonkinlaiseen käsitykseen, mutten ole sisäistänyt konseptia niin hyvin, että voisin kirjoittaa siitä.

### Lauseiden rajojen tiukkuus

Olkoon $\phi_k$ $k$:nnes syklotominen polynomi. On tunnettua, että $p \in S(\phi_k) \implies p \mid k$ tai $p \equiv 1 \pmod{k}$. Tämän väitteen todistuksesta voi lukea Evan Chenin monisteesta [Orders Modulo A Prime](http://web.evanchen.cc/handouts/ORPR/ORPR.pdf).

Niiden alkulukujen tiheys, joilla $p \equiv 1 \pmod{k}$, on tunnetusti $\frac{1}{\phi(k)}$ (kiinnostunut lukija löytää tästä lisää tietoa netistä - hakusanat "Dirichlet's theorem" ja "prime number theorem for arithmetic progressions" riittävät pitkälle). Koska syklotomisten polynomien aste on $\phi(k)$, osoittaa tämä, että raja on saavutettavissa äärettömän monella polynomilla: valitaan $n = 1$, $P_1(x) = \phi_k(x)$.

Esimerkkinä monelle polynomille rajan tiukkuudesta toimii $P_i(x) = \phi_{p_i}(x)$, missä $p_i$ ovat erisuuria alkulukuja. Tämän toimivuus voidaan osoittaa kiinalaisella jäännöslauseella.

Samalla tämä osoittaa lauseen 1 ylärajan: olkoot $P_i$ sellaisia, että $\delta(S(P_1) \cap \ldots \cap S(P_n)) = \frac{1}{\deg(P_1) \cdots}$. Tällöin lauseen 1 mukaisen $D$:n asteen tulee ehdon $\delta(S(D)) \ge \frac{1}{\deg(D)}$ nojalla toteuttaa $\deg(D) \ge \deg(P_1) \ldots \deg(P_n)$.

### Yläraja

Pätee siis $\delta(S(D)) \ge \frac{1}{\deg(D)}$. Onko mahdollista saada ylärajaa? Suoraan tämä ei ole mahdollista: polynomin $P(x) = (x - 1)(x - 2) \ldots (x - n)$ alkutekijliden tiheys on $1$ kaikilla $n \in \mathbb{Z}_+$.

Parempi kysymys olisi: onko mahdollista antaa epätriviaalia ylärajaa polynomin $P$ alkutekijöiden tiheydelle, kun $P$:llä ei ole rationaalisia juuria?

Tämäkään ei aivan onnistu: polynomin $(x^2 - 2)(x^2 - 3)(x^2 - 6)$ alkutekijöiden tiheys on $1$ neliönjäännösten multiplikatiivisuuden vuoksi.

Jaottomilla polynomeilla yläraja kuitenkin löytyy. Yläraja on $1 - \frac{1}{\deg(P)}$ kaikilla jaottomilla $P$, ja ylärajan saavuttaminen vaatii, että $\deg(P)$ on alkuluvun potenssi. Tämä on osoitettu artikkelissa [On a theorem of Jordan](http://www.ams.org/journals/bull/2003-40-04/S0273-0979-03-00992-3/S0273-0979-03-00992-3.pdf) (Jean-Pierre Serre).
