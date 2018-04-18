---
layout: post
author: "Akseli Jussinmäki, Joonatan Honkamaa, Olli Järviniemi"
title: "Rekursiivisen tehtävän monenlaisia ratkaisuja"
math: true
excerpt_separator: "<!--jatkuu-->"

---

Tässä postauksessa käydään kolme hyvin erilaista ja varsin mielenkiintoista ratkaisua seuraavalle tehtävälle:

**Valmennustehtävät, 2018 tammikuu, tehtävä 21**
Määritellään $a_0 = a_1 = 3$ ja $a_{n+1} = 7a_n - a_{n-1}$ jokaisella $n \in \mathbb{Z_+}$. Osoita, että $a_n - 2$ on neliöluku jokaisella $n \in \mathbb{Z_+}$.

<!--jatkuu-->

**Ensimmäinen ratkaisu (Akseli Jussinmäki)**

Tässä ratkaisussa käytetään apuna Fibonaccin lukuja. Määritellään $F_0=1$, $F_1=1$ ja $F_n=F_{n-1}+F_{n-2}$, kun $n\geq 2$

Kun $n=1$, niin $a_1-2=3-2=1$.
Kun $n\geq 2$, niin  $a_n-2=(F_{2n-4}+3F_{2n-3})^2$. Jos tämä pätee, niin selvästi $a_n-2$ on neliöluku kaikilla $n\in\mathbb{N}$. Todistetaan väite induktiolla. Todistetaan ensin tapaukset $n=2$ ja $n=3$:

  $a_2-2=21-3-2=16$ ja
   $(F_{2\times2-4}+3F_{2\times2-3})^{2}=(F_0+3F_1)^{2}=(1+3\times1)^{2}=4^{2}=16$.

  $a_3-2=7\times18-3-2=121$ ja
 $(F_{2\times3-4}+3F_{2\times3-3})^{2}=(F_2+3F_3)^{2}=(2+3\times3)^{2}=11^{2}=121$.

   Otetaan seuraavaksi induktioaskel, eli todistetaan, että $a_n-2=(F_{2n-4}+3F_{2n-3})^2$, kun $a_{n-1}-2=(F_{2n-6}+3F_{2n-5})^2$ ja $a_{n-2}-2=(F_{2n-8}+3F_{2n-7})^2$.

  $$a_n-2=(F_{2n-4}+3F_{2n-3})^2$$
  $$7a_{n-1}-a_{n-2}-2=(F_{2n-4}+3F_{2n-3})^2$$
  $$7((F_{2n-6}+3F_{2n-5})^2+2)-((F_{2n-8}+3F_{2n-7})^2+2)-2=(F_{2n-4}+3F_{2n-3})^2$$
  $$7(F_{2n-8}+F_{2n-7}+3(F_{2n-8}+2F_{2n-7}))^{2}+14-(F_{2n-8}+3F_{2n-7})^2-2-2=$$
          $$(2F_{2n-8}+3F_{2n-7}
  +3(3F_{2n-8}+5F_{2n-7}))^{2}$$
  $$7(4F_{2n-8}+7F_{2n-7})^{2}-(F_{2n-8}+3F_{2n-7})^2+10=(11F_{2n-8}+18F_{2n-7})^{2}$$
  $$112(F_{2n-8})^{2}+492(F_{2n-8})\times(F_{2n-7})+343(F_{2n-7})^{2}-(F_{2n-8})^{2}-6(F_{2n-8})\times(F_{2n-7})$$
  $$-9(F_{2n-7})^{2}+10=
  121(F_{2n-8})^{2}+396(F_{2n-8})\times(F_{2n-7})+324(F_{2n-7})^{2}$$
  $$10(F_{2n-7})^{2}-10(F_{2n-8})\times(F_{2n-7})-10(F_{2n-8})^{2}=-10$$
  $$(F_{2n-8})^{2}+(F_{2n-7})\times(F_{2n-8})-(F_{2n-7})^{2}=1$$

  Väite siis pätee, jos alimman rivin yhtälö pätee. Todistetaan sekin induktiolla. Halutaan siis osoittaa, että $$(F_{2a})^{2}+(F_{2a})\times(F_{2a+1})-(F_{2a+1})^{2}=1$$

  Selvästi tämä pätee, kun $a=0$: $F_0^{2}+(F_0)\times(F_1)-F_1^{2}=1+1-1=1$. Oletetaan nyt, että pätee $(F_{2a-2})^{2}+(F_{2a-2})\times(F_{2a-1})-(F_{2a-1})^{2}=1$. Mutta nyt $$(F_{2a})^{2}+(F_{2a})\times(F_{2a+1})-(F_{2a+1})^{2}$$
  $$=(F_{2a-2}+F_{2a-1})^{2}+(F_{2a-2}+F_{2a-1})\times(2F_{2a-1}+F_{2a-2})
  -(2F_{2a-1}+F_{2a-2})^{2}$$
  $$=(F_{2a-2})^{2}+2(F_{2a-2})\times(F_{2a-1})+(F_{2a-1})^{2}+(F_{2a-2})^{2}+3(F_{2a-2})\times(F_{2a-1})$$
  $$+2(F_{2a-1})^{2}-4(F_{2a-1})^{2}-4(F_{2a-2})\times(F_{2a-1})-(F_{2a-2})^{2}$$
  $$=(F_{2a-2})^{2}+(F_{2a-2})\times(F_{2a-1})-(F_{2a-1})^{2}=1.$$ Induktioaskel on otettu ja todistus on valmis.

  Motivaatio ratkaisun takana: Tehtävän todistamiseksi on mukavaa, jos $a_n-2$ saadaan esitettyä riittävän yksinkertaisten termien neliönä. Idean saamiseksi on loogista tarkastella, minkä lukujen neliöitä $a_n-2$:t ovat pienillä n:n arvoilla. $\sqrt{a_2-2}=4$, $\sqrt{a_3-2}=11$, $\sqrt{a_4-2}=29$. Sitten voi tarkastella näiden lukujen erotuksia siinä toivossa, että löytäisi niille jonkin kaavan. $29-11=18$, $11-4=7$, $4-1=3$. Nyt voidaan huomata, että neliöjuuret ja niiden erotukset saadaan lisäämällä yhteen edelliset neliöjuuri ja erotus tai erotus ja neliöjuuri: $1+3=4$, $3+4=7$, $4+7=11$, $7+11=18$ ja $11+18=29$. Tässä on mukavasti logiikkaa. Kirjoitetaan seuraavaksi neliöjuuret ykkösten ja kolmosten summana: $4=1\times1+1\times3$, $11=1+3+(1+3+3)=2\times1+3\times3$, $29=2\times1+3\times3+3\times1+5\times3=5\times1+8\times3$
 Nyt huomataan, että kertoimet ovat Fibonaccin lukuja ja voidaan päätyä ratkaisun alussa näkyvään yhtälöön.









**Toinen ratkaisu (Joonatan Honkamaa)**

Määritellään $b_1=1, b_2=4$ ja $b_{n+1}=3b_n-b_{n-1}$. Osoitetaan, että $a_n-2={b_n}^2$ kaikilla positiivisilla kokonaisluvuilla $n$. Tämä riittääkin tehtävän ratkaisemiseksi. Todistetaan ensin seuraava tulos:

Olkoon $b_1=1, b_2=4$ ja $b_{n+1}=3b_n-b_{n-1}$. $\forall$ $n \in \mathbb{N} $ pätee ${b_{n+1}}^2-3b_{n+1}b_n+{b_n}^2=5$.

**Todistus.** Todistetaan väite induktiolla. Kun $n=1$, niin $ 4^2-3\cdot 4 \cdot 1 +1^2=5$ eli väite pätee. Oletetaan sitten, että väite pätee, kun $n = m-2$ ja osoitetaan, että se pätee, kun $n = m-1$.
Käyttämällä rekursioyhtälöä saamme:
$
{b_m}^2-3{b_m}b_{m-1}+{b_{m-1}}^2=
$
$
9{b_{m-1}}^2-6b_{m-1}b_{m-2}+{b_{m-2}}^2-9{b_{m-1}}^2+3b_{m-1}b_{m-2}+{b_{m-1}}^2=
$
$
{b_{m-1}}^2-3b_{m-1}b_{m-2}+{b_{m-2}}^2
$
Todistus on valmis.

Osoitetaan sitten induktiolla, että ${b_n}^2=a_n -2$.
 Kun $n=1$, $ 3-2=1=1^2 $ eli väite pätee.
 Kun $n=2$, $ 7\cdot3-1\cdot3-2=16=4^2$, eli väite pätee.
Oletetaan, että väite pätee, kun $n = m$ ja kun $n = m-1 $ ja todistetaan, että se pätee, kun $n = m+1$. Käytetään lisäksi apuna äsken osoitettua tulosta:

$
{b_{m+1}}^2=a_{n+1}-2
$
$
{b_{m+1}}^2= 7a_{m}-a_{m-1}-2
$
$
9{b_m}^2-6b_m b_{m-1}+{b_{n-1}}^2=7{b_m}^2-{b_{m-1}}^2+10
$
$
{b_m}^2-3b_m b_{m-1} +{b_m}^2 = 5
$
Todistus ja siten myös tehtävän ratkaisu on valmis.

Motivaatio ratkaisun takana: Tehtävän todistamiseksi on mukavaa, jos $a_n-2$
saadaan esitettyä kivasti määritellyn luvun neliönä. Idean saamiseksi on loogista tarkastella, minkä lukujen neliöitä $ a_n - 2 $:t ovat pienillä n:n arvoilla. $ \sqrt{a_1-2}=1 $, $ \sqrt{a_2-2}=4 $, $\sqrt{a_3-2}=11$, $\sqrt{a_4-2}=29$.
Huomataan, että seuraava neliöjuuri saadaan määriteltyä rekursiivisesti lisäämällä edellisen neliöjuuren kolminkertaisena ja vähentämällä sitä edellisen neliöjuuren.
Tässä on mukavasti logiikkaa. Määritellään siis tällä tavalla lukujono $b_n$.
Nyt voi alkaa räpeltää sopivasti induktion kanssa, kuten tämän todistuksen loppuosassa, ja huomata, että todistuksen alussa olevan tuloksen on pakko päteä.



**Kolmas ratkaisu (Olli Järviniemi)**


Luonnollinen idea on tutkia sitä lukujonoa $b_n$, jolla $a_n - 2 = b_n^2$. Laskemalla ensimmäiset arvot saamme $b_0 = 1$, $b_1 = 1$, $b_2 = 4$, $b_3 = 11$, $b_4 = 29$ ja niin edelleen. Huomataan, että rekursioyhtälö $b_{n+1} = 3b_n - b_{n-1}$ näyttää pätevän, paitsi kun $n = 1$. Tämä saadaan korjattua asettamalla $b_0 = -1$, jolloin edelleen $a_0 - 2 = b_0^2$. Pyritään nyt todistamaan, että rekursioyhtälöllä $b_{n+1} = 3b_n - b_{n-1}$, $b_0 = -1$, $b_1 = 1$ määritelty lukujono toteuttaa ehdon $a_n - 2 = b_n^2$.

Ratkaisu rakentuu niin, että muodostamme yleisen termin lausekkeen jonoille $a_n$ ja $b_n$, ja todistamme tätä kautta $a_n - 2 = b_n^2$. Ratkaistaan yleinen lauseke luvulle $a_n$. On yleisesti tunnettua, miten tämä tehdään, mutta ratkaiseminen esitetään kuitenkin suhteellisen yksityiskohtaisesti

On uskottavaa, että lukujono $a_n$ kasvaa eksponentiaalisesti. Veikataan, että yhtälö $a_n = r^n$ kaikilla $n \in \mathbb{N}$ jollain vakiolla $r$. Tämä veikkaus ei tietenkään toimi, mutta ei välitetä vielä siitä. Tutkitaan, mikä $r$:n arvon tulee olla, jotta rekursioyhtälö $a_{n+1} = 7a_n - a_{n-1}$ pätee. Yhtälön $r^{n+1} = 7r^n - r^{n-1}$ tulee päteä. Poissuljetaan $r = 0$. Yhtälö palautuu muotoon $r^2 - 7r + 1 = 0$. Tämä on toisen asteen yhtälö, jolle saamme ratkaisut $x = \frac{7 + 3\sqrt{5}}{2}$ ja $y = \frac{7 - 3\sqrt{5}}{2}$.

Parannetaan sitten veikkaustamme yleisen lausekkeen termille. Saimme äsken selville, että veikkaus $a_n = x^n$ toteuttaa rekursioyhtälön. On helppoa todeta, että tällöin myös $a_n = ax^n$ toteuttaa myös rekursioyhtälön, kun $a$ on vakio. Vastaavasti $a_n = by^n$ toteuttaa rekursioyhtälön kaikilla vakiolla $b$. Todetaan vielä, että nyt näiden summa toteuttaa rekursioyhtälön, siis lauseke $a_n = ax^n + by^n$ (jos et usko, sijoita tämä lauseke rekursioyhtälöön). Enää siis tulee murehtia alkuarvoista $a_0$ ja $a_1$.

Nyt voimme sijoittaa $3 = a_0 = ax^0 + by^0 = a + b$, ja $3 = a_1 = ax + by$. Muuttujat $a$ ja $b$ ovat tuntemattomia, mutta $x$ ja $y$ ovat tiedossa olevia vakioita. Tämä on siis vain tavallinen lineaarinen yhtälöpari, josta voimme ratkaista luvut $a$ ja $b$. Tämä ei ole järin mielenkiintoista, joten ilmoitan vain vastauksen. $a = \frac{3 - \sqrt{5}}{2}$ ja $b = \frac{3 + \sqrt{5}}{2}$. Näin ollen olemme saaneet yleisen termin lausekkeen jonolle $a_n$. Se on ruma, mutta se toimii.

Aivan vastaavaan tapaan voidaan ratkaista yleinen termi jonon $b_n$ jäsenille. Se on muotoa $b_n = cz^n + dw^n$, missä $z = \frac{3 + \sqrt{5}}{2}$, $w = \frac{3 - \sqrt{5}}{2}$, $c = \frac{\sqrt{5} - 1}{2}$ ja $d = -\frac{\sqrt{5} + 1}{2}$.

Palataan sitten yhtälöön $a_n - 2 = b_n^2$. Ennen kuin lähdemme sijoittamaan saamiamme lausekkeita yhtälöön, voidaan jo todeta, että saamme osoitettua yhtälön paikkaansapitävyyden (olettaen että se tosiaan pitää paikkaansa, eli rekursioyhtälö jonolle $b_n$ toimii). Nimittäin, kun kerromme kaiken auki ja vähennämme luvut samalle puolelle, tulee yhtälöstä muotoa
$c_1 \cdot q_1^n + c_2 \cdot q_2^n + \ldots c_k \cdot q_k^n = 0$ (missä voi hyvin olla $q_i = 1$ vakiotermille). Väitteeni on, että jos tämä yhtälö pätee kaikilla $n$, niin silloin yhtälö pätee triviaalisti, eli vasen puoli sievenee nätisti nollaksi. Tämä pätee, sillä jos olisi jokin $i$, jolla $q_i > q_j$ kaikilla $j \neq i$, missä $q_i$:n kerroin ei ole $0$, tulisi isoilla $n$:n arvoilla termi $c_i \cdot q_i^n$ dominoimaan, jolloin yhtälön vasen puoli ei olisi aina $0$.

Enää tulee sijoittaa annetut arvot ja todeta yhtälön paikkansapitävyys. Saamme
$b_n^2 = (cz^n + dw^n)^2 = c^2(z^2)^n + d^2(w^2)^n + 2cd(zw)^n$, sekä
$a_n - 2 = ax^n + by^n - 2$. On helppoa laskea, että on oikeastaan $cd = -1$, $zw = 1$, $c^2 = a$, $d^2 = b$, $z^2 = x$ ja $w^2 = y$. Näistä syistä todistettava yhtälö pätee (varsin triviaalisti, kuten aiemmin todettiin).

Huomautus: yllä esitetyn esimerkin tapaisesti voidaan ratkaista mikä tahansa rekursioyhtälö $c_n = sc_{n-1} + tc_{n-2}$, kun on annettu kaksi alkuarvoa, paitsi jos yhtälöllä $r^2 - rs - t = 0$ on kaksoisjuuri. Tämäkin tapaus on ratkaistavissa. Ratkaisumetodit yleistyvät myös rekursioyhtälöille, joiden syvyys on suurempi kuin $2$. Tällöin ratkastavan polynomin aste kasvaa ja yhtälöryhmän yhtälöiden määrä kasvaa. Lisää informaatiota lineaarisista rekursioyhtälöistä löytyy netistä.

Motivaatio ratkaisun takana: yleinen lauseke termeille $a_n$ ja $b_n$ on hyvin helppoa (tosin hieman työlästä) ratkaista. Yleisestä lausekkeesta on kuitenkin varsin helppoa todistaa yhtälö $a_n - 2 = b_n^2$.
