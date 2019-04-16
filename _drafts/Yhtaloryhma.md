---
layout: post
author: Olli Järviniemi
title: "Polynomiyhtälöryhmän ratkaiseminen"
math: true
excerpt_separator: "<!--jatkuu-->"

---


Tässä postauksessa käsitellään yleisen polynomiyhtälöryhmän ratkaisemista.


<!--jatkuu-->

Koulussa yhtälönratkaisu aloitetaan ensimmäisen asteen yhtälöstä

$$ax + b = 0$$

Tämän jälkeen yhtälönratkaisussa jakaudutaan kahteen suuntaan:

1. Toisen ja korkeamman asteen polynomiyhtälöt. Esimerkkinä lukiossa esiteltävä toisen asteen yhtälö $ax^2 + bx + c = 0$ ja sen ratkaiseminen.

2. Lineaarinen yhtälöpari ja -ryhmä. Esimerkkinä yläasteella käytävät yhtälöparit muotoa $x + y = 4$, $x - y = 1$.

Koulussa ei järjestelmällisesti käydä läpi yleisen polynomiyhtälöryhmän ratkaisemista. Yksi syy tälle on se, että kyseinen ongelma on erittäin vaikea. Ensinnäkin, on tunnettua ettei viidennen tai korkeamman asteen polynomiyhtälöille $P(x) = 0$ ole olemassa yleistä ratkaisumenetelmää. Tämä antaa joitain rajoitteita sille, mitä yhtälöryhmän "ratkaisemisella" tarkoitetaan.

Netistä löytämäni materiaali polynomiyhtälöistä oli suurimmaksi osaksi liian vaikeaa olettaen liikaa esitietoja. Lopulta löysin [tästä materiaalista](https://www.geometrictools.com/Documentation/PolynomialSystems.pdf) suoraviivaisen ratkaisumenetelmän.

Ideana on siis esittää ratkaisumentelmä, jolla polynomiyhtälöryhmän ratkaiseminen voidaan palauttaa yhden muuttujan polynomien nollakohtien etsimiseksi. Menetelmässä on kuitenkin joitain ongelmia, joihin keskitytään myöhemmin. **En suosittele menetelmän soveltamista kilpailuissa esiintyviin yhtälöryhmiin - niissä on yleensä jotain symmetrioita ja muita erikoisominaisuuksia, mihin ratkaisu perustuu.** Lisäksi kisatehtävissä etsitään usein reaaliratkaisuja, mikä antaa mahdollisuuden epäyhtälöiden soveltamiseen - vastaava ei ole mahdollista kompleksiluvuissa. Toinen ominaisuus reaaliluvuilla on, että mikäli lukujen neliöiden summa on $0$, niin luvut itsessään ovat nollia.

Ennen yleistä polynomiyhtälöryhmää käyn ensiksi läpi lineaarisen yhtälöryhmän. Tämä siksi, että lineaarinen yhtälöryhmä on usein esiintyvä ongelma, ja toisekseen sen vuoksi, että ideoita voidaan soveltaa yleisiin polynomiyhtälöryhmiin.


## Lineaarinen yhtälöryhmä

Miltä lineaarinen yhtälöryhmä näyttää? Tältä:

$$
\begin{array}{cc}
a_{1, 1}x_1 + a_{1, 2}x_2 + \ldots + a_{1, n}x_n = b_1\\
a_{2, 1}x_1 + a_{2, 2}x_2 + \ldots + a_{2, n}x_n = b_2\\
\vdots \\
a_{n, 1}x_1 + a_{n, 2}x_2 + \ldots + a_{n, n}x_n = b_n
\end{array}
$$

Usein lineaarinen yhtälöryhmä esitetään matriisina seuraavasti:


$$
\left(\begin{array}{cc}
a_{1, 1} & a_{1, 2} & \ldots & a_{1, n} & b_1\\
a_{2, 1} & a_{2, 2} & \ldots & a_{2, n} & b_2\\
\vdots & \vdots & \ldots & \vdots & \vdots\\
a_{n, 1} & a_{n, 2} & \ldots & a_{n, n} & b_n
\end{array}\right)
$$

Syynä matriisiksi muuttamiseen on yksinkertaisesti selkeys. Lisäksi matriiseille on määritelty laskutoimituksia, joiden avulla ratkaisuja voidaan käsitellä.

Yhtälöryhmän ratkaisemiseksi tälle matriisille tehdään ns. alkeisrivitoimituksia. Nämä vastaavat yksinkertaisesti yhden yhtälön kertomista vakiolla, kahden yhtälön laskemista yhteen ja kahden rivin paikkojen vaihtamista. Oleellista on, että **nämä operaatiot eivät vaikuta yhtälöryhmän ratkaisuihin.** Alkeisrivitoimitusten kautta saadaan ratkaistua yhtälöryhmä. Tutkitaan tätä esimerkin kautta.

### Esimerkki

Ratkaistaan yhtälöryhmä

$$
\begin{array}{cc}
x + y + z = 1 \\
2x - 3y - z = 4 \\
3x + 2z = 1 \\
\end{array}
$$

Tämä vastaa matriisia

$$
\left(\begin{array}{cc}
1 & 1 & 1 & 1 \\
2 & -3 & -1 & 4 \\
3 & 0 & 2 & 1
\end{array}\right)
$$

Oikea pystyrivi vastaa siis vakiokertoimia, ja on siinä mielessä erilainen kuin muut. Muutetaan matriisia alkeisrivitoimituksilla niin, että vasemmassa $3 \times 3$ -osamatriisissa on nollasta eroavia alkioita vain vasemmasta ylänurkasta lähtevällä päädiagonaalilla. Tehdään tämä pystyrivi kerrallaan, ja käsitellään ensimmäisenä vasen pystyrivi. Vähennetään toisesta vaakarivistä ylin vaakarivi kerrottuna kahdella, jolloin saadaan matriisi

$$
\left(\begin{array}{cc}
1 & 1 & 1 & 1 \\
0 & -5 & -3 & 2 \\
3 & 0 & 2 & 1
\end{array}\right)
$$

Vastaavasti vähennetään alimmasta vaakarivistä ylin vaakarivi kerrottuna kolmella:


$$
\left(\begin{array}{cc}
1 & 1 & 1 & 1 \\
0 & -5 & -3 & 2 \\
0 & -3 & -1 & -2
\end{array}\right)
$$

Tutkitaan sitten toista pystyriviä, ja muutetaan siitä ensimmäisen ja kolmannen vaakarivin alkiot nolliksi. Lisätään siis ylimpään vaakariviin viidesosa toisesta vaakarivistä:

$$
\left(\begin{array}{cc}
1 & 0 & \frac{2}{5} & \frac{7}{5} \\
0 & -5 & -3 & 2 \\
0 & -3 & -1 & -2
\end{array}\right)
$$

Vastaavasti nollataan alimman rivin toisen pystyrivin alkio


$$
\left(\begin{array}{cc}
1 & 0 & \frac{2}{5} & \frac{7}{5} \\
0 & -5 & -3 & 2 \\
0 & 0 & \frac{4}{5} & -\frac{16}{5}
\end{array}\right)
$$

Ennen näitä kahta operaatiota olisimme voineet kertoa toisen vaakarivin alkiot luvulla $\frac{-1}{5}$ - joissain tilanteissa tämä voi muuttaa laskuja helpommiksi, tässä tapauksessa kyseessä on enemmänkin makuasia.

Kolmatta pystyriviä nollatessa laskut helpottuu hieman, kun kerrotaan alin vaakarivi viidellä, jolloin siis saadaan matriisi

$$
\left(\begin{array}{cc}
1 & 0 & \frac{2}{5} & \frac{7}{5} \\
0 & -5 & -3 & 2 \\
0 & 0 & 4 & -16 \\
\end{array}\right)
$$

Ja nyt nähdään, että alinta vaakariviä voi vielä supistaa neljällä:

$$
\left(\begin{array}{cc}
1 & 0 & \frac{2}{5} & \frac{7}{5} \\
0 & -5 & -3 & 2 \\
0 & 0 & 1 & -4 \\
\end{array}\right)
$$

Nollataan nyt muut kolmannen pystyrivin alkiot. Ensiksi ylimmän vaakarivin luku nollaksi:

$$
\left(\begin{array}{cc}
1 & 0 & 0 & 3 \\
0 & -5 & -3 & 2 \\
0 & 0 & 1 & -4 \\
\end{array}\right)
$$


ja toinen vaakarivi:

$$
\left(\begin{array}{cc}
1 & 0 & 0 & 3 \\
0 & -5 & 0 & -10 \\
0 & 0 & 1 & -4 \\
\end{array}\right)
$$

Lopullista vastausta varten on hyödyllistä, että päädiagonaalilla on vain ykkösiä, joten kerrotaan keskimmäinen yhtälö luvulla $-\frac{1}{5}$.


$$
\left(\begin{array}{cc}
1 & 0 & 0 & 3 \\
0 & 1 & 0 & 2 \\
0 & 0 & 1 & -4 \\
\end{array}\right)
$$


Tämä matriisi siis vastaa yhtälöryhmää

$$
\begin{array}{cc}
x & & = 3 \\
& y & = 2 \\
& & z = -4 \\
\end{array}
$$

Alkeisrivitoimitukset eivät muuta yhtälöryhmän ratkaisuja, joten tässä on alkuperäisen yhtälöryhmän kaikki ratkaisut.

### Hyöty

Kun luin ensimmäistä kertaa yhtälöryhmän ratkaisemisesta yllä kuvatulla menetelmällä (ns. Gaussin eliminointimenetelmä), pidin sitä turhan vaikeana ja jossain määrin hyödyttömänä. Olin tottunut ratkaisemaan yhtälöryhmiä (koulussa opetetulla tavalla) niin, että ensin yhdestä yhtälöstä ratkaistaan $z$ muuttujien $x$ ja $y$ avulla, mistä saadaan kahden muuttujan yhtälöpari, joka voidaan ratkoa vastaavasti. On (ainkain) pari syytä, miksi yllä esitetty menetelmä on kuitenkin parempi kuin aiemmin käyttämäni metodi.

1. Kun muuttujien määrä on suuri, yhden muuttujan ilmaiseminen muiden avulla pienemmän yhtälöryhmän saamiseksi on melko hidasta - pitkä sijoitus tulee tehdä jokaiseen yhtälöön. Yllä esitetyssä menetelmässä tulee toki myös tehdä paljon laskutoimituksia, mutta laskuvirheen riski on mielestäni pienempi, koska aukikertomista ei tarvitse suorittaa.

2. Yllä esitetty menetelmä on mekaanisesti helpompi suorittaa, ja se on helpompi ohjelmoida kuin sijoittamiseen perustuva menetelmä.

3. Eliminointimenetelmä yleistyy paremmin kuin sijoitusmenetelmä, kuten nähdään seuraavassa osiossa. Minusta tuntuu, että kisatehtävissä esiintyvät algebralliset manipulaatiot ovat lähempänä eliminointimenetelmää - pitää keksiä jotain ovelaa summaamalla yhtälöitä yhteen, eikä vain raa'asti ratkaista yhtä muuttujaa kerrallaan.



## Yleinen polynomiyhtälöryhmä

Tutkitaan vaikkapa yhtälöryhmää

$$
\begin{array}{cc}
x^2 + y^2 - 1 = 0 \\
x^3 + y^3 - 3 = 0
\end{array}
$$

Yksi tapa ratkaista yhtälöryhmä on ratkaista ensimmäisestä yhtälöstä $y$ muuttujan $x$ avulla, ja sijoittaa tämä alempaan yhtälöön, aivan kuten lineaaristen yhtälöryhmien tapauksessa. Tässä on kaksikin ongelmaa:

1. Alempaan yhtälöön ei synny polynomia. Tässä tapauksessa polynomin saa aikaan sopivalla neliöinnillä, mutta yleisesti ongelman korjaaminen ei vaikuta kovin helpolta.

2. Yhden muuttujan määrittäminen muiden avulla ei aina onnistu - miten ratkaiset $y$:n $x$:n avulla yhtälöstä $y^5 + y = x$?

Toinen idea on eräänlainen eliminointimenetelmä. Idea on lyhyesti esitetty [täällä](https://www.geometrictools.com/Documentation/PolynomialSystems.pdf) (luvut 3 ja 4). Tutkitaan tätä yhtälöryhmän

$$
\begin{array}{cc}
x^2 + y^2 - 1 = 0 \\
x^3 + y^3 - 3 = 0
\end{array}
$$

kautta. Olkoon $f(x, y) = x^2 + y^2 - 1$ ja $g(x, y) = x^3 + y^3 - 3$. Eliminoidaan ensiksi muuttuja $y$ pienentämällä sen astetta yhtälöparin polynomeissa. Olkoon siis

$$h(x, y) = g(x, y) - yf(x, y)$$

Nähdään, että $h$:n aste $y$:n suhteen on enintään $2$, eli pienempi kuin $g$:n, juuri kuten haluttiinkin. Lisäksi on oleellista huomata, että **pari $(x, y)$ toteuttaa ehdon $f(x, y) = g(x, y) = 0$ jos ja vain jos se toteuttaa ehdon $h(x, y) = f(x, y) = 0$**

Tutkitaan siis polynomien $f$ ja $g$ sijasta polynomeja $f$ ja $h$ - **näitä vastaavilla yhtälöpareilla on täsmälleen samat ratkaisut** (vertaa tätä lineaarisen yhtälöryhmän ratkaisemiseen). Polynomi $h$ voidaan laskea auki:

$$h(x, y) = -xy^2 + y + x^3 - 3$$

Näin voidaan jatkaa: eliminoidaan nyt vaikkapa termi $y^2$ polynomista $h$. Olkoon

$$i(x, y) = h(x, y) + xf(x, y)$$

**Vastaan tulee ongelma**: edellä esitetty ominaisuus parin $(x, y)$ toimivuudesta ei aivan toimi tässä tapauksessa: voi päteä $i(x, y) = h(x, y) = 0$ vaikkei päde $f(x, y) = 0$, nimittäin jos $x = 0$. Emme siis voi sanoa, että yhtälöparilla $i(x, y) = h(x, y) = 0$ on täsmälleen samat ratkaisut kuin yhtälöparilla $h(x, y) = f(x, y) = 0$. Tässä tapauksessa parista $(f, h)$ voitaisiin siirtyä pariin $(i, f)$, jolloin tätä ongelmaa ei esiinny ja $y$:n astetta saadaan pienennettyä toisesta yhtälöparin polynomista kuten haluttiinkin, mutta yleisesti voi olla, ettei kumpikaan siirtyminen kelpaa.

Miltä yleinen eliminointiaskel näyttää? Olkoon meillä polynomit $a(x, y)$ ja $b(x, y)$, joilla $b$:n aste $y$:n suhteen on vähintään $a$:n aste $y$:n suhteen. Olkoon näiden asteiden erotus $n \ge 0$. Valitaan

$$c(x, y) = P(x)a(x, y) + Q(x)y^nb(x, y)$$

Ideana on siis tutkia yhtälöparin $a(x, y) = b(x, y) = 0$ sijasta yhtälöparia $b(x, y) = c(x, y) = 0$, ja haluaisimme, että näillä on täsmälleen samat ratkaisut.

Tässä polynomit $P(x)$ ja $Q(x)$ valitaan niin, että korkeimman $y$:n potenssin kerroin (joka on polynomi $x$:stä!) saadaan nollaksi. Esimerkkeinä toimii aiemmin esitetyt $h$:n ja $i$:n valinnat.

Ongelmia esiintyy enintään niissä tapauksissa, joissa $P(x) = 0$, $Q(x) = 0$ tai $y = 0$. Mutta näitä tapauksia on vain äärellisen monta! Voidaan siis vain tutkia tapaus, jossa $y = 0$ - **tällöin ratkaistavana on yhtälöryhmä, jossa on yksi muuttuja vähemmän kuin aiemmin.** Vastaavasti voidaan käydä läpi kaikki ne $x$:n arvot, joilla $P(x) = 0$ tai $Q(x) = 0$.

Muuten menetelmä toimii - $y$:n astetta saadaan jatkuvasti pienennettyä. Lopussa tilanne lienee se, että polynomin $a$ aste $y$:n suhteen on $0$ ja $b$:n aste $y$:n suhteen on $1$. Tällöin $b$:stä redusoidaan $y$-termi pois, jolloin jäljelle jää yhtälöpari muuttujalle $x$ (vaikka yksikin yhtälö riittäisi).

Mutta mitä sitten tapahtuu? Tarkoittaako tämä sitä, että alkuperäisellä yhtälöparilla $f(x, y) = g(x, y) = 0$ on ratkaisu jos ja vain jos $A(x) = B(x) = 0$ jollain yhden muuttujan polynomeilla $A, B$? Mihin $y$ "katoaa" - voidaanko se siis valita vapaasti?

On oikeasti tärkeää tutkia edellä kuvaillut tapaukset $P(x) = 0, Q(x) = 0, y = 0$ - sieltä ne ratkaisut todellisuudessa löytyvät.

(Käytännössä $y$:n asteen pienentäminen voidaan lopettaa siinä kohtaa, kun ollaan saatu eliminoitua $y$ yhdestä yhtälöstä.)

Tässä eliminointimenetelmässä on pari ongelmaa:

1. Ristiriitaisuuksien huomaaminen: miten nähdään, ettei yhtälöparilla $x + y = 1$, $x^2 + 2xy + y^2 = 0$ ole ratkaisuja?

2. Miten käsitellään tapaus, jossa muuttujia on enemmän kuin yhtälöitä? Entä jos muuttujia on vähemmän?

Lisäksi laskut muuttuvat nopeasti melko ikäviksi (esimerkiksi ratkaisussa esiintyvät yhden muuttujan polynomit saattavat olla _hyvin_ korkea-asteisia, minkä vuoksi käytännössä varmaankin käytetään muita menetelmiä), mutta toisaalta polynomiyhtälöryhmien ratkaisujoukot ovat itsessään melko ikäviä.

Ongelmia on kohtalaisen helppoa käsitellä yksittäisissä, konkreettisissa tapauksissa, mutten halua olla se, joka formalisoi algoritmin, määrittää ongelmatapaukset ja todistaa menetelmän toimivuuden.

Huomaa, että ideat yleistyvät suoraan useammalle kuin kahdelle muuttujalle ja useammille yhtälöille.


**Harjoitustehtäviä**

Ratkaise seuraava yhtälöpari postauksen menetelmällä. Etsi kaikki kompleksiratkaisut.

$$
\begin{array}{cc}
x^2 + y^2 - 2 = 0 \\
xy - 1 = 0
\end{array}
$$

**[EGMO 2019](https://artofproblemsolving.com/community/q1h1818714p12141493), tehtävä 1**

Määritä kaikki reaalilukukolmikot $(a, b, c)$, jotka toteuttavat ehdot $ab + bc + ca = 1$ ja

$$a^2b + c = b^2c + a = c^2a + b$$
