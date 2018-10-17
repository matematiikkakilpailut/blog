---
layout: post
author: "Olli Järviniemi"
title: "Moniulotteisia ongelmia"
math: true
excerpt_separator: "<!--jatkuu-->"

---

Tässä postauksessa käydään läpi kaksi kisatehtävää, joita voi tulkita moniulotteisesti.

<!--jatkuu-->

Ensimmäinen esimerkkitehtävä on MAOLin lukion loppukilpailusta.

**Esimerkki 1 (MAOLin loppukilpailu, 2017, T4)**

Olkoon $m$ positiivinen kokonaisluku. Kahden pelaajan, Akselin ja Elinan, välinen peli HAUKKU$(m)$ etenee seuraavasti: Akseli aloittaa, ja pelaajat valitsevat kokonaislukuja vuorotellen. Aluksi valittavien kokonaislukujen joukko on luvun $m$ positiivisten tekijöiden joukko. Vuorossa oleva pelaaja valitsee yhden jäljellä olevista luvuista, ja valittavien lukujen listasta poistetaan tämä luku ja sen kaikki monikerrat. Pelaaja, joka joutuu valitsemaan luvun $1$, häviää.Osoita, että aloittajalla eli Akselilla on voittostrategia pelissä HAUKKU$(m)$ kaikilla $m \in \mathbb{Z_+}$.

**Huomautus** Alkuperäisessä tehtäväpaperissa oli pieni virhe: Akseli häviää, jos $m = 1$, mutta muissa tapauksissa hänellä on voittostrategia.

Esitetään ensimmäisenä ehkäpä yksinkertaisin ratkaisu tehtävään.

**Ratkaisu**

Tutkitaan kahta tapausta:

1. Akseli voittaa, jos valitsee luvun $m$ ensimmäisellä vuorollaan. Tässä tapauksessa Akselilla on voittostrategia.

2. Akseli ei voita, jos valitsee luvun $m$ ensimmäisellä vuorollaan. Tämä tarkoittaa, että Elina voittaa valitessaan Akselin ensimmäisen siirron jälkeen luvun $d$. Mutta tällöin Akseli voittaisi valitsemalla luvun $d$ ensimmäisellä vuorollaan.

Molemmissa tapauksissa Akselilla on voittostrategia, joten Akselilla on voittostrategia kaikilla $m > 1$. (Missä kohtaa ratkaisua käytettiin tietoa $m > 1$?)

Esitetään sitten, miten tehtävää voi havainnollistaa geometrisesti.

**Havainnollistus**

On luonnollista tutkia luvun $m$ alkutekijähajotelmaa. Kirjoitetaan $m = p_1^{\alpha_1}p_2^{\alpha_2} \ldots p_k^{\alpha_k}$. Tutkitaan, mitkä listan luvut poistuvat, kun jompikumpi pelaajista valitsee luvun $d = p_1^{\beta_1}p_2^{\beta_2} \ldots p_k^{\beta_k}$. Nämä ovat täsmälleen ne listan luvut, joiden alkutekijähajotelmassa luvun $p_i$ eksponentti on vähintään $\beta_i$ kaikilla $i$.

Tutkitaan sitten, mitä tämä tarkoittaa geometrisesti, kun $k = 2$. Luvun $m$ tekijät voidaan kirjoittaa ruudukkoon, jonka sivut ovat $\alpha_1 + 1$ ja $\alpha_2 + 1$. Alla esimerkki, kun $\alpha_1 = 3$ ja $\alpha_2 = 2$.


| $1$ | $p_1$  | $p_1^2$  | $p_1^3$  |
|---|---|---|---|
| $p_2$  | $p_1p_2$  | $p_1^2p_2$  | $p_1^3p_2$  |
| $p_2^2$  | $p_1p_2^2$  | $p_1^2p_2^2$  | $p_1^3p_2^2$  |

Jos jompikumpi pelaajista valitsee esimerkiksi tekijän $p_1p_2$, poistuu ruudukosta $2 \times 3$-pikkuruudukko oikeasta alakulmasta.

Yleisessä tilanteessa pelin alkutilaa voidaan mallintaa $k$-ulotteisena suorakulmaisena särmiönä, jonka sivjen pituudet ovat $\alpha_i + 1$.



Edellisessä esimerkkitehtävässä moniulotteinen mallinnus ei tuo uudenlaista ratkaisua tehtävään (vaikkakin se voi auttaa ratkaisun keksimistä). Seuraavassa esimerkissä samanlainen havainnollistus auttaa merkittävästi tehtävän ratkaisemista.

**Esimerkki 2 (Baltian Tie -valintakoe 2018, T5). Tehtävän muotoilu kirjoittajan ulkomuistista**

Sanotaan, että positiiviset kokonaisluvut $a$ ja $b$ ovat alkulukusuhteutettavissa, jos on olemassa alkuluku $p$, jolla $a = bp$ tai $b = ap$. Määritä kaikki positiiviset kokonaisluvut $n$, joilla on vähintään kolme tekijää, ja joilla luvun $n$ tekijät voidaan asettaa ympyrän kehälle niin, että kaikki tekijät esiintyvät täsmälleen kerran, ja mitkä tahansa kaksi vierekkäistä lukua ovat alkulukusuhteutettavissa.


**Ratkaisuhahmotelma**

Olkoon luvun $n$ alkutekijähajotelma $p_1^{\alpha_1} \ldots p_k^{\alpha_k}$. Luvun $n$ tekijät voidaan asettaa $k$-ulotteiseen suorakulmaiseen särmiöön kuten edellisessä tehtävässä. Tästä saadaan ensimmäinen tärkeä huomio: haluttu tekijöiden asettaminen ympyrän kehälle vastaa polkua suorakulmaisen särmiön pikkukuutioissa, missä polun tulee aina kulkea "vierekkäiseen" kuutioon käyden jokaisessa kuutiossa täsmälleen kerran ja lopulta palata takaisin alkuperäiseen kuutioon.

Tapauksessa $k = 1$ polku on selvästi mahdoton. Tapauksessa $k = 2$ polku vastaa kaksiulotteisen ruudukon läpikäyntiä. Polku on olemassa, jos vähinrään yksi ruudukon sivuista on parillisen pituinen, mikä voidaan todistaa konstruktiolla ja shakkilautavärityksellä. Yksityiskohdat jätetään lukijalle. Tapaus $k = 3$ on myös hahmotettavissa, jolloin päädytään samaan tulokseen: polku on olemassa jos ja vain jos vähintään yksi särmiön sivuista on parillisen pituinen.

Näiden huomioiden perusteella vaikuttaisi siltä, että tehtävänannon luvuiksi $n$ kelpaa kaikki ne luvut, jotka eivät ole alkuluvun potensseja tai neliölukuja. Tämä ei ole kovin vaikeaa todistaa induktiolla luvun $k$ suhteen. Induktioaskeleen voi esimerkiksi suorittaa tutkimalla $k+1$-ulotteista särmiöta ja paloittelemala sen $k$-uloitteisiin särmiöihin. Yksityiskohdat jätetään lukijalle.


**Harjoitustehtävä**

Olkoon $n > 1$ kokonaisluku, jonka alkutekijät ovat $p_1, p_2, \ldots , p_k$. Aluksi luvun $n$ tekijät on kirjoitettu liitutaululle. Jokainen operaatio koostuu seuraavista askelista:

1. Valitaan jotkin $k$ kokonaislukua $a_1, a_2, \ldots , a_k$.
2. Poistetaan liitutaululta ne luvun $n$ tekijät $d$, joilla $v_{p_i}(d) = a_i$ vähintään yhdellä $i$. Tässä $v_p$ on ns. [p-adic valuation](https://blog.matematiikkakilpailut.fi/2018/07/19/Vp.html).

Mikä on pienin määrä operaatioita, jonka jälkeen taululla ei ole enää yhtäkään lukua jäljellä?
