---
layout: post
author: Olli Järviniemi
title: "Lineaariset rekursiot"
math: true
excerpt_separator: "<!--jatkuu-->"

---

Tässä postauksessa käsitellään lineaarisia rekursioita.

<!--jatkuu-->

Määritellään ensin lineaariset rekursiot.

**Määritelmä**

Olkoot $a_1, a_2, \ldots $ joitain reaalilukuja. Sanotaan, että lukujono $a_1, a_2, \ldots $ on lineaarisesti rekursiivinen, jos on olemassa positiivinen kokonaisluku $d$ ja luvut $c_0, c_1, \ldots , c_{d-1}$, joilla

$$a_{i+d} = c_{d-1}a_{i+d-1} + c_{d-2}a_{i+d-2} + \ldots + c_0a_i$$

kaikilla $i > 0$.

Esimerkkeinä toimivat ns. Fibonaccin luvut, joilla $F_{n+2} = F_{n+1} + F_n$, ja kakkosen potenssit generoiva lukujono $a_0 = 1$, $a_{n+1} = 2a_n$.

Tapauksessa $a_0 = 1$, $a_{n+1} = 2a_n$ on selvää, mikä on jonon yleisen termin lauseke: se on $2^n$. Voidaanko yleisesti antaa eksplisiittinen lauseke jonon yleiselle termille? Osoittautuu, että voidaan, ja tähän keskitytään seuraavaksi.

Kutsutaan määritelmän mukaista $d$ lineaarisesti rekursiivisen lukujonon $a$ syvyydeksi (oletetaan $c_0 \neq 0$). On helppoa nähdä, että arvot $a_1, a_2, \ldots , a_d$ yksikäsitteisesti määrittävät loput lukujonon termit. Siis tiettyjä kertoimia $c_0, \ldots , c_{d-1}$ kohden voidaan muodostaa erilaisia lukujonoja vaihtamalla näiden alkuarvojen $a_1, \ldots , a_d$ arvoja. "Vapausasteita" on $d$ kappaletta.

Sitten seuraava huomio:

**Ratkaisujen summa**

Olkoon $f$ funktio, jolla $a_n = f(n)$ kaikilla $n \ge 1$ sopivilla alkuarvojen valinnoilla. Olkoon $g(n)$ vastaavanlainen funktio. Nyt funktiolla $h(n) = f(n) + g(n)$ on vastaava ominaisuus, eli joillain alkuarvojen valinnoilla pätee $a_n = h(n)$ kaikilla $n \ge 1$.

**Todistus**

Olkoon funktiota $f$ vastaavat alkuarvot $a_i = f_i$ ja funktiolle $g$ arvot $g_i$. Funktiolle $h$ alkuarvot ovat $a_i = f_i + g_i$. Yhtälön $h(n) = a_n$ pätevyys näillä alkuarvoilla on helppo induktiotodistus, joka jätetään lukijalle.


Kutsutaan edellisen tuloksen mukaisia $f, g, h$ lukujonon $a_1, a_2, \ldots $ ratkaisuiksi. Tulos siis osoittaa, että kahden ratkaisun summa on ratkaisu. Vastaavassa hengessä voidaan osoittaa seuraava väite:

**Ratkaisun kertominen**

Olkoon $f$ ratkaisu, ja olkoon $c$ vakio. Funktio $g(n) = cf(n)$ on ratkaisu.

**Todistus**

Suoraviivaista, jätetään lukijalle.

Edelliset huomiot voidaan esittää aavistuksen formaalimmin vektoriavaruuksien avulla. Vektoriavaruuksista voi lukea lisää [tästä blogipostauksesta](https://blog.matematiikkakilpailut.fi/2018/09/02/Algebralliset.html).

**Ratkaisujen avaruus**

Olkoon $F$ kaikkien ratkaisujen joukko. Joukko $F$ on $\mathbb{R}$-vektoriavaruus. Toisin sanoen,

1. Kahden joukon $F$ alkion summa kuuluu joukkoon $F$.
2. Joukon $F$ alkioita voidaan kertoa reaaliluvuilla, ja lopputulos on jälleen joukon $F$ alkio.


**Ulottuvuus**

Vektoriavaruuden $F$ alkiot voidaan kuvata ensimmäisellä $d$ alkuarvolla yksikäsitteisesti, ja tämä on bijektiivinen kuvaus: jokaista $d$ lukua $a_1, a_2, \ldots , a_d$ vastaa tasan yksi $F$:n alkio, ja toisin päin. Vektoriavaruuden ulottuvuus on siis $d$.


Seuraavaksi esitetään esimerkkinä Fibonaccin lukujen yleisen lausekkeen määrittäminen, jonka jälkeen osoitetaan yleisen lineaarisen rekursioyhtälön ratkaisut.

**Esimerkki (Fibonaccin luvut)**

Olkoot Fibonaccin luvut määritelty tavalliseen tapaan asettamalla $F_1 = 1, F_2 = 2$, ja $F_{n+2} = F_{n+1} + F_n$, kun $n \ge 1$. Tällöin

$$F_n = \frac{1}{\sqrt{5}}\Big( (\frac{1 + \sqrt{5}}{2})^n - (\frac{1 - \sqrt{5}}{2})^n \Big)$$

Veikataan ensin, että Fibonaccin luvut olisivat muotoa $r^n$, missä $r$ on jokin reaaliluku. Jotta tämä $r$ toteuttaisi rekursioyhtälön, tulee päteä

$$r^{n+2} = r^{n+1} + r^n$$

Poissuljetaan epämielenkiintoinen tapaus $r = 0$, jolloin yhtälö muuttuu muotoon $r^2 = r + 1$. Tällä yhtälöllä on kaksi ratkaisua $a$ ja $b$. Siis funktiot $f(n) = a^n$ ja $g(n) = b^n$ ovat ratkaisuja rekursioyhtälölle $F_{n+2} = F_{n+1} + F_n$. Ainoaksi ongelmaksi tulee alkuarvojen osuminen kohdalleen.

Nyt voidaan käyttää apuna ratkaisujen muodostamaa vektoriavaruutta: ratkaisut $f$ ja $g$ voidaan kertoa mielivaltaisilla reaaliluvuilla $x$ ja $y$, ja lopputulokset $xf$ ja $yg$ ovat edelleen ratkaisuja rekursioyhtälölle. Kahden ratkaisun summa on ratkaisu, joten funktio $h(n) = xf(n) + yg(n)$ on ratkaisu kaikilla vakioiden $x, y$ valinnoilla. Valitaan $x$ ja $y$ niin, että alkuarvot $h(1)$ ja $h(2)$ osuvat kohdilleen. Haluamme siis $1 = h(1) = xf(1) + yg(1) = ax + yb$, ja $2 = h(2) = xf(2) + yg(2) = xa^2 + yb^2$. Luvut $a$ ja $b$ ovat tunnettuja, joten tämä on vain lineaarinen yhtälöpari muuttujien $x$ ja $y$ suhteen. Tästä voidaan ratkaista $x$ ja $y$, jolloin saadaan haluttu, alkuarvoja vastaava ratkaisu, joka on esitetty yllä.

Huomaa, että yhtälöparin ratkaisemista voi yksinkertaistaa hieman asettamalla $h(0) = F_0 = 0$, ja tutkimallakin yhtälöparia $0 = h(0) = x + y$, $1 = h(1) = ax + by$.


Edellisen ratkaisun innoittamana määritellään ns. karakteristinen polynomi.

**Määritelmä (karakteristinen polynomi)**

Olkoon $a_1, a_2,  \ldots $ lineaarisesti rekursiivinen lukujono, ja olkoot $d, c_0, c_1, \ldots , c_{d-1}$ kuten ensimmäisessä määritelmässä. Lukujonon $a_1, \ldots $ karakteristinen polynomi $P$ määritellään asettamalla

$P(x) = x^d - c_{d-1}x^{d-1} - \ldots - c_1x - c_0$


Mitä hyötyä määritelmästä on? Fibonaccin lukujonon tapauksessa lukujonon ratkaisujen määrittäminen palautui karakteristisen polynomin $r^2 - r - 1$ nollakohtiin $a, b$. Yleisessä tapauksessa tilanne etenee pääpiirteittäin vastaavasti, mutta moninkertaiset nollakohdat muuttavat tilannetta hieman. Esitetään tästä esimerkki.

**Esimerkki (moninkertainen nollakohta)**

Olkoon $a_{n+2} = 4a_{n+1} - 4a_n$ kaikilla $n \ge 1$. Määritä lukujonon $a_1, a_2, \ldots $ ratkaisujen joukko.

**Ratkaisu**

Rekursioyhtälön syvyys on $2$, joten odotamme, että lopullisessa ratkaisussa on kaksi vapaata muuttujaa. Fibonaccin lukujono -esimerkki antaisi olettaa, että yleinen ratkaisu on muotoa $xr_1^n + yr_2^n$, missä $r_1, r_2$ ovat karakteristisen polynomin juuria ja $x, y$ ovat vapaita parametreja, jotka voidaan valita vastaamaan alkuarvoja.

Ongelmana on kuitenkin se, että lukujonon $a_1, a_2, \ldots , $ karakteristisella polynomilla $x^2 - 4x + 4$ on kaksinkertainen nollakohta $x = 2$. Miten edetä?

Osoittautuu, että myös $n2^n$ on ratkaisu. Matematiikkansa puolesta puutteellinen mutta ehkäpä intuitiota herättävä perustelu tälle on seuraava: koska $r = 2$ on karakteristisen polynomin nollakohta, on se myös sen derivaatan $2x - 4$ nollakohta. Siispä ratkaisun $r^n$ derivaatta $nr^{n-1}$ on ratkaisu. Ratkaisu voidaan kertoa luvulla $r$, joten $nr^n$ on ratkaisu.

Tässä tapauksessa voidaan helpolla sijoituksella todeta, että $n2^n$ on ratkaisu rekursioyhtälölle. Siis yleinen ratkaisu annetulle lukujonolle on $a2^n + bn2^n = (a + bn)2^n$, missä $a$ ja $b$ ovat vakioita.

Entä kolminkertainen nollakohta, tai yleinen tapaus? Tämän käsittelee seuraava väite:

**Yleinen ratkaisu**

Olkoon $a_1, a_2, \ldots $ lineaarisesti rekursiivinen lukujono, ja olkoon sen karakteristinen polynomi $P$. Olkoon $P$:n erisuuret juuret $r_1, r_2, \ldots , r_k$, ja olkoon $r_i$ $m_i$-kertainen juuri. Yleinen ratkaisu lukujonolle $a_1, a_2, \ldots $ on


$$Q_1(n)r_1^n + Q_2(n)r_2^n + \ldots + Q_k(n)r_k^n$$

missä $\deg(Q_i) < m_i$ kaikilla $i$. Tässä siis polynomit $Q_i$ ovat vapaita parametreja, joiden kertoimia voidaan muuttaa.


**Perustelu**

Todetaan ensin, että ratkaisujen joukon ulottuvuus on $d = \deg(P)$. Koska astetta $d$ olevalla polynomilla on tasan $d$ nollakohtaa, pätee $m_1 + m_2 + \ldots + m_k = d$. Polynomin $Q_i$ kertoimia on $m_i$ kappaletta, joten ratkaisuja voidaan muodostaa vaihtelemalla $d$ parametria. Vielä pitäisi varmistaa, että eri kertoimilla saadaan eri ratkaisut (eli siis emme esitä kahdella eri tavalla samaa ratkaisua). Tämä ei ole järin vaikeaa, ja jätetään harjoitustehtäväksi (kts. postauksen loppu).

On siis uskottavaa, että jos kaikki annettua muotoa olevat lausekkeet todella ovat ratkaisuja, niin ne ovat kaikki ratkaisut. Pyritään nyt siis perustelemaan, miksi kaikki yllä olevaa muotoa olevat lausekkeet ovat ratkaisuja. Ensinnäkin riittää osoittaa, että $n^tr_i^n$ on ratkaisu kaikilla $0 \le t < m_i$, koska ratkaisuja voi kertoa ja summata yhteen. Tämä on selvää tapauksessa $t = 0$, kuten käy ilmi Fibonacci-esimerkin kautta. Tapausta $t = 1$ on pyritty aukaisemaan edellisessä esimerkissä. Yleinen tapaus perustuus moninkertaisten nollakohtien tutkimiseen, mutta vaatii melko paljon esitietoja matriiseista, minkä vuoksi todistusta ei esitetä tässä. Todistus kuitenkin toimii ilman ongelmia, kun karakterisella polynomilla ei ole moninkertaisia nollakohtia.

Seuraavaksi käsitellään esimerkkejä, edeten yksinkertaisista vaikeampiin.


**Esimerkki (perustapaus)**

Olkoon $a_0 = 0$, $a_1 = 5$, ja $a_{n+2} = 7a_{n+1} - 6a_n$. Määritä yleinen lauseke termille $a_n$.

**Ratkaisu**

Ratkaisut muotoa $r^n$ saadaan karakteristisen polynomin $x^2 - 7x + 6$ nollakohdista: ratkaisut ovat $x = 1$ ja $x = 6$. Siis vakiofunktio $1^n$ toteuttaa rekursioyhtälön, kuten myös eksponenttifunktio $6^n$. Yleinen ratkaisu lukujonolle onkin

$$a_n = x6^n + y1^n = x6^n + y$$

missä $x, y$ ovat joitain vakioita. Tässä tapauksessa halutaan $a_0 = 0$ ja $a_1 = 5$, joten

$$0 = a_0 = x6^0 + y = x + y$$

ja

$$5 = a_1 = x6^1 + y = 6x + y$$

Tällä yhtälöparilla on yksikäsitteinen ratkaisu $x = 1$, $y = -1$. Siis lauseke termille $a_n$ on

$$a_n = 6^n - 1$$

Ratkaisun toimivuuden voi tarkistaa vielä helpolla induktiolla.

**Esimerkki (kattofunktio)**

Olkoon $n \ge 0$ kokonaisluku, Osoita, että

$$2^n \mid \lceil (3 + \sqrt{5})^n \rceil$$

Tässä $\lceil x \rceil$ kuvaa pienintä kokonaislukua, joka on $\ge x$.

**Ratkaisu**

Tätä tehtävää on vaikea lähestyä, ellei ole nähnyt vastaavaa aiemmin (tehtävätyyppi on tosin kohtuullisen tunnettu). On kuitenkin kaksi ideaa, jotka voivat tulla mieleen:

1. Kerrotaan luku $(3 + \sqrt{5})^n$ auki binomilauseen nojalla:

$$(3 + \sqrt{5})^n = 3^n + {n \choose 1}3^{n-1}\sqrt{5} + {n \choose 2}3^{n-2}5 + \ldots + \sqrt{5}^n$$

 Joka toinen termi on muotoa $k\sqrt{5}$ ja joka toinen muotoa $k'$, missä $k, k'$ ovat kokonaislukuja. Muotoa $k\sqrt{5}$ olevat termit voisi koittaa saada kumottua tutkimalla summaa $(3 + \sqrt{5})^n + (3 - \sqrt{5})^n$. Tämä sattuu toimimaan, mutta jäljelle jäänyt kokonaisluku ei ole varsin kaunis. Huomataan kuitenkin, että tämä kokonaisluku on se, mitä haluamme: $0 < (3 - \sqrt{5})^n < 1$, eli $\lceil (3 + \sqrt{5})^n \rceil = (3 + \sqrt{5})^n + (3 - \sqrt{5})^n$.

 2. Muistetaan, että vaikkapa Fibonaccin lukujonon yleisen termin lausekkeessa on muotoa $a^n$ olevien termien erotus, ja erotus jaettuna luvulla $\sqrt{5}$ on kokonaisluku $F_n$. Erotuksessa toinen termeistä $a^n$, siis $(\frac{1 - \sqrt{5}}{2})^n$, on hyvin pieni. Tämä kertoo, että luku $\frac{1}{5}(\frac{1 + \sqrt{5}}{2})^n$ on lähellä kokonaislukua suurilla luvun $n$ arvoilla. Voisiko lineaarisia rekursioita hyödyntää tässä tehtävässä?

 Edellisten ideioiden innoittamana yksi idea ratkaisuun voisi olla seuraava: muodostetaan lukujono $a_n$, jonka yleinen jäsen on suunnilleen $(3 + \sqrt{5})$, ja tutkitaan tämän lukujonon jäsenten jaollisuutta luvulla $2^n$.

Rekursioyhtälön karakteristisen polynomin voi keksiä tutkimalla toisen asteen polynomeja $x^2 + ax + b$, ja käyttämällä toisen asteen yhtälön ratkaisukaavaa. Karakteristiseksi polynomiksi saadaan $x^2 - 6x + 4$. Nollakohdat ovat $3 \pm \sqrt{5}$. Idean 1 perusteella olisi luontevaa valita lukujonon alkuarvot niin, että yleinen termi on täsmälleen luvut muotoa $(3 + \sqrt{5})^n + (3 - \sqrt{5})^n$. Alkuarvoiksi tulisi tällöin $a_0 = 2$ ja $a_1 = 6$.

Saadaan siis rekursioyhtälö $a_{n+2} = 6a_{n+1} - 4a_n$ alkuarvoilla $a_0 = 2$ ja $a_1 = 6$. Nyt on helppoa osoittaa induktiolla, että $2^n \mid a_n$. Mutta $a_n = (3 + \sqrt(5))^n + (3 - \sqrt{5})^n =  \lceil (3 + \sqrt{5})^n \rceil$, joten tämä osoittaa väitteen.

Lopuksi esitetään viikon 50 [viikotehtävä](https://keskustelu.matematiikkakilpailut.fi/t/viikkotehtava-osajoukkojen-summien-jaollisuus-viikko-50-2018/224/4) ja sen ratkaisu. Ratkaisussa esitetään myös, miten voidaan ratkaista ongelma, jonka voi ajatella olevan lineaarisen rekursion yleisen jäsenen määrittämisen ja lineaarisen yhtälöparin yhdistelmä.

**Esimerkki (viikkotehtävä)**

Selvitä joukon $\lbrace 1, 2, \ldots , 2000 \rbrace$ niiden osajoukkojen lukumäärä, joiden sisältämien lukujen summa on viidellä jaollinen.

**Ratkaisu motivaatioineen**

Ensimmäinen ajatus on, että mitä tapahtuu, jos $5$ korvataankin jollain muulla luvulla. Tästä saadaan ajatusketju, joka johdattelee triviaaleista seikoista mielenkiintoisiin havaintoihin.


1. Yhdellä jaollisuus. Tällöin osajoukkojen määrä on $2^n$ joukon koon ollessa $n$.

2. Kahdella jaollisuus, joukko $\lbrace 1, 2, \ldots , n \rbrace$. Osoitetaan, että tasan puolet osajoukoista on sellaisia, joissa osajoukon alkioiden summa on parillinen. Valitaan jokin osajoukko $X$. Jos $1 \in X$, muodostetaan joukko $X'$ poistamalla joukosta $X$ alkio $1$. Tällöin joukon $X'$ alkioiden summan parillisuus on eri. Vastaavasti jos $1 \not\in X$, muodostetaan $X'$ lisäämällä joukkoon $X$ alkio $1$. Näin saadaan helposti muodostettua osajoukoista pareja, joiden alkioiden summat ovat eri modulo $2$. Tämä osoittaa väitteen.

3. Kolmella jaollisuus. Nyt ongelmaksi tulee se, ettei yksinkertaista paritusta voida tehdä kuten kohdassa 2. Ideaa voi kuitenkin jalostaa: valitaan jokin joukon $\lbrace 4, 5, \ldots , n\rbrace$ osajoukko $X$. Voimme luoda tästä 8 erilaista joukon $\lbrace 1, 2, \ldots , n \rbrace$ osajoukkoa sen mukaan, mitä alkioita joukosta $\lbrace 1, 2, 3\rbrace$ lisätään joukkoon $X$. Huomataan, että halutunlaisten osajoukkojen määriä voidaan laskea: jos $X$:n alkioiden summa on jaollinen kolmella, voidaan sitä laajentaa joukon $\lbrace 1, 2, 3 \rbrace$ alkioilla neljällä tavalla, jotta summa on jälleen jaollinen kolmella: joko ei lisätä mitään, lisätään alkiot $1$ ja $2$, lisätään alkio $3$, tai lisätään kaikki alkiot. Vastaavasti voidaan käsitellä muita tapauksia. Rekursiivisesti voidaan edetä arvosta $n-3$ arvoon $n$.


Samaa ideaa kuin kohdassa 3. voidaan soveltaa viidellä jaollisuuteen. Keskitytään tähän yksityiskohtaisemmin. Idea on seuraava: oletetaan, että arvolla $n = k$ tiedetään, kuinka monen joukon $\lbrace 1, 2, \ldots , k \rbrace$ osajoukkoa on, joiden alkioiden summa on $0 \pmod{5}$, $1 \pmod{5}$, jne., $4 \pmod{5}$, niin vastaavat tiedot saadaan ratkaistua arvolle $n = k+5$.

Kiinnostavinta on tutkia vain viidellä jaollisten joukkojen kokoa. Merkitään $5n$-kokoisen joukon $\lbrace 1, 2, \ldots , 5n \rbrace $ niiden osajoukkojen määrää, joiden alkioiden summa on $0 \pmod{5}$, luvulla $a_n$. Määritellään vastaavasti lukujonot $b_n, c_n, d_n, e_n$ jakojäännöksille $1, 2, 3, 4$.

Intuitio sanoo, että jäännökset $1$ ja $4$ eivät juurikaan poikkea toisistaan, ne ovat ikään kuin toistensa komplementteja. Tämä on helppo muotoilla formaalisti: olkoon $X$ joukko, jonka alkioiden summa $S(X)$ on $1 \pmod{5}$. Tällöin $X$:n komplementin, eli niiden $y \in \lbrace 1, 2, \ldots 5n \rbrace $ joukko, joilla $y \not\in X$, alkioiden summa on $1 + 2 + \ldots + 5n - S(X) = \frac{5n(5n + 1)}{2} - S(X) \equiv 4 \pmod{5}$. Tämä osoittaa, että $b_n \le e_n$ kaikilla $n$. Vastaavasti saadaan $e_n \le b_n$, joten $e_n = b_n$. Analogisesti $c_n = d_n$ kaikilla $n$.

Ongelma on nyt palautettu kolmeen lukujonoon viiden sijasta, mikä on hyvää edistystä. Seuraavaksi voidaan jo edetä varsinaisten rekursioyhtälöiden muodostamiseen (tämän olisi voinut tehdä ennen ehdon $b_n = e_n$ osoittamista, mutta ongelmaa kannattaa yksinkertaistaa aina jos siihen on mahdollisuus).

Käyttäen kohdan 3. ideaa saadaan siis seuraava rekursioyhtälö:

$$a_{n+1} = a_1a_n + e_1b_n + d_1c_n + c_1d_n + b_1e_n$$

Lyhyt perustelu, joka on kuin edellä: valitaan jokin joukon $\lbrace 6, 7, \ldots , 5(n+1) \rbrace$ osajoukko $X$. Jos $S(X) \equiv 0 \pmod{5}$, voidaan joukkoa $X$ täydentää $a_1$ tavalla. Vastaavasti jos $S(X) \equiv 1 \pmod{5}$, niin $e_1$ tavalla, jne.

On helppoa laskea $a_1 = 8$, $b_2 = c_2 = d_2 = e_2 = 6$. Käyttäen vielä ehtoja $e_n = b_n$ ja $d_n = c_n$ saadaan

$$a_{n+1} = 8a_n + 12b_n + 12c_n$$

Vastaavasti saadaan

$$b_{n+1} = 6a_n + 14b_n + 12c_n$$

ja

$$c_{n+1} = 6a_n + 12b_n + 14c_n$$

Nyt on triviaalia osoittaa induktiolla, että $b_n = c_n$ kaikilla $n$. Ongelma redusoituu enää kahteen lukujonoon, eli siis

$$a_{n+1} = 8a_n + 24b_n$$

ja

$$b_{n+1} = 6a_n + 26b_n$$

Nyt ei ole ilmeistä, miten jatkaa. Kyseessä on lineaaristen rekursioiden ja yhtälöparin yhdistelmä. Kuten lineaarisissa yhtälöpareissa, voisi kuvitella tässäkin olevan mahdollista eliminoida toinen muuttuja (eli lukujono), jolloin ongelma palautuu yhden lukujonon tutkimiseen. Yksi tapa tähän on toistuva sijoittaminen:

$$a_{n+1} = 8a_n + 24b_n = 8a_n + 24(6a_{n-1} + 26b_{n-1}) = 8a_n + 24(6a_{n-1} + 26(6a_{n-2} + 26b_{n-2})) = \ldots$$

Lopputulos on jotain kauheaa, mutta ideana on, että kyseessä on jokin sumam termeistä $a_n$. Lisäksi summan kertoimet vaikuttavat olevat likimain geometriset. Jos kertoimet muodostaisivat geometrisen lukujonon, jonka suhdevakio on $c$, olisi erotuksen $a_{n+1} - ca_n$ tutkiminen hyödyllistä: tällöinhän miltei kaikki supistuisi pois. Nyt tilanne ei tunnu olevan aivan otollisin tälle, mutta yritetään silti:

$$a_{n+1} - ca_n = (8a_n + 24b_n) - ca_n = (8 - c)a_n + 24b_n$$

Vielä ei mitään hyödyllistä, joten jatketaan iterointia:

$$= (8 - c)(8a_{n-1} + 24b_{n-1}) + 24(6a_{n-1} + 26b_{n-1})$$

$c$ halutaan valita niin, että termi $b_{n-1}$ supistuu pois. Tämä onnistuu, kun $24(8 - c) + 24\cdot 26 = 0$, eli kun $c = 34$. Tällöin saadaan

$$a_{n+1} - 34a_n = 64a_{n-1}$$

Tämä on tavallinen lineaarinen rekursioyhtälö, joka osataan ratkaista. Alkuarvo $a_1 = 8$ on tiedossa. Lisäksi voidaan ajatella, että $a_0 = 1$, jolloin saadaan ratkaisu:


$$a_n = \frac{2^{n+2} + 2^{5n}}{5}$$

Arvolla $n = 400$ saadaan tehtävään ratkaisu $\frac{2^{402} + 2^{2000}}{5}$. Vastaus on oikeaa kokoluokkaa, onhan $a_n \approx b_n = c_n = d_n = e_n \approx \frac{2^{2000}}{5}$. $a_n$ sattuu olemaan hieman yleisempi.

**Huomautus**

Yllä esitetty metodi rekursioyhtälöparin ratkaisuun yleistynee useammallekin yhtälölle, mutta prosessi tuskin on miellyttävä.

**Huomautus**

Tehtävään on myös aivan toisenlainen ratkaisu, jonka voi lukea [tehtävän keskusteluketjusta](https://keskustelu.matematiikkakilpailut.fi/t/viikkotehtava-osajoukkojen-summien-jaollisuus-viikko-50-2018/224). Vaihtoehtoisen ratkaisun elegantilla menetelmällä on kohtuullisen vakiintunut nimi, "roots of unity filter". Tästä voi lukea lisää vaikkapa Art of Problem Solving -sivuston käyttäjän stuck [blogipostauksesta](https://artofproblemsolving.com/community/c1340h1003741_roots_of_unity_filter).

Lopuksi mainittakoon mielenkiintoinen fakta: olkoot $a_n$ ja $b_n$ lineaarisesti rekursiivisia lukujonoja. Olkoot $c_n = a_nb_n$ ja $d_n = a_n + b_n$. Tällöin $c_n$ ja $d_n$ ovat lineaarisesti rekursiivisia. Lukujonon $d_n$ karakteristinen polynomi on jonojen $a_n$ ja $b_n$ polynomien tulo, mutta lukujonolle $c_n$ on polynomi mutkikkaampi. Keskutelua tästä on käyty [Mathematics Stack Exchange](https://math.stackexchange.com/questions/1348838/sum-and-product-of-linear-recurrences) -sivustolla.

**Harjoitustehtäviä**

**Laatoitus**

Olkoon $n$ positiivinen kokonaisluku. Kuinka monella tavalla $2 \times n$ -ruudukon voi laatoittaa $1 \times 2$ -laatoilla? Laattoja saa asettaa ruudukkoon pysty- ja vaakasuuntaan.

**Variantteja**

Esitä yleinen ratkaisu seuraaville lukujonoille:

1. $a_{n+2} = a_{n+1} + a_n + 1$

2. $a_{n+2} = a_{n+1} + a_n + n$

3. $a_{n+2} = 3a_{n+1} - 2a_n + 1$

4. $a_{n+2} = 2a_{n+1} - a_n + 1$

5. $a_{n+2} = 2a_{n+1} - a_n + n$

Tutki lukujonon 3 käyttäytymistä joillain alkuarvoilla, ja vertaa tätä lukujonoon $a_{n+2} = 3a_{n+1} - 2a_n$ samoilla alkuarvoilla. Tee sama lukujonoille 4 ja 5. Mitä huomaat, ja mistä ilmiö johtuu?

**Yleisen ratkaisun toimivuuden perustelu**

Olkoot $f_1(n)$ ja $f_2(n)$ funktioita, jotka ovat muotoa

$$Q_1(n)r_1^{n} + Q_2(n)r_2^{n} + \ldots + Q_k(n)r_k^{n}$$

missä $Q_i, r_i$ ovat kuten postauksessa, ja polynomien $Q_i$ kertoimet voivat vaihdella funktioiden $f_1, f_2$ välillä. Osoita, että $f_1(n) = f_2(n)$ kaikilla $n$ jos ja vain jos kaikkien polynomien $Q_i$ kertoimet ovat samat funktiolle $f_1$ ja $f_2$.
