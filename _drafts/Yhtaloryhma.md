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

