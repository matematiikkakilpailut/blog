---
layout: post
author: "Olli Järviniemi"
title: "Catalan"
math: true
---

Tämän postauksen tavoite on selittää alkeet Catalanin luvuista. Seuraavan kilpailutehtävän (yksi) ratkaisu perustuu Catalanin lukujen ominaisuuksiin. Ratkaisu on esitetty lopussa.

**Tehtävä (pohjoismainen, 2012, tehtävä 4)**

Taululle on kirjoitettu luku 1. Sen jälkeen taululle kirjoitetaan vaiheittain lisää lukuja seuraavasti: kussakin vaiheessa jokainen taululla oleva luku $a$ korvataan luvuilla $a-1$ ja $a+1$; jos taululle ilmestyy luku 0, se pyyhitään pois. Jos jokin luku ilmestyy taululle useammin kuin kerran, kaikki esiintymät jätetään taululle. Siten vaiheessa 0 taululla on luku 1, vaiheessa 1 luku 2, vaiheessa 2 luvut 1 ja 3, vaiheessa 3 luvut 2, 2, ja 4 jne. Montako lukua taululla on vaiheessa n?

**Catalanin lukujen määritelmä**

$n$:nnes Catalanin luku määritellään kaavalla

$$
C_n = {2n \choose n} \frac{1}{n+1} , n = 0, 1, 2, \ldots $$

Tämä on aina positiivinen kokonaisluku, sillä


$$ C_n = {2n \choose n}\frac{1}{n+1} = \frac{(2n)!}{n!(n+1)!} = \frac{(2n)!}{n!n!} \Big( 1 - \frac{n}{n+1}    \Big ) =
$$

$$
\frac{(2n)!}{n!n!} - \frac{(2n)!}{(n-1)!(n+1)!}
= {2n  \choose n} - {2n \choose n+1}
$$

Ensimmäiset Catalanin luvut ovat (alkaen nollasta) $1, 1, 2, 5, 14, 42$. Catalanin luvut antavat vastauksia monenlaisiin kombinatorisiin ongelmiin. Perehdymme näistä vain yhteen, mikä on tärkein esimerkkitehtävän kannalta. Netistä löytyy paljon lisäinformaatiota ihan vain haulla "Catalan's numbers".

**Kombinatorinen merkitys**

Käsitellään seuraavanlaista ongelmaa:

*Ongelma 1.*
Tutkitaan erilaisia tapoja päästä $xy$-koordinaatiston pisteestä $(0, 0)$ pisteeseen $(2n, 0)$ seuraavin ehdoin:
  1. Jokaisella askeleella $x$-koordinaatti kasvaa yhdellä, ja $y$-koordinaatti joko kasvaa tai pienenee yhdellä
  2. $y$-koordinaatti ei koskaan ole negatiivinen

Kuinka monta erilaista ehdot täyttävää polkua on olemassa kullekin $n$:n arvolle?

Edellä olevan ongelman voi myös muotoilla seuraavasti

*Ongelma 2.*
Aloitetaan luvusta $0$. Jokaisella operaatiolla voimme joko kasvattaa tai pienentää lukuamme yhdellä. Kuinka monta tapaa on päästä nollaan $2n$ operaation jälkeen, kun lukumme ei saa missään kohtaa olla negatiivinen?


Todistetaan, että vastaus on $C_n$. Käytetään ratkaisussa jälkimmäistä esitystapaa tehtävälle.

**Ratkaisu**
Jos unohdamme ehdon, että lukumme tulee olla aina epänegatiivinen, on tapojen määrä ${2n \choose n}$, sillä voimme valita meidän $2n$ operaatiosta $n$ kohtaa, joissa kasvatamme lukua yhdellä.
Jotta saamme selville kelvollisten tapojen määrän, riittää vähentää kaikista tavoista kelpaamattomien tapojen määrä. Selvitetään nyt niiden reittien määrä, jotka eivät ole kelvollisia.

Voimme kuvata operaatiosarjaamme lukujonolla $a_1, a_2, \ldots a_{2n}$, jossa $a_i = \pm 1$ kaikilla $i$. Luku, jossa olemme $k$ operaation jälkeen on $a_1 + a_2 + \ldots + a_k$. Oletetaan nyt, että operaatiosarja ei ole kelvollinen. Tämä tarkoittaa sitä, että olemme jossain kohtaa luvussa, joka on negatiivinen. Valitaan se kohta, jossa ensimmäisenä päädymme negatiiviseen lukuun. Olkoon tämä $m$ operaation jälkeen. Pätee $a_1 + a_2 + \ldots + a_m = -1$, ja $a_m = -1$. Täten $a_1 + a_2 + \ldots + a_{m-1} = 0$. Sillä luku, johon lopussa päädymme on $0$, tulee olla $a_{m+1} + a_{m+2} + \ldots + a_{2n} = 1$.

Muodostetaan nyt uusi lukujono $b_1, b_2, \ldots b_{2n}$ seuraavasti:

  Jos $i \le m$, $b_i = -a_i$.
  Jos $i > m$, $b_i = a_i$.

Tiedämme siis, että $b_1 + b_2 + \ldots + b_{2n} = (b_1 + \ldots + b_{m-1}) + b_m + (b_{m+1} + \ldots + b_{2n}) = 0 + 1 + 1 = 2$

Lukujono $b_1, b_2, \ldots b_{2n}$ kuvaakin siis operaation, jolla päästään aloitusluvusta $0$ lukuun $2$. Osoitetaan, että *jokaista* operaatiosarjaa, jolla päästään luvusta $0$ lukuun $2$ vastaa lukujono $b_i$, joka on saatu edellä kuvatulla tavalla jostain lukujonosta $a_i$.

**Lemma**

Olkoon $O$ niiden operaatiosarjojen joukko, joilla pääsemme luvusta $0$ lukuun $2$ lisäämällä aina lukuumme joko $1$ tai $-1$, yhteensä $2n$ kertaa. Olkoon $B$ edellä kuvatulla tavalla muodostettujen jonojen $b_i$ joukko. Joukot $O$ ja $B$ ovat samat.

**Lemman todistus**

On selvää, että jokainen $B$:n jono sisältyy joukkoon $O$. Todistetaan vielä, että jokainen joukon $O$ jono kuuluu joukkoon $B$.

Valitaan jokin jono joukosta $O$, olkoon se $o_1, o_2, \ldots o_{2n}$. Pätee $o_1 + o_2 + \ldots + o_{2n} = 2$. Valitaan pienin $k$, jolla $o_1 + o_2 + \ldots + o_k > 0$. Vaihtamalla ensimmäiset $k$ termiä lukujonosta vastaluvukseen saamme lukujonon $p_1, p_2, \ldots p_{2n}$. Tämän lukujonon termien summa on täten $0$, ja pätee
$p_1 + p_2 + \ldots + p_k = -1$

Lukujono $p_1, p_2, \ldots p_{2n}$ kuvaa siis kelvottoman tavan päästä luvusta $0$ lukuun $0$ yhteensä $2n$ operaatiolla. Voimme täten valita pienimmän indeksin $i$, jolla pätee
$p_1 + p_2 + \ldots p_i < 0$, vaihtaa ensimmäisen $i$ termiä vastaluvukseen, ja näin saada lukujonon, joka kuuluu joukkoon $B$. Selvästi pätee $i = k$ (miksi?), eli tämä lukujono on sama kuin alkuperäinen lukujono $o_1, o_2, \ldots o_{2n}$. Siis alkuperäinen mielivaltainen joukon $O$ jono kuuluu joukkoon $B$. Tästä seuraa $O = B$.


Mitä hyödymme tuloksesta? Tapojen määrä päästä luvusta $0$ lukuun $2$ on tietysti ${2n \choose n+1}$. Siispä kelpaavien tapojen määrä päästä luvusta $0$ lukuun $0$ on

$${2n \choose n} - {2n \choose n+1} = C_n$$

**Ratkaisu esimerkkitehtävään**

Esitetään nyt ratkaisu postauksen alussa esitettyyn tehtävään.

Merkitään luvulla $P(n)$ lukujen määrää vaiheessa $n$, jolloin $P(0) = 1$, $P(1) = 1$, $P(2) = 2$, $P(3) = 3$, $P(4) = 6$, jne. Taululla olevat luvut ovat aina samaa parillisuutta, eli aluksi on vain parittomia, sitten parillisia, sitten parittomia, ja näin edespäin.

Taululla olevien lukujen määrä suunnilleen kaksinkertaistuu, paitsi välillä sieltä poistetaan syntyneet nollat. Nollia ei kuitenkaan synny, jos taululla olevat luvut ovat parillisia: seuraavassa vaiheessa kaikki luvut tulevat olemaan parittomia, eli ei nollia. Tästä saammekin jo tuloksen

$$P(2k) = 2P(2k - 1)$$

kaikilla $k > 0$.

Olkoon $C(n)$ ykkösten määrä vaiheessa $n$. Tiedämme, että
$$P(2k+1) = 2P(2k) - C(2k)$$

Määritetään $C(2k)$, kun $k = 0, 1, \ldots$ Listaamalla saadaan tulokset $1, 1, 2, 5, 14, \ldots $. Nämä näyttävät Catalanin luvuilta!. Enää tämä tulee todistaa:


**Lemma**

$C(2k) = C_k$, missä $C_k$ on $k$:nnes Catalanin luku.

**Todistus**

Verrataan tätä ongelmaan $1$. Tutkitaan, miten vaiheen $2k$ ykköset syntyvät. Aloitamme luvusta $1$, ja voimme aina kasvattaa tai vähentää lukuamme yhdellä ($y$-akseli). Emme kuitenkaan saa mennä nollaan, sillä muuten luku pyyhitään pois. Jokaisella operaatiolla me myös menemme yhden operaation eteenpäin ($x$-akseli). Tämä on siis aivan vastaava tilanne kuin ongelmassa $1$. Täten $C(2k) = C_k$.



Sillä
$C_k = {2k \choose k}\frac{1}{k+1}$

voimme muodostaa rekursioyhtälöt $P$:lle:

$$P(2k) = 2P(2k - 1)$$

ja

$$P(2k + 1) = 2P(2k) - {2k \choose k}\frac{1}{k+1}$$

Nämä rekursioyhtälöt eivät vielä ole vastaus tehtävään. Vastaus tehtävään on kuitenkin helppo selvittää niiden avulla: voimme listata muutaman ensimmäisen luvun paperille ja arvata vastauksen. Lukujono näyttää tältä: $1, 1, 2, 3, 6, 10, 20, 35, 60$. Jos lukujonosta ottaa vain joka toisen luvun, se muuttuu muotoon $1, 2, 6, 20, 70$. Nämä ovat luvut ${2n \choose n}$, missä $n = 0, 1, \ldots $. Tämän avulla saamme viimeisteltyä tehtävän: ilmoitetaan vastaus ja todistetaan se induktiolla. Ei ole vaikeaa veikata, että vastaus on:

$$P(2k) = {2k \choose k}$$ ja $$P(2k + 1) = {2k + 1 \choose k}$$.


Tämän todistaminen jätetään lukijalle. Todistus on helppoa algebrallista manipulaatiota ja rekursioyhtälöiden soveltamista.

Tehtävän vastaus voidaan esittää kompaktisti yhdellä lausekkeella:

Vaiheessa $n$ olevien lukujen määrä on

$${n \choose \lfloor \frac{n}{2} \rfloor}$$
