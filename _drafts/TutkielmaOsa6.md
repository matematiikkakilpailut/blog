---
layout: post
author: "Olli Järviniemi"
title: "Polynomien yhteiset alkutekijät, osa 6: yleinen tapaus"
math: true
excerpt_separator: "<!--jatkuu-->"

---

Tässä postauksessa esitetään tapa laajentaa heikko versio lauseesta 1 yleiseen tapaukseen.


<!--jatkuu-->

**Sisällysluettelo**

1. [Osa 1 - johdanto](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAjohdanto.html)
2. [Osa 2 - esitiedot](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAesitiedot.html)
3. [Osa 3 - tulokset](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAtulokset.html)
4. [Osa 4 - motivaatio](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAmotivaatio.html)
5. [Osa 5 - heikko versio](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAheikko.html)
6. Osa 6 - yleinen tapaus
7. [Osa 7 - lause 2](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAlause2.html)
8. [Osa 8 - lause 3](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAlause3.html)
9. [Osa 9 - lause 4](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAlause4.html)
10. [Osa 10 - sovelluksia](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAsovelluksia.html)
11. [Osa 11 - lisäaiheita](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAlisaaiheita.html)


Tämän postauksen tulokset ovat täysin alkeellisia, joten jätän joitain rutiininomaisia tarkistuksia lukijalle.

Ensiksi tämän postauksen tärkein ja vaikein lemma, joka on mielestäni melko pitkästyttävä. On varmaankin nautinnollisempaa yrittää todistaa lause itse kuin lukea kirjoittamani todistus.

### Lemma 7

Olkoot $A, B \in \mathbb{Z_*}[x]$. Oletetaan, että on olemassa sellainen $D \in \mathbb{Z_*}[x]$, jolla pätee seuraavat ehdot:

1. $S(A) \cap S(B) \approx S(D)$
2. $S_v(A) \cap S_v(B) \subset S_v(D)$

Tällöin on olemassa sellainen $D_*$, jolla $S_d(A) \cap S_d(B) = S_d(D_*)$.

Lemma 7 siis osoittaa, että mikäli on olemassa $D$, joka on melkein toimiva, niin on olemassa täysin toimiva $D_*$.

**Todistus**

Pätee $S_d(A) \cap S_d(B) \approx S_d(D)$ seuraten ehdosta 1.

Tutkitaan siis niitä äärellisen montaa $p$, joilla $p^k$ kuuluu vain toiseen joukoista $S_d(A) \cap S_d(B)$ ja $S_d(D)$. Käsitellään nämä $p$ jakaantumalla kahteen eri tapaukseen sen mukaan, kumpaan näistä joukoista $p^k$ ei kuulu.

Tapaus 1. $p^k \in S_d(A) \cap S_d(B)$, mutta $p^k \not\in S_d(D)$. Ehdon 2 nojalla tälöin $p \not\in S_v(A) \cap S_v(B)$, koska muuten $p \in S_v(D)$. Olkoon $v_1$ suurin luku, jolla $p^{v_1} \in S_d(A) \cap S_d(B)$. Olkoon $v_2$ vastaavasti suurin, jolla $p^{v_2} \in S_d(D)$. Olkoon $D_p(x) = p^{v_2 - v_1}D(x)$. Ei ole vaikeaa osoittaa, että polynomilla $D_p$ on seuraava ominaisuus:

Kaikilla alkuluvuilla $q \neq p$ pätee $q^t \in S_d(D) \Leftrightarrow q^t \in S_d(D_p)$ kaikilla $t \in \mathbb{Z}_+$, ja $p^s \in S_d(A) \cap S_d(B) \Leftrightarrow p^s \in S_d(D_p) \forall s \in \mathbb{Z}_+$.

Tämä operaatio siis korjaa alkuluvun $p$.

Tapaus 2. $p^k \in S_d(D)$, mutta $p^k \not\in S_d(A) \cap S_d(B)$. Ideana on eliminoida $D$:n alkutekijä $p$. Jos $D(0) = 0$, muutetaan $D$ polynomiksi $D(x + C)$, missä $C$ on mielivaltaisen suuri vakio. Tämä ei muuta tekijöitä. Oletetaan siis, että $D(0) \neq 0$.

Olkoon $v = v_p(D(0))$, mikä on äärellinen edellisen nojalla. Valitaan

$$D_p(x) = \frac{D(p^{v+1}x)}{p^v}$$

Ei ole vaikeaa osoittaa, että seuraavat ehdot pätevät:

1. $D_p$:n kaikki kertoimet vakiokerrointa lukuun ottamatta ovat jaollisia $p$:llä. Siis $p \not\in S(D_p)$.

2. Kaikilla $q \neq p$ pätee $q^t \in S_d(D) \Leftrightarrow q^t \in S_d(D_p)$.

Tämän jälkeen kerrotaan $D_p$ sopivalla $p$:n potenssilla, jotta alkuluku $p$ saadaan korjatuksi.

Suorittamalla operaatiot kaikille äärellisen monelle $p$ saadaan luotua $D_*$, jolla $p^k \in S_d(A) \cap S_d(B) \Leftrightarrow p^k \in S_d(D_*)$. Lemman 1 nojalla pätee $S_d(A) \cap S_d(B) = S_d(D_*)$.

### Lemma 8

Lemma 8 käsittelee pääpolynomeja: tällä saadaan korjattua heikossa versiossa tehty oletus siitä, että $A$ ja $B$ ovat pääpolynomeja.

**Väite**

Olkoon $P \in \mathbb{Z_*}[x]$. On olemassa pääpolynomi $Q \in \mathbb{Z_*}[x]$, jolla $S(P) \approx S(Q)$ ja $S_v(P) \subset S_v(Q)$.

**Todistus**

Olkoon $d = \deg(P)$ ja $c$ polynomin $P$ korkeimman asteen termin kerroin. Valitaan

$$Q(x) = c^{d-1}P(\frac{x}{c})$$

Ei ole vaikeaa osoittaa, että $q^t \in S_d(Q) \Leftrightarrow q^t \in S_d(P)$ kaikilla alkuluvuilla $q \nmid c$. Lisäksi on helppoa osoittaa $S_v(P) \subset S_v(Q)$. Lisäksi helppo lasku osoittaa, että $Q$ on kokonaislukukertoiminen pääpolynomi.


### Lemma 9

Lemma 9 osoittaa, että lauseen 1 väite pätee kaikilla jaottomilla $A, B$. Tämän jälkeen ei ole enää vaikeaa osoittaa väitettä kaikille $A, B$.

**Väite**

Olkoot $A, B \in \mathbb{Z_*}[x]$ jaottomia. On olemassa sellainen $D$, jolla $S_d(A) \cap S_d(B) = S_d(D)$.

**Todistus**

Väite seuraa pääpolynomeille suoraan heikon version ja lemman 7 avulla.

Olkoot $A, B \in \mathbb{Z_*}[x]$ nyt mielivaltaisia jaottomia polynomeja. Olkoot $A_*, B_*$ ne pääpolynomit, jotka saadaan lemmasta 8 polynomeille $A, B$. Tällöin $A_*, B_*$ ovat myös jaottomia. Siispä on olemassa sellainen $D_*$, jolla $S_d(A_*) \cap S_d(B_*) = S_d(D_*)$.

Lemman 8 nojalla pätee $S_v(A) \cap S_v(B) \subset S_v(A_*) \cap S_v(B_*) = S_v(D_*)$. Vastaavasti, $S(A) \cap S(B) \approx S(A_*) \cap S(B_*) = S(D_*)$. Polynomi $D_*$ on täten lemman 7 mukaisesti tarpeeksi lähellä toimivuutta polynomeille $A, B$, joten on olemassa sellainen $D$, jolla $S_d(A) \cap S_d(B) = S_d(D)$.

### Lemma 10

Lemma 10 on hyvin helppo, mutta myös mielenkiintoinen - se todistaa lauseen 1 väitteen tekijöiden yhdisteelle leikkauksen sijasta.

**Väite**

Olkoot $A, B \in \mathbb{Z_*}[x]$. On olemassa sellainen $D \in \mathbb{Z_*}[x]$, jolla $S_d(A) \cup S_d(B) = S_d(D)$.


**Todistus**

Valitaan $D = AB$. Ei ole vaikeaa nähdä, että $D$ toteuttaa lemman 7 ehdot polynomeille $A, B$. Vaikka lemmassa 7 puhutaankin joukkojen $S(A) \cap S(B)$ leikkauksesta, ei missään käytetty tietoa siitä, että kyseessä on juuri leikkaus eikä vaikkapa unioni. Siispä on olemassa sellainen $D_*$, jolla $S_d(A) \cap S_d(B) = S_d(D_*)$.

Lemman tuloksen voi yleistää induktiolla mielivaltaiselle määrälle polynomeja.

## Lauseen 1 todistus

Pääsemme vihdoinkin itse asiaan. Väite pätee jo jaottomille $A, B$ lemman 9 nojalla. Osoitetaan väite nyt mielivaltaisille $A, B$. Ideana on yhdistellä lemman 9 mukaisia polynomeja $A$:n ja $B$:n jaottomille tekijöille lemman 10 avulla. Tämä ei ole kovin vaikeaa.

Olkoot $A = A_1A_2 \ldots A_a$ ja $B = B_1B_2 \ldots B_b$, missä $A_i, B_j \in \mathbb{Z_*}[x]$ ovat jaottomia. (Tämä tekijöihinjako on mahdollinen, kts. esitiedot.)

Olkoon $D_{i, j}$ lemman 9 mukaisesti sellainen, jolla $S_d(A_i) \cap S_d(B_j) = S_d(D_{i, j})$. Olkoon $D$ lemman 10 mukaisesti sellainen, jolla

$$S_d(D) = \bigcup_{i, j} S_d(D_{i, j})$$

On suoraviivaista tarkistaa, että $S_v(D) = S_v(A) \cap S_v(B)$ (valitse jokin $p \in S_v(D)$, ja osoita, että $p \in S_v(A) \cap S_v(B)$. Toista toiseen suuntaan). Täten lemman 7 nojalla on olemassa selliainen $D_*$, jolla $S_d(D_*) = S_d(A_*) \cap S_d(B_*)$.


### $D$:n aste

Lauseessa luvattiin myös, että $\deg(D) = \deg(P_1)\deg(P_2) \ldots \deg(P_n)$. Riittää osoittaa tämä kun $n = 2$, koska induktio hoitaa loput $n$.

Tutkitaan ensin heikon version tuottamaa $D$. Se on tulo polynomeista $D_1, D_2, \ldots , D_t$. Polynomin $D_i$ aste on sama kuin kuntalaajennuksen $\mathbb{Q}(\gamma_i) / \mathbb{Q}$ aste. Siispä

$$\deg(D_i) = [\mathbb{Q}(\gamma_i) : \mathbb{Q}] = [\mathbb{Q}(\alpha, \beta_i) : \mathbb{Q}]$$

Käyttäen tulon kuntalaajennusten multiplikatiivisuutta

$$= [\mathbb{Q}(\alpha, \beta_i) : \mathbb{Q}(\alpha)][\mathbb{Q}(\alpha) : \mathbb{Q}]$$

Kuntalaajennuksen $\mathbb{Q}(\alpha) / \mathbb{Q}$ aste on luvun $\alpha$ minimaalisen polynomin aste (kunnassa $\mathbb{Q}$), eli $\deg(A)$.

Olkoon $K = \mathbb{Q}(\alpha)$. Kuntalaajennuksen $\mathbb{Q}(\alpha, \beta_i) / \mathbb{Q}(\alpha) = K(\beta_i) / K$ aste on luvun $\beta_i$ minimaalisen polynomin aste (kunnassa $K$), eli $\deg(E_i)$.

Siis $\deg(D_i) = \deg(A)\deg(E_i)$. Täten


$$\deg(D) = \deg(D_1D_2 \ldots D_t) = \deg(D_1) + \deg(D_2) + \ldots + \deg(D_t)$$

$$ = \deg(A) \sum \deg(E_i) = \deg(A)\deg(B)$$

Tämä osoittaa väitteen. Se, että tämä on joskus pienin mahdollinen aste, todistetaan lauseen 2 yhteydessä.
