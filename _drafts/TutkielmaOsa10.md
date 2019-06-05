---
layout: post
author: "Olli Järviniemi"
title: "Polynomien yhteiset alkutekijät, osa 10: sovelluksia"
math: true
excerpt_separator: "<!--jatkuu-->"

---
Tässä postauksessa esitetään työn sovelluksia neliönjäännöksiä ja korkeampien potenssien jäännöksiä käsitteleviin kysymyksiin.


<!--jatkuu-->

**Sisällysluettelo**

1. [Osa 1 - johdanto](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAjohdanto.html)
2. [Osa 2 - esitiedot](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAesitiedot.html)
3. [Osa 3 - tulokset](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAtulokset.html)
4. [Osa 4 - motivaatio](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAmotivaatio.html)
5. [Osa 5 - heikko versio](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAheikko.html)
6. [Osa 6 - yleinen tapaus](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAyleinen.html)
7. [Osa 7 - lause 2](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAlause2.html)
8. [Osa 8 - lause 3](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAlause3.html)
9. [Osa 9 - lause 4](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAlause4.html)
10. Osa 10 - sovelluksia
11. [Osa 11 - lisäaiheita](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAlisaaiheita.html)


Tämän postauksen sisältöä ei tilanpuutteen vuoksi kirjoitettu lopulliseen tutkielmaan. Pidän tämän postauksen tuloksia hyvin mielenkiintoisina (vaikkakin todistuksia aavistuksen puuduttavina), joten esitän ne tässä.

Ensimmäisenä neliönjäännöksistä tulos, jota olen sivunnut [aiemminkin](https://blog.matematiikkakilpailut.fi/2018/12/09/Nelionjaannos.html).

# Lause

Olkoot $a_1, a_2, \ldots , a_n \in \mathbb{Z}$ sellaisia, ettei minkään joukon $\lbrace a_1, a_2, \ldots , a_n \rbrace$ epätyhjän osajoukon alkioiden tulo ole neliöluku. Olkoon $S \subset \lbrace 1, 2, \ldots , n \rbrace$. Olkoon $T_S$ niiden $p$ joukko, joilla on seuraava ominaisuus:

$a_i$ on neliönjäännös modulo $p$ jos ja vain jos $i \in S$.

Tällöin

$$\delta(T_S) = \frac{1}{2^n}.$$


## Todistus

Tutkimme siis polynomien $P_i(x) = x^2 - a_i$ alkutekijöitä.

Osoitetaan ensiksi, että voimme soveltaa lauseen 3 tulosta.

**Lemma**

Olkoon $F$ polynomin $P_1P_2 \ldots P_n$ juurikunta. $[F : \mathbb{Q}] = 2^n$.

**Todistus**

Olkoon $B$ joukko, joka sisältää kaikki joukon $\lbrace a_1, a_2, \ldots , a_n \rbrace$ osajoukkojen alkioiden tulot, eli $B$ sisältää $2^n$ alkiota.

Olkoon $C$ joukko, joka sisältää luvut muotoa $\sqrt{b}, b \in B$.

Riittää osoittaa, että $C$:n alkiot ovat lineaarisesti riippumattomia rationaalilukujen yli. Toisin sanoen, **ei** ole olemassa nollasta eroavia rationaalilukua $q_1, q_2, \ldots , q_k$ ja pareittain erisuuria $C$:n alkioita $c_1, c_2, \ldots , c_k$, joilla

$$q_1c_1 + q_2c_2 + \ldots + q_kc_k = 0$$

Miksi tämä on riittävä ehto? Oletetaan, että $[F : \mathbb{Q}] < 2^n$, tavoitteena vastaoletus yllä esitetyn ehdon kanssa. Käyttäen vastaavanlaista ideaa kuin lauseen 3 todistuksessa, saadaan

$$[F : \mathbb{Q}] = [\mathbb{Q}(\sqrt{a_1}, \ldots , \sqrt{a_n}) : \mathbb{Q}(\sqrt{a_1}, \ldots , \sqrt{a_{n-1}})] \cdots [\mathbb{Q}(\sqrt{a_1}, \sqrt{a_2}) : \mathbb{Q}(\sqrt{a_1})][\mathbb{Q}(\sqrt{a_1}) : \mathbb{Q}].$$

Oikean puolen tulon jokainen termi on selvästi enintään $2$. Jos kaikki termit olisivat $2$, pätisi $[F : \mathbb{Q}] = 2^n$, mikä ei ole mielenkiintoista. Oletetaan siis, että jokin tulontekijä on $1$. Täten on olemassa sellainen $i$, jolla luvun $\sqrt{a_i}$ minimaalisen polynomin aste kunnassa $\mathbb{Q}(\sqrt{a_1}, \ldots \sqrt{a_{i-1}})$ on $1$, eli $\sqrt{a_i}$ kuuluu tähän kuntaan. Siispä $\sqrt{a_i}$ voidaan esitää polynomina luvuista $\sqrt{a_1}, \ldots , \sqrt{a_{i-1}}$. Nähdään, että tämä on ristiriita lineaarisesti riippumattomuuden kanssa.

