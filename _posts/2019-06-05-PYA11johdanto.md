---
layout: post
author: "Olli Järviniemi"
title: "Polynomien yhteiset alkutekijät, osa 1: johdanto"
math: true
excerpt_separator: "<!--jatkuu-->"

---

Tässä postauksessa esitetään ensimmäinen osa sarjasta blogipostauksia, jotka käsittelevät tekemääni tutkielmaa. Ensimmäisen osan tarkoitus on antaa kokonaiskatsaus projektista.


<!--jatkuu-->

**Sisällysluettelo**


1. Osa 1 - johdanto
2. [Osa 2 - esitiedot](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA10esitiedot.html)
3. [Osa 3 - tulokset](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA09tulokset.html)
4. [Osa 4 - motivaatio](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA08motivaatio.html)
5. [Osa 5 - heikko versio](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA07heikko.html)
6. [Osa 6 - yleinen tapaus](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA06yleinen.html)
7. [Osa 7 - lause 2](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA05lause2.html)
8. [Osa 8 - lause 3](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA04lause3.html)
9. [Osa 9 - lause 4](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA03lause4.html)
10. [Osa 10 - sovelluksia](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA02sovelluksia.html)
11. [Osa 11 - lisäaiheita](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA01lisaaiheita.html)

**Mistä on kyse?**

Olen opiskellut [Päivölän matematiikkalinjalla](https://www.matematiikkalinja.fi/), jossa toisen vuoden opiskelijat tekevät tutkielman. [Tutkielmassa](https://www.matematiikkalinja.fi/tutkielma/) tavoitteena on opetella jatko-opiskelussa hyödyllisiä taitoja, kuten kirjoittamista ja tiedonhakua.


**Lyhyt kuvaus työn sisällöstä**

Olen jo jonkin aikaa ollut kiinnostunut polynomien alkutekijöistä. Polynomin $P \in \mathbb{Z}[x]$ alkutekijöiksi kutsutaan niitä alkulukuja $p$, joilla yhtälöllä $P(x) \equiv 0 \pmod{p}$ on ratkaisu. [Schurin lauseen](https://blog.matematiikkakilpailut.fi/2018/05/27/Schur.html) nojalla näitä on äärettömän monta (kun $P$ ei ole vakio), mutta tämä antaa varaa laajentaa tulosta:

1. Tutkitaan vain niitä $p$, joilla yhtälöllä $P(x) \equiv 0 \pmod{p^2}$ on ratkaisu. Onko näitä edelleen äärettömän monta?

2. Onko kahden (tai useamman) polynomin yhteisiä alkutekijöitä äärettömän monta?

3. Kuinka suuri osa alkuluvuista on $P$:n alkutekijöitä? Esimerkiksi luvun $2$ potenssit $2^n$ ovat hyvin harvassa kokonaislukujen joukossa, mutta parillisia lukuja on melko tiheästi, joten luonnollinen laajennus alkutekijöiden äärettömyydestä on niiden tiheyden tutkiminen.

Tämä toimi tutkielman lähtökohtana. Tässä ei, ainakaan joillain standardeilla, ole riittävää materiaalia tutkielmaan: jokaiseen kysymyksistä 1-3 on vastattu jo! Tuloksia ei kuitenkaan ole "yhdistetty", eli en löytänyt kirjallisuudesta viitteitä vaikkapa kysymykseen "Kuinka suuri osa alkuluvuista on kahden polynomin A ja B yhteisiä alkutekijöitä?" vastausta.

Tutkielmassani keskityin enimmäkseen polynomien yhteisiin alkutekijöihin. Päätuloksena toimii seuraava väite:

Olkoot $P_1, P_2, \ldots , P_n \in \mathbb{Z}[x]$. On olemassa polynomi $D \in \mathbb{Z}[x]$, jolla on seuraava ominaisuus: polynomien $P_1, P_2, \ldots , P_n$ yhteiset alkutekijät ovat polynomin $D$ alkutekijöitä, ja toisin päin.

Tämä on, ainakin omasta mielestäni, varsin kaunis tulos: päätuloksen avulla ongelmat, jotka käsittelevät polynomien yhteisiä alkutekijöitä, voidaan redusoida yhden polynomin alkutekijöiden tutkimiseen.

Päätulos ja sen todistus antavat seurauksena monia muita tuloksia, joihin perehdytään myöhemmin.


**Aiheen valikoituminen**

Aiheen valitseminen alkoi ensimmäisen opiskeluvuoteni keväällä 2018 ollessani [BOI-kilpailussa](https://boi2018.progolymp.se/) Tukholmassa. Jostain mieleeni heräsi kysymys, joka on sama kuin Schurin lauseen väite (en kuitenkaan vielä tuohon aikaan tiennyt, että tuloksella on oma nimensä). Keksin todistuksen väitteelle varsin nopeasti (todistukseni oli sama kuin postauksessa [Schurin lause](https://blog.matematiikkakilpailut.fi/2018/05/27/Schur.html) esitetty jälkimmäinen todistus).

Palattuani Suomeen aloin miettiä samoja kysymyksiä kuin yllä luetellut. Sain selvitettyä, että jokaiseen kysymykseen on vastaus, mutta todistukset olivat jokaisessa liian vaikeita. Todellisuudessa kysymyksiin 1 ja 2 vastaaminen ja vastauksen osoittaminen oikeaksi on kohtuullisen helppoa. Kysymys 3 on vaikea, tästä lisää myöhemmin. Jätin aiheen tutkimisen kevään osalta tähän.

Kesän loppupuolella ajattelin uudestaan tutkielma-aiheita, ja ajattelin, että jostain pitää kuitenkin tutkielma tehdä. Mietin uudelleen polynomien alkutekijöiden tutkimista, ja totesin sen olevan paras idea mitä minulla on.

Mistä itse tutkiminen sitten alkoi? Kysymyksen 2 käsittelevä todistus muodostaa kahdelle polynomille $A, B \in \mathbb{Z}[x]$ sellaisen polynomin $D \in \mathbb{Z}[x]$, jolla $D$:n alkutekijät ovat $A$:n ja $B$:n alkutekijöitä (poislukien äärellisen monta alkulukua). Tällä polynomilla $D$ tuntui olevan se ominaisuus, että kaikki $A$:n ja $B$:n alkutekijät ovat myös $D$:n alkutekijöitä, jälleen poislukien äärellisen monta alkulukua. Sain tämän selville kirjoittamalla ohjelman, joka määrittää annetuille $A, B$ kyseisen $D$, ja joka tutkii alkutekijöitä.

**Syy kirjoittamiseen**

Lyhyesti syitä, miksi haluan kirjoittaa työstäni blogiin:

1. Tulokset ovat mielestäni hyvin mielenkiintoisia. Alkutekijän määritelmä on hyvin luonnollinen, ja niin ovat niistä yllä esittämäni kysymykset.

2. Todistusten taustalla on teoriaa, joka on (mielestäni) myös hyvin mielenkiintoista, vaikka henkilökohtaisesti pidän matematiikassa enemmän ongelmien kuin teorian tutkimisesta.

3. Työhön liittyvä teoria esitetään mielestäni hyvin vaikeasti, vaikka ajatukset ja ideat ovat hyvin luonnollisia.

4. Kyseisen teorian ymmärtäminen on auttanut ymmärtämään paremmin kilpailumatematiikassa esiintyviä lukuteorian rakenteita, ja jotkin tehtävät jopa ratkeavat melko suoraan näillä ideoilla.

5. Pääsen harjoittelemaan kirjoittamista - en ole vielä täydellinen kirjoittaja.

Edellisistä syistä johtuen tavoittelen tekstissäni helppolukuisuutta ja ideoiden selittämistä.

**Aikajana ja työprosessi**

Minua olisi kiinnostanut kuulla ennen työni aloittamista, millainen on muiden ihmisten työprosessi matematiikan parissa. Tässä siis kuvaus omista työtavoistani ja työn aikajanasta.

Aivan projektin alussa käytin aikaa ohjelmoimiseen ja konjekturointiin: koitin hahmottaa, millaisesta ongelmasta on kyse. Ajattelin, että on varmaankin olemassa valmista teoriaa, jolla päätuloksen todistuksen vaikein kohta saataisiin selätettyä, joten luin myös jonkin verran kirjallisuutta, yhtenä lähteenä Evan Chenin kirjoittama [Napkin](http://web.evanchen.cc/napkin.html). Mitä enemmän teoriaa luin, sitä syvemmälle ja kauemmas se johdatti minut ongelman ratkaisusta, joten aloin improvisoimaan. Suoraan sanoen en oikeastaan osannut paljoakaan teoriaa työhön liittyen, vaan improvisoin todistukset. Päätuloksen todistamiseen kesti suunnilleen kuukauden verran - minulla oli varsin pitkään karkea idea todistuksesta, mutta en vain saanut ajatuksia formaalisti paperille. Työtä hidasti myös se, että ongelma oli hieman vaikeampi kuin luulin: yksinkertainen ideani ei suoraan toiminut, vaan se vaati ylimääräisen kikan, jota en aiemmin keksinyt.

Päätuloksen todistamisen jälkeen oli pitkään melko hiljainen aikajakso: ajattelin, että kaikki on nyt tehty, työ on hiomisia vaille valmis. Suurimmilta osin näin olikin, mutta todistukset vaativat vielä viilailua. Lisäksi tässä vaiheessa en ollut ajattelut kovin pitkälle muita tuloksia, joita päätuloksesta saa irti, ja näitä voi pitää yhtä tärkeänä osana työtä kuin itse päätulosta. Muita tuloksia varten kirjoitin myös paljon eri ohjelmia ja tutkin esimerkkitapauksia.

Kirjoitin tutkielmaani Latexilla puhtaaksi sitä mukaa tietokoneelle kun sain väitteitä todistettua. Tässä oli hyvät ja huonot puolensa: toisaalta kirjoittaessani pystyin varmistumaan siitä, että todistukset todella toimivat, koska jouduin kirjoittamaan ne tarpeeksi yksityiskohtaisesti, että ulkopuolinen pystyy lukemaan ne. Toisaalta kirjoittamiseen kului hyvin suuri määrä aikaa, ja jouduin kirjoittamaan monia kohtia useita kertoja uudelleen. En ole varma, tekisinkö jotain toisin. Tulevaisuutta ajatellen olen päättänyt miettiä tarkemmin tiedostojen ja eri versioiden organisointia.

Projektiin upposi paljon aikaa. Tuntimääriä on vaikea sanoa, koska mietin ongelmia aina sivumennen kävellessäni paikasta toiseen, syödessä, jne., mutta kokoluokka on satoja tunteja. Käytin joitain viikonloppuja kotona pelkästään tutkielman tekemiseen, jolloin parin vuorokauden aikana työhön saattoi upota 20-30 tuntia. Eniten aikaa vievät askareet olivat juurikin kirjoittaminen, mutta aikaa vei myös ihan vain konseptien tarkastelu monesta eri näkökulmasta ja ohjelmien ajaminen esimerkkitapauksilla. Olin hyvin varovainen, koska en suoraan sanoen luottanut itseeni.

Työn saaminen valmiiksi tuntuu hyvin palkitsevalta, ja tunnetta vahvistaa se, että itse ajattelen tuloksien olevan kauniita. Lisäksi olen keksinyt paljon jatkotutkimusaiheita ja oppinut muiden kehittämää teoriaa.


**Kuinka lukea postaussarjaa?**

Suosittelen lukemaan postauksia pienissä paloissa - materiaalia on sen verran paljon, ettei kannata koittaa lukea kaikkea yhdeltä istumalta. Tarvittaessa voi etsiä netistä vastauksia joihinkin kysymyksiin.

Materiaalin paljous varmistaa myös sen, että kirjoitusvirheitä, huonoja lauserakenteita, ja niin edelleen, löytyy varmasti tekstin seasta. Myös virheet ovat mahdollisia. Ei kannata juuttua liikaa yksityiskohtiin. Korjauksia ja kysymyksiä voi lähettää vaikkapa sähköpostiini olli.jarviniemi@gmail.com.

**Huomautus**

Suurin osa materiaalista on kirjoitettu suunnilleen vuoden 2019 tammikuussa. Tilanne tuolloin oli se, että tutkielman palauttamisen deadlineen oli vielä noin kuukausi (deadlinehan on 1.2.).

Tämä huomautus on kirjoitettu vuoden 2019 kesäkuun alussa. Olen saanut varmemman otteen työhön liittyvästä teoriasta ja työn kytköksistä muiden ihmisten tuloksiin, joten olen päättänyt tehdä pieniä muokkauksia kirjoituksiini.

Olen myös keksinyt yksinkertaisempia todistuksia joillekin tuloksille, ja saanut työn yleisen rakenteen yksinkertaisemmaksi.

Lisäksi lyhyt päivitys kilpailujen näkökulmasta: työni pääsi Tutki-Kokeile-Kehitä -kilpailun finaaliin, ja voitin kilpailun! (Voittajatöitä valitaan perinteisesti kaksi, ja olin toinen niistä.) Siispä minä edustan Suomea European Union Competition for Young Scientists -kilpailussa syyskuussa 2019. Kilpailuun työtä tuli tiivistää vielä entisestään - maksimipituus oli 10 sivua. Palautettuani kilpailutyöni EUCYSiin aloin muokkaamaan näitä blogipostauksia.


[Seuraava postaus.](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA10esitiedot.html)
