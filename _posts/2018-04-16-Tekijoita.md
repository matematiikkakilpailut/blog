---
layout: post
author: "Olli Järviniemi"
title: "Tekijöihinjakoa"
math: true
excerpt_separator: "<!--jatkuu-->"
---
<div class="hidden">
$\newcommand{\syt}{\mathop{\rm syt}}$
</div>

Tässä postauksessa käydään läpi muutama asia liittyen tekijöihinjakoon.

<!--jatkuu-->



Tekijöihin jakaminen on tärkeä taito kilpailumatematiikassa niin algebrallisten kuin lukuteoreettistenkin tehtävien parissa. Polynomien oletetaan olevan ennestään jo hieman tuttuja, ja kompleksilukujen perusominaisuudetkaan eivät ole pahitteeksi.

**Jakoyhtälö yhden muuttujan polynomeille**

Olkoot $P$ ja $Q$ polynomeja, $\deg(P) \ge \deg(Q)$. On olemassa polynomit $S$ ja $R$, joilla pätee

$$P(x) = Q(x)S(x) + R(x)$$ kaikilla $x \in \mathbb{R}$

missä $\deg(Q) > \deg(R)$. Tätä tulosta kutsutaan jakoyhtälöksi.

Saisimme tällä jaettua polynomin $P$ tekijöihin, jos $R$ olisi nollapolynomi.

Valitsemalla $Q$:n sopivasti voimme joskus saada polynomin $R$ nollapolynomiksi. Tämä onnistuu, jos kaikki $Q$:n nollakohdat ovat myös $P$:n nollakohtia (mukaan lukien kompleksinollakohdat).
Todistus väitteelle etenee seuraavasti: olkoot $x_1, x_2, \ldots x_n$ polynomin $Q$ kaikki nollakohdat (tässä $n = \deg(Q)$). Nyt, jokaisella $i$ pätee

$$R(x_i) = P(x_i) - Q(x_i)S(x_i) = 0 - 0 = 0$$

Täten polynomilla $R$ on vähintään $n$ nollakohtaa. Mutta $\deg(R) < \deg(Q) = n$, joten $R$:n tulee olla nollapolynomi.

Huomautus: todistuksessa ei kiinnitetty juurikaan huomiota moninkertaisiin nollakohtiin. Todistusta voidaan muokata käsittelemään myös moninkertaiset nollakohdat, mutta yksinkertaisuuden vuoksi jätämme asian sikseen. Lukija voi todistaa väitteen yleiselle tapaukselle.

Tämän avulla voimme jakaa tekijöihin polynomeja löytämällä helppoja nollakohtia,
kuten on tapana esimerkiksi lukiomatematiikassa. Huomautettakoon, että voimme myös
 löytää kompleksinollakohtia, joiden avulla saamme polynomille $P$ toisen asteen
tulontekijän. Esimerkiksi $P(x) = x^5 + x^3 - 2x^2 - 2$ on jaollinen polynomilla $Q(x) = x^2 + 1$. Tämän voi nähdä vaikkapa huomaamalla $P(i) = P(-i) = 0$.


**Usean muuttujan polynomit**
Usein kilpailutehtävissä esiintyy monen muuttujan polynomeja vain yhden muuttujan sijasta. Jakoyhtälö ei suoraan yleisty monelle muuttujalle, mutta samantapainen idea toimii.

**Esimerkki** (Valmennustehtävät, helmikuu 2018, tehtävä 12)

Olkoot $x, y, z$ reaalilukuja, jotka toteuttavat ehdot $x + y \ge 2z$ ja $y + z \ge 2x$. Osoita, että

$$5(x^3 + y^3 + z^3) + 12xyz \ge 3(x^2 + y^2 + z^2)(x+y+z)$$

ja että yhtäsuuruus vallitsee jos ja vain jos $x + y = 2z$ tai $y + z = 2x$.

**Ratkaisu**

Merkitään $P(x, y, z) = $$5(x^3 + y^3 + z^3) + 12xyz - 3(x^2 + y^2 + z^2)(x+y+z)$. Tehtävänannossa pyydetään osoittamaan muiden asioiden ohessa, että $P(x, y, z) = 0$, kun $2z = x + y$. Tämä on helppoa tarkistaa. Nollakohdan löytyminen tarkoittaa käytännössä sitä, että $P$ on jaollinen termillä $x+y-2z$. Vastaavasti saamme toisesta yhtäsuuruusehtoa koskevasta väitteestä tekijäksi lausekkeen $2x - y - z$. Sillä $P$ on symmetrinen polynomi, on sillä myös kolmas analoginen tekijä. Tästä voimme jo päätellä, että

$$P(x, y, z) = (x + y - 2z)(x - 2y + z)(2x - y - z)Q(x, y, z)$$

jollain polynomilla $Q$. Sillä $P$:n aste on $3$, ja yhtälön oikean puolen aste on $\deg(Q) + 3$, on $Q$ vakiopolynomi. On helppoa saada kokeilemalla, että $Q = 1$. Tehtävän viimeisteleminen on helppoa, ja jätetään lukijalle.

**Identiteetit**

Kisatehtävissä tulee usein vastaan erilaiset identiteetit. Niiden opetteleminen ei ole hauskaa, mutta tärkeimmät on hyvä muistaa ulkoa. Kaikkea ei tarvitse opetella ulkoa, mutta tärkeää on kuitenkin tietää, mitkä lausekkeet jakaantuvat tekijöihin ja tarvittaessa pystyä johtamaan tulomuodot.

$x^n - y^n$ jakautuu helposti kahen termin tuloksi, joista toinen on $x - y$. Saamme sijoituksella $z = -y$ tulomuodon lausekkeelle $x^n + y^n$, kun $n$ on pariton. Hieman yllättäen pätee myös, että $x^4 + y^4$ jakautuu tekijöihin:

$x^4 + y^4 = (x^2 + y^2)^2 - (\sqrt{2}xy)^2$

Tämä on kahden neliön erotus, ja voidaan jakaa tekijöihin. Huomaa, että tekijöissä tulee olemaan $\sqrt{2}$ kertoimena, joten emme voi suoraan jakaa lauseketta tekijöihin kokonaisluvuissa.

Toteamme siis, että $x^n \pm y^n$ **jakautuu aina tekijöihin, paitsi tapauksessa $x^2 + y^2$**. Nimittäin, jos luvulla $n$ on pariton alkutekijä, voimme ottaa tulontekijäksi $x+y$, ja jos $n$ on jaollinen neljällä, voimme käyttää tulohajotelmaa lausekkeelle $x^4 + y^4$. (Huomaa siis, että voimme kirjoittaa esimerkiksi $x^8 + y^8 = (x^2)^4 + (y^2)^4$, ja jakaa tämän tekijöihin).


Henkilökohtaisesti pidän seuraavista tekijöihinjaoista:

$a^3 + b^3 + c^3 - 3abc = \frac{1}{2}(a+b+c)((a-b)^2 + (b-c)^2 + (c-a)^2)$

$x^3 + y^3 = (x+y)((x+y)^2 - 3xy)$

Vielä viimeisenä mainitaan Sophie Germainin identiteetti, jonka avulla lauseke $a^4 + 4b^4$ voidaan jakaa tekijöihin. Tässä on hyvä huomata, että tekijöiden kertoimet ovat kokonaislukuja, toisin kuin lausekkeen $x^4 + y^4$ tapauksessa.

$$a^4 + 4b^4 = (a^2 + 2b^2)^2 - (2ab)^2 = (a^2 - 2ab + 2b^2)(a^2 + 2ab + 2b^2)$$

**Esimerkki** (Valmennusviikonloppu 2017, helmikuu, Otte Heinävaaran lukuteoriamoniste, tehtävä 7)

Etsi kaikki epänegatiiviset kokonaisluvut $m$, joilla

$$a_m = (2^{2m+1})^2 + 1$$

on jaollinen enintään kahdella erisuurella alkuluvlla.

**Ratkaisu**

Käytetään Sophie-Germainin identiteettiä

$a_m = 4\cdot 2^{4m} + 1= 4\cdot (2^m)^4 + 1 = (2^{2m+1} - 2^{m+1} + 1)(2^{2m + 1} + 2^{m+1} + 1)$

Merkitään $x = 2^{2m + 1} - 2^{m+1} + 1$ ja $y = 2^{2m + 1} + 2^{m+1} + 1$.

Ensinnäkin, $x, y > 1$ kaikilla $m > 0$. $m = 0$ on ratkaisu tehtävään. Sivutetaan se loppuratkaisun ajaksi.

 Huomataan, että $\syt(x, y) \mid y - x = 2^{2m+2}$. Mutta $x$ ja $y$ ovat parittomia, joten $\syt(x, y) = 1$. Siispä jos $a_m$ on jaollinen enintään kahdella erisuurella alkuluvulla, tulee sekä luvun $x$ että luvun $y$ olla alkuluvun potenssi.

Tutkimalla modulo $5$ saamme, että $a_m$ on aina jaollinen viidellä. Täten joko $x$ tai $y$ on jaollinen viidellä. Jaetaan ratkaisu kahteen osaan.

**Tapaus 1. $x$ on viiden potenssi**

Tulee olla $2^{2m + 1} - 2^{m+1} + 1 = 5^k$, eli
$2^{m+1} (2^m - 1) = 5^k - 1$

Tässä kohtaa ratkaisua käännytään ns. Lifting the Exponent Lemman (LTE) puoleen. Hyvä materiaali aiheesta löytyy osoitteesta

 [Lifting The Exponent Lemma]( http://s3.amazonaws.com/aops-cdn.artofproblemsolving.com/resources/articles/lifting-the-exponent.pdf
   )

Osoite sisältää lauseen, todistuksen ja runsaasti harjoitustehtäviä. Sillä LTE on hyvin tärkeä, kirjoitan lauseen vielä tähän:

**LTE**

Olkoon $p$ pariton alkuluku, jolla $p \mid x - y$, $p \nmid xy$. Olkoon $n \in \mathbb{Z_+}$. Pätee

$$v_p(x^n - y^n) = v_p(x - y) + v_p(n)$$

missä $v_p(m)$ on suurin $p$:n potenssi, joka jakaa luvun $m$. Lisäksi tapauksessa $p = 2$ pätee (olettaen samat ehdot kuin edellä)

$$v_2(x^n - y^n) = v_2(x-y) + v_2(x+y) + v_2(n) - 1$$

Sitten, takaisin ratkaisuun.

Tutkitaan suurinta kakkosen eksponettia, joka jakaa yhtälön kunkin puolen. Vasemmalle puolelle tämä on $m+1$, ja oikealle puolelle

$v_2(5^k - 1) =  v_2(k) + 2 = m+1$. Täten, $k \ge 2^{m-1}$.

Luvun $k$ tulee olla hyvin suuri, joten yhtälöllä ei ole kovin montaa ratkaisua. Tarkemmin,

$5^k - 1 \ge 5^{2^{m-1}} - 1 \ge 5^{m+1} - 1 > 4^{m+1} - 1 > 2^{2m+1} - 1 > 2^{m+1}(2^m - 1)$
kaikilla $m \ge 3$. Siis yhtälöllä voi olla ratkaisuja vain jos $m = 1$ tai $m = 2$.
$m = 1$ on ratkaisu, ja niin myös $m = 2$, sillä $a_2 = 1025 = 5^2 \cdot 41$.

**Tapaus 2. $y$ on viiden potenssi**
Jos taas $y$ on luvun $5$ potenssi, on

$2^{2m+1} + 2^{m+1} + 1 = 5^k  $

Voimme edetä tässä samalla tavalla kuin aiemmassakin tapauksessa. Emme saa täältä uusia ratkaisuja.

Siis ainoat ratkaisut alkuperäiseen tehtävään ovat $m = 0, 1, 2$.


**Harjoitustehtäviä**
Tässä on pari tehtävää, joiden (yksi) ratkaisu perustuu paljolti tekijöihinjakoon (aika spoilaus).

**Lukion matematiikkakilpailun loppukilpailu, 1999, tehtävä 3**

Selvitä, montako alkulukua on jonossa
$$101, 10101, 1010101, \ldots $$

**Pohjoismainen 2003, tehtävä 2**

Etsi kaikki kokonaislukukolmikot $(x, y, z)$, joille

$$x^3 + y^3 + z^3 - 3xyz = 2003$$

**Baltian tie -valintakoe 2016, tehtävä 4**

Reaaliluvuille $a$, $b$, $c$ on voimassa

$$(2b-a)^2 + (2b-c)^2 = 2(2b^2 - ac)$$

Osoita, että $a$, $b$ ja $c$ ovat jonkin aritmeettisen jonon kolme peräkkäistä jäsentä.

**Valmennustehtävät 2017, huhti-toukokuu, tehtävä 14**

Olkoot $a$, $b$ ja $c$ sellaisia reaalilukuja, ettei niistä minkään kahden summa ole nolla. Osoita, että

$$\frac{a^5 + b^5 + c^5 - (a+b+c)^5}{a^3 + b^3 + c^3 - (a+b+c)^3} \ge \frac{10}{9}(a+b+c)^2$$
