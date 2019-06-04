---
layout: post
author: "Olli Järviniemi"
title: "Polynomien yhteiset alkutekijät, osa 5: heikko versio"
math: true
excerpt_separator: "<!--jatkuu-->"

---

Tässä postauksessa esitetään todistus lauseen 1 heikolle versiolle.


<!--jatkuu-->

**Sisällysluettelo**

1. [Osa 1 - johdanto](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAjohdanto.html)
2. [Osa 2 - esitiedot](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAesitiedot.html)
3. [Osa 3 - tulokset](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAtulokset.html)
4. [Osa 4 - motivaatio](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAmotivaatio.html)
5. Osa 5 - heikko versio
6. [Osa 6 - yleinen tapaus](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAyleinen.html)
7. [Osa 7 - lause 2](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAlause2.html)
8. [Osa 8 - lause 3](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAlause3.html)
9. [Osa 9 - lause 4](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAlause4.html)
10. [Osa 10 - sovelluksia](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAsovelluksia.html)
11. [Osa 11 - lisäaiheita](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAlisaaiheita.html)


Tavoitteena on osoittaa seuraava väite:

Olkoot $A, B \in \mathbb{Z_c}[x]$ **jaottomia pääpolynomeja**. On olemassa sellainen $D \in \mathbb{Z_c}[x]$, joka toteuttaa seuraavat ehdot:

1. $S(A) \cap S(B) \approx S(D)$.
2. $S_v(A) \subset S_v(B) \subset S_v(D)$.

Miksi juuri nämä ehdot? Ehto 1 kertoo, että on vain äärellisen monta myöhemmin korjattavaa alkulukua. Ehto 2 takaa sen, ettei $D$:stä puutu yhtäkään vahvaa alkutekijää. Tämä on tärkeää, koska en löytänyt operaatiota, jolla vahvan alkutekijän voisi luoda (mutta poistaminen onnistuu). Epäilen, että vahvan alkutekijän lisääminen ei edes aina ole mahdollista. Esimerkiksi, onko olemassa polynomi $P$, jolla on muuten samat alkutekijät kuin polynomilla $x^2 + 1$, mutta jolla pätee $2 \in S_v(P)$?

Ehto siitä, että $A, B$ eivät jakaudu, on myös korjattavissa: on intuitiivista, että väite voidaan laajentaa myöhemmin kaikille polynomeille.

Ehto siitä, että $A, B$ ovat pääpolynomeja, ei ole niin ilmeinen. Syy tämän taustalla on ehdon 2 varmistaminen: heikon version todistaminen niin, että ehto 1 toimii, oli suhteellisen helppoa. Ongelmia tuotti ehto 2. Lisäehto siitä, että $A, B$ ovat pääpolynomeja auttaa varmistamaan ehdon 2, kuten myöhemmin nähdään. Yleisen tapauksen todistuksessa saadaan laajennettua väite pääpolynomeilta kaikille polynomeille.

Heikon version ehdot saadaan siis suoraan siitä, mitä muunnoksia kyetään tekemään.

# Todistus

Kuten edellisessä postauksessa mainittiin, osoitetaan ensin, että on olemassa vastaavuus kompleksijuurien ja nollakohtien (mod $p^k$) välillä.

## Vastaavuus

Olkoon $A(\alpha) = 0$, $A$ jaoton pääpolynomi, ja olkoon $A(a) \equiv 0 \pmod{p^k}$. Tavoitteena on luoda hyvin määritelty kuvaus, joka kuvaa luvun $\alpha$ lukuun $a$. Tätä alustetaan seuraavalla lemmalla.

## Lemma 3

Olkoon $A \in \mathbb{Z_c}[x]$ jaoton, ja olkoon $\alpha$ jokin sen juuri. Olkoon $p$ sellainen, joka ei jaa $A$:n korkeimman asteen termin kerrointa. Olkoot $k \in \mathbb{Z}_+$ ja $a \in \mathbb{Z}$ sellaisia, joilla $A(a) \equiv 0 \pmod{p^k}$.

Olkoon $P \in \mathbb{Z_c}[x]$ sellainen, jolla $P(\alpha) = 0$. Tällöin $P(a) \equiv 0 \pmod{p^k}$.

**Todistus**

Olkoon $c_d$ $A$:n korkeimman asteen termin kerroin. Tällöin polynomi $\frac{A}{c_d}$ on luvun $\alpha$ minimaalinen polynomi (koska $A$ on jaoton). Koska $P(\alpha) = 0$, on se jaollinen luvun $\alpha$ minimaalisella polynomilla. Siispä

$$\frac{A}{c_d} \mid P$$

On siis olemassa sellainen $Q \in \mathbb{Q}[x]$, jolla $P = AQ$.

Riittää osoittaa, että $Q$:n kertoimien nimittäjät eivät ole jaollisia $p$:llä, koska tällöin $P(a) = A(a)Q(a)$ on jaollinen luvulla $p^k$ (laajennettu jaollisuuden määritelmä, mutta sopivalla vakiolla kertominen puolittain toimii myös).

Se, mitä tapahtuu seuraavaksi, ei ole kovin mielenkiintoista. Ideana on vain tehdä vastaoletus ja saada ristiriita kahdella tavalla laskemisella.

Olkoot

$$A(x) = a_{d_a}x^{d_a} + \ldots + a_1x + a_0$$

$$P(x) = p_{d_p}x^{d_p} + \ldots + p_1x + p_0$$

$$Q(x) = q_{d_q}x^{d_q} + \ldots + q_1x + q_0$$

(Lupasin aiemmin, että kirjain $p$ viittaa aina alkulukuun. Tässä tapahtui nyt pieni lipsahdus muuttujien nimeämisessä. $p_i$ ei siis ole välttämättä alkuluku, vaan jokin kokonaisluku.)

Oletetaan, että jonkin $q_i$ nimittäjä on jaollinen $p$:llä. Valitaan näistä $i$ suurin mahdollinen. Tutkitaan termin $x^{d_a + i}$ kerrointa $P$:ssä. Tämä on määritelmän nojalla $p_{d_a + i}$, eli kokonaisluku. Mutta toisaalta, tämä on yhtälön $P = AQ$ nojalla


$$q_ia_{d_a} + q_{i+1}a_{d_a - 1} + \ldots $$

Termit ovat siis muotoa $q_{i+j}a_{d_a - j}$. Jos $j > 0$, kyseessä on rationaaliluku, jonka nimittäjä ei ole jaollinen $p$:llä, koska luvut $a_0, a_1, \ldots$ ovat kokonaislukuja, ja $i$ määriteltiin olemaan suurin indeksi, jolla luvun $q_i$ nimittäjä on jaollinen $p$:llä.

Summa voidaan siis kirjoittaa muodossa

$$q_ia_{d_a} + \frac{x}{y}$$

missä $p \nmid y$. Kirjoitetaan $q_ia_{d_a} = \frac{v}{w}$. Koska $p$ jakaa $q_i$:n nimittäjän, ja oletuksen nojalla $p$ ei jaa lukua $a_{d_a}$, pätee $p \mid w$ ja $p \nmid v$. Ja nyt,

$$p_{d_a + i} = \frac{v}{w} + \frac{x}{y} = \frac{vy + wx}{yw}$$

Tässä $p \mid yw$, mutta $p \nmid vy + wx$, koska $p \mid wx$ ja $p \nmid vy$. Olemme saaneet aikaan ristiriidan.


## Alustus lemmalle 4

Lemma 4 muodostaa halutun kuvauksen, joka formalisoi aiemmin mainitun vastaavuuden. Tätä ennen määritellään joukko $\mathbb{Z}_p(\alpha)$. Määrittely voi tuntua hieman ikävältä, mutta idea on yksinkertainen: haluamme kuvata $\mathbb{Q}(\alpha)$:n alkioita kokonaisluvuille mod $p^k$. Lukua $\frac{1}{p} \in \mathbb{Q}(\alpha)$ on kuitenkin käytännössä katsoen mahdotonta kuvata kokonaisluvuksi mod $p^k$ niin, että lopputulos olisi järkevä. Meidän tulee siis hieman valikoida lukuja, joita kuvaamme.

**Määritelmä - $\mathbb{Z}_p(\alpha)$**

Kunta $\mathbb{Q}(\alpha)$ voidaan tulkita $\mathbb{Q}$-vektoriavaruutena, jonka kanta on $\lbrace 1, \alpha, \alpha^2, \ldots , \alpha^{n-1}\rbrace$ (tässä $n$ on $\alpha$:n minimaalisen polynomin aste). Olkoon $\mathbb{Z}_p(\alpha)$ niiden $x \in \mathbb{Q}(\alpha)$ joukko, joilla $x$:n esitys kannan avulla ei sisällä rationaalilukuja, joiden nimittäjät ovat jaollisia $p$:llä.

Toisin sanoen, $\mathbb{Z}_p(\alpha)$ sisältää ne luvut $x$, jotka ovat muotoa $P(\alpha)$, $\deg(P) < n$, ja $P$:n kertoimien nimittäjät eivät ole jaollisia $p$:llä.

Esimerkiksi $\mathbb{Z}_7(\sqrt{2})$ sisältää luvut muotoa $a + b\sqrt{2}, a, b \in \mathbb{Q}$, missä $7$ ei jaa lukujen $a, b$ nimittäjiä.

Olkoon $A \in \mathbb{Z_c}[x]$ jaoton, ja olkoon $\alpha$ sen juuri. Olkoon $p$ alkuluku, joka ei jaa $A$:n korkeimman asteen termin kerrointa. Väitän, että $\mathbb{Z}_p(\alpha)$ on rengas, eli siis eritysesti kahden joukon $\mathbb{Z}_p(\alpha)$ tulo on myös tämän joukon alkio.

Tämä on helppoa visualisoida samalla tavalla kuin osoitettiin, että $\alpha^k$ voidaan esittää pienempien $\alpha$:n potenssien avulla. Olkoon $A(x) = a_nx^n + \ldots + a_1x + a_0$. Tällöin

$$\alpha^n = -\frac{a_{n-1}\alpha^{n-1} + \ldots + a_0}{a_n}$$

Siispä $\alpha^n \in \mathbb{Z}_p(\alpha)$.

Yleisesti, kuvitellaan operaatiosarjaa, jolla redusoidaan $\alpha^k$ pienempien $\alpha$:n potenssien esitykseksi. Tällöin $\alpha^k$:n esityksessä käytetyt kertoimet eivät ole jaollisia $p$:llä (mistä $p$:llä jaollinen nimittäjä muka syntyisi?). Jos ei tähän vielä usko, niin voi osoittaa induktiolla muuttujan $k$ suhteen, että $\alpha^k \in \mathbb{Z}_p(\alpha)$.

Vielä määritellään homomorfismi.

**Määritelmä - homomorfismi**

Olkoot $R, S$ renkaita (eli kuin kunnat, muttei välttämättä käänteisalkiota. Esim. $\mathbb{Z}$ on rengas). Olkoon $f : R \to S$ kuvaus. Sanotaan, että $f$ on homomorfismi, jos

1. $f(xy) = f(x)f(y)$ kaikilla $x, y \in R$.
2. $f(x + y) = f(x) + f(y)$ kaikilla $x, y \in R$.
3. $f(1) = 1$.

Määritelmä on siis täsmälleen sama kuin isomorfismin tapauksessa, paitsi $f$:n ei tarvitse olla bijektio. Esimerkkinä homomorfista $f : \mathbb{Z} \to \mathbb{Z}_2$ (kokonaisluvuille mod $2$) toimii $f(2n) = 0$, $f(2n + 1) = 1$ kaikilla $n \in \mathbb{Z}$. Moduloon redusoiminen on siis vain homomorfismi.

Joku voisi väittää, että tällä $f$ ehto $2$ ei toteudu, onhan $0=f(0) = f(1 + 1) = f(1) + f(1) = 2$. Tämä kuitenkin toteutuu, kun yhtäsuuruutta ajatellaan $S$:n eli $\mathbb{Z}_2$:n näkökulmasta.

Tämä homomorfismi on juurikin se "hyvin määritelty kuvaus" mistä olen aiemmin puhunut:

## Lemma 4

Olkoon $A \in \mathbb{Z_c}[x]$ jaoton, ja olkoon $p$ alkuluku, joka ei jaa $A$:n korkeimman asteen termin kerrointa. Olkoon $A(a) \equiv 0 \pmod{p^k}$.

 On olemassa homomorfismi $f : \mathbb{Z}_p(\alpha) \to \mathbb{Z}_{p^k}$ (eli joukolta $\mathbb{Z}_p(\alpha)$ joukolle "kokonaisluvut modulo $p^k$"), jolla $f(\alpha) = a$.


**Todistus**

Määritellään yksinkertaisesti $f(P(\alpha)) = P(a)$ kaikilla $P$, joiden kertoimien nimittäjät eivät ole jaollisia $P$:llä. On selvää, että $f(\alpha) = a$, ja että $f$ toteuttaa homomorfismin määritelmän ehdot 1, 2, 3. Olemme siis valmiit. Vai olemmeko?

Funktion määritelmään kuuluu, että jokainen alkio kuvautuu täsmälleen yhteen alkioon. Toisin sanoen, jos $a = b$, niin $f(a) = f(b)$. Tämä tulee siis vielä varmistaa (monesti tämä on ilmeistä funktioita määritellessä, mutta tällä kertaa ei).

Olkoot $P_1, P_2$ jotain polynomeja, joiden kertoimet eivät ole jaollisia $p$:llä. Oletetaan, että $P_1(\alpha) = P_2(\alpha)$, ja osoitetaan, että $P_1(a) \equiv P_2(a) \pmod{p^k}$.

Olkoon $P(x) = P_1(x) - P_2(x)$. Tiedämme siis, että $P(\alpha) = 0$, ja haluamme osoittaa, että $P(a) \equiv 0 \pmod{p^k}$. Tämä pätee lemman 3 nojalla.

## Lemma 5

Lemman 5 tavoite on osoittaa, että $S_v(A) \cap S_v(B) \subset S_v(D)$, kun $D$ valitaan sopivasti. Määritellään seuraavaksi $D$.

Olkoon $\alpha$ jokin $A$:n juuri, joka pidetään vakiona tämän todistuksen loppuun saakka. Jaetaan $B$ tekijöihin kunnassa $\mathbb{Q}(\alpha)$. Olkoon siis $B(x) = E_1(x)E_2(x) \ldots E_t(x)$. Esitystapa voidaan valita niin, että $E_i$ ovat pääpolynomeja., koska $B$ on pääpolynomi. Oletetaan tietysti vielä, että $E_i$ ovat ei-vakioita ja jaottomia (kunnassa $\mathbb{Q}(\alpha)$).

Olkoon $\beta_i$ polynomin $E_i$ juuri kaikilla $i$. Olkoot $\gamma_i$ sellaisia, että $\mathbb{Q}(\alpha, \beta_i) = \mathbb{Q}(\gamma_i)$ kaikilla $i$. Kuten Primitive element theoremin todistuksesta voidaan lukea, että $\gamma_i$ voidaan valita olemaan muotoa $\alpha + n_i\beta_i$, missä $n_i$ on sopiva kokonaisluku. Tällä valinnalla ei juurikaan ole väliä, mutta se yksinkertaistaa todistusta.

Olkoon $D_i$ luvun $\gamma_i = \alpha + n_i\beta_i$ minimaalinen polynomi kaikilla $i$. Määritellään $D$ olemaan polynomien $D_i$ tulo. Voidaan osoittaa, että $D$ on kokonaislukukertoiminen (algebralliset kokonaisluvut ovat rengas), mutta tarvittaessa $D$ voitaisiin kertoa kertoimien nimittäjiensä tulolla.

Osoitetaan, että tällä $D$:llä pätee $S_v(A) \cap S_v(B) \subset S_v(D)$.

**Todistus**

Tutkitaan polynomia $F_i(x) := D_i(\alpha + n_ix)$. Tämä on polynomi, jonka kertoimet ovat kunnassa $\mathbb{Q}(\alpha)$. Lisäksi pätee $F_i(\beta_i) = D_i(\alpha + n_i\beta_i) = D_i(\gamma_i) = 0$. Täten $F_i$ on jaollinen luvun $\beta_i$ minimaalisella polynomilla (kunnassa $\mathbb{Q}(\alpha)$), eli polynomilla $E_i$.

Täten on olemassa sellainen polynomi $G_i \in \mathbb{Q}(\alpha)[x]$, jolla $F_i(x) = E_i(x)G_i(x)$, eli siis $D_i(\alpha + n_ix) = E_i(x)G_i(x)$. Kertomalla tätä muotoa olevat yhtälöt keskenään kaikilla $1 \le i \le t$ saadaan


$$D_1(\alpha + n_1x)\ldots D_t(\alpha + n_tx) = E_1(x) \ldots E_t(x)G_1(x) \ldots G_t(x) = B(x)G_1(x) \ldots G_t(x)$$

Olkoot $c_1, c_2, \ldots , c_t$ polynomien $G_1, G_2, \ldots , G_t$ kertoimien nimittäjien tulot. Olkoon $H_i(x) = G_i(x) \cdot c_i$, ja olkoon $H$ kaikkien $H_i$ tulo. Tällöin $H_i$:n kertoimet kuuluvat joukkoon $\mathbb{Z}_p(\alpha)$.

$$c_1c_2 \ldots c_t D_1(\alpha + n_1x) \ldots D_t(\alpha + n_tx) = B(x)H(x)$$

Osoitetaan nyt, että $p \in S_v(A) \cap S_v(B) \implies p \in S_v(D)$.

Olkoon $k$ jokin mielivaltaisen suuri kokonaisluku, ja oletetaan, että $A(a) \equiv B(b) \equiv 0 \pmod{p^k}$.

Olkoon $f : \mathbb{Z}_p(\alpha) \to \mathbb{Z_{p^k}}$ lemman 4 mukainen homomorfismi. Koska $A$ on pääpolynomi, $p$ ei jaa $A$:n korkeimman asteen termin kerrointa, eli tämä kuvaus on olemassa. Sijoitetaan yllä olevaan yhtälöön $x = b$, jolloin

$$c_1c_2 \ldots c_tD_1(\alpha + n_1b) \ldots = B(b)H(b)$$

Kuvataan molemmat puolet homomorfismilla $f$. Nähdään, että $f(D_i(\alpha + n_ib)) = D_i(a + n_ib)$ (tämän voi todistaa suoraan homomorfismien ominaisuuksista). Siispä

$$c_1 \ldots c_t D_1(a + n_1b) \ldots D_t(a + n_tb) = f(B(b)H(b)) = B(b)f(H(b))$$

Koska $B(b) \equiv 0 \pmod{p^k}$, pätee $B(b)f(H(b)) \equiv 0 \pmod{p^k}$. Täten

$$c_1 \ldots c_tD_1(a + n_1b) \ldots D_t(a + n_tb) \equiv 0 \pmod{p^k}$$

Nyt, jos $p$ ei olisi minkään $D_i$ vahva alkutekijä, olisi olemassa sellaiset $e_1, \ldots , e_t$, joilla yhtälöllä $D_i(x) \equiv 0 \pmod{p^{e_i}}$ ei ole ratkaisua. Olkoon $C = v_p(c_1 \ldots c_t)$, missä $v_p$ on [p-adic valuation](https://blog.matematiikkakilpailut.fi/2018/07/19/Vp.html). Ei ole vaikeaa nähdä, että yhtälöllä

$$c_1c_2 \ldots c_tD_1(x_1)D_2(x_2) \ldots D_t(x_t) \equiv 0 \pmod{p^k}$$

ei ole ratkaisua, kun $k > C + e_1 + e_2 + \ldots + e_t$. Tämä on ristiriita sen kanssa, että

$$c_1 \ldots c_tD_1(a + n_1b) \ldots D_t(a + n_tb) \equiv 0 \pmod{p^k}$$

kaikilla $k \in \mathbb{Z}_+$ (missä $a, b$ valitaan $k$:n mukaan). Siispä $p$:n pitää olla jonkin $D_i$ vahva alkutekijä. Tämä todistaa väitteen.


**Kommentteja**

Eikö ideana ollutkaan sieventää $D(a + b)$ modulo $p^k$? Yllä oleva todistus näyttää olevan melko kaukana tästä. Alunperin todistus oli tällainen, ja oikeastaan yllä oleva todistus on myös, mutta sieventäminen on piilotettu.

Mitä se sieventäminen todella on? Käytännössä se on polynomien jakoyhtälöä: esimerkiksi jos $\alpha^2 + 1 = 0$, luvun $\alpha^3$ sieventäminen on oikeasti sitä, että polynomi $x^3$ jaetaan jakokulmassa polynomilla $x^2 + 1$. Siispä jakoyhtälö on formaali tapa esittää sieventäminen.

Tutkitaan siis yhtälöä $D_i(\alpha + n_i\beta_i) = 0$. Käyttäen toistuvasti ehtoa $E_i(\beta_i) = 0$ saadaan ensiksi redusoitua kaikki $\beta_i$:t yhtälöstä. Lopuksi jäljellä on yhtälö muotoa $P(\alpha) = 0$, joka sieventyy käyttäen yhtälöä $A(\alpha) = 0$.

Aivan vastaavasti voidaan suorittaa yhtälön $D_i(a + n_ib) \equiv 0 \pmod{p^k}$ sieventäminen. Osio, jossa "$\beta_i$ tai $b$ sievennetään pois" vastaa lemman todistuksen kuvausta $f$ edeltävää osiota, ja $\alpha$:n tai $a$:n sieventäminen vastaa $f$:n käyttämistä. $f$ antaa formaalin tavan sieventää yhden muuttujan polynomeja.




## Heikon version todistuksen viimeistely

Edellä osoitettiin, että $S_v(A) \cap S_v(B) \subset S_v(D)$. Osoitetaan vielä toinen halutuista ehdoista, eli $S(A) \cap S(B) \approx S(D)$. Tämä on oikeastaan todistettu jo. Nimittäin, valitaan jokin $p \in S_v(D)$. Tällöin $p \in S_v(D_i)$ jollain $i$ (helppo vastaoletustodistus). Tällöin kysymyksen 2 todistuksen nojalla kaikilla paitsi äärellisen monella $p$ pätee väite $p \in S_v(A) \cap S_v(B)$.

Siis kaikki paitsi äärellisen moni $S_v(D)$:n alkio on myös $S_v(A) \cap S_v(B)$:n alkio. Käyttäen ehtoa $S_v(A) \cap S_v(B) \subset S_v(D)$ saadaan ehto

$$S_v(A) \cap S_v(B) \approx S_v(D)$$

Koska $S_v(P) \approx S(P)$ kaikilla $P \in \mathbb{Z_c}[x]$ lemman 2 nojalla, osoittaa tämä

$$S(A) \cap S(B) \approx S(D)$$


Kysymys 2 on työssäni lemma 6, joten lemmojen numerointi jatkuu luvusta 7.
