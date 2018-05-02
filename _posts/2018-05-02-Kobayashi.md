---
layout: post
author: "Olli Järviniemi"
title: "Kobayashin lause"
math: true
excerpt_separator: "<!--jatkuu-->"
---
<div class="hidden">
$\newcommand{\syt}{\mathop{\rm syt}}$
</div>

Tässä postauksessa käsitellään Kobayashin lausetta.
<!--jatkuu-->

**Määritelmä**

Olkoon $a_1, a_2, \ldots $ ääretön, ei-rajoitettu lukujono kokonaislukuja (ei välttämättä positiivisia). Sanotaan, että tällä lukujonolla on $P$-ominaisuus, jos on olemassa vain äärellisen monta alkulukua $p$, jolla $p \mid a_i$ jollain $i$.

Määritelmää sovelletaan myöhemmin myös lukujoukoille vastaavasti.

Kobayashin lause on vahva lause. Sitä ei voi soveltaa jokaiseen kisassa vastaan tulevaan tehtävään, mutta jos sitä pystyy käyttämään järkevästi, voi tehtävä ratketa hyvinkin helposti.

Se, mitä useissa kisamatematiikan lähteissä kutsutaan Kobayashin lauseeksi, on seuraavanlainen tulos:

**Kobayashin lause (heikko versio)**

Olkoon $a_n$ lukujono, jolla on $P$-ominaisuus. Tällöin lukujonolla $b_n = a_n + c$, missä $c \neq 0$ on kokonaislukuvakio, ei ole $P$-ominaisuutta.

Kobayashin lauseelle on vielä yleisempikin muoto, johon palataan myöhemmin tässä kirjoituksessa. Kuitenkin jo tällä heikommalla versiolla saadaan todistettua hyvin suoraviivaisesti monia ei-triviaaleja tuloksia, esimerkiksi:

On olemassa äärettömän monta alkulukua $p$, jotka jakavat jonkin Fermat'n luvun $F_n = 2^{2^n} + 1$

Olkoon $k \in Z$, ($k \neq 0$). On olemassa äärettömän monta alkulukua $p$, jolla $k$ on neliönjäännös modulo $p$ (eli $p \mid x^2 - k$ jollain $x \in \mathbb{Z}$). Tämä tulos yleistyy suoraan kuutionjäännöksille, neljänsien potenssien jäännöksille, ja niin edespäin. Todistus jätetään (helpoksi) harjoitustehtäväksi.

Olkoon $P$ kokonaislukukertoiminen polynomi, jolla on rationaalilukunollakohta $r \neq 0$. Olkoon $a_n$ lukujono, jolla on $P$-ominaisuus. Lukujonolla $b_n = P(a_n)$ ei ole $P$-ominaisuutta. Esimerkiksi on olemassa äärettömän monta alkulukua, jotka jakavat lausekkeen $2^{3n} - 2^{2n + 1} + 2^{n+1} - 1$, kun $n$ käy positiiviset kokonaisluvut läpi.

Viimeisen tuloksen todistus ei ole aivan ilmeinen, joten se esitetään tässä. Olkoon $P(x) = (x-r)Q(x)$, missä $Q$ on polynomi. $Q$:n kertoimet ovat rationaalilukuja (miksi?), joten voimme kertoa yhtälön puolittain sopivalla kokonaisluvuilla $k$ ja $m$, $km \neq 0$ niin, että $kr$ on kokonaisluku ja $mQ$ on kokonaislukukertoiminen.
Nyt, määritellään $c_n = kmP(a_n) = (ka_n - kr)mQ(a_n)$. Sillä lukujonolla $ka_n$ on $P$-ominaisuus, ei lukujonolla $ka_n - kr$ ole $P$-ominaisuutta. Täten lukujonolla $c_n$ ei myöskään ole $P$-ominaisuutta. On siis olemassa äärettömän monta alkulukua $p$, joilla pätee $p \mid c_i = km\cdot b_i$ jollain $i$, ja lisäksi $p > km$. Näillä $p$ pätee myös, että $p \mid b_i$. Siispä lukujonolla $b_n$ ei ole $P$-ominaisuutta.

Kobayashin lauseen koko versio on seuraava (käännös tekstistä [On Existence of Infinitely Many Prime Divisors in a Given Set, Hiroshi Kobayashi](https://projecteuclid.org/download/pdf_1/euclid.tjm/1270215162), notaatiota muutettu)

**Kobayashin lause**

Olkoon $M$ ei-rajoitettu joukko kokonaislukuja, jolla on $P$-ominaisuus. Olkoon $a \neq 0$ kokonaisluku, ja $m \ge 3$ kokonaisluku. Olkoon $(b_t)$, $t \in M$ lukujono kokonaislukuja, jonka indeksijoukko on $M$. Asetetaan $N = \lbrace a + b_t^m \cdot t \mid t \in M\rbrace$. Jos $N$ on ääretön joukko, niin sillä ei ole $P$-ominaisuutta.

Huomaa, että lukujonolla $b_t$ ei tarvitse olla $P$-ominaisuutta.

Asettamalla $M = \lbrace a_1, a_2, a_3, \ldots \rbrace$ ja $b_t = 1$ kaikilla $t \in M$ saamme aiemmin esitetyn heikomman version lauseesta.



**Esimerkkitehtävä (Kiinan kansallisen kilpailun finaali, 2011, tehtävä 6)**

Olkoot $n$ ja $m$ positiivisia kokonaislukuja. Osoita, että on olemassa äärettömän monta paria $(a, b)$, $a, b \in N$, niin että

$a + b \mid am^a + bn^b$, ja $\syt(a, b) = 1$

**Ratkaisu**

Tehtävänannnon ehto ei ole kovin sievä, joten luonnollinen idea on sieventää sitä.

$am^a + bn^b \equiv am^a - (a + b - b)n^b \equiv a(m^a - n^b) \pmod{a+b}$

Sillä $\syt(a, b) = 1$, riittää todistaa $a + b \mid m^a - n^b$ äärettömän monella $a, b$.

Usein on helpompaa tutkia asioita modulo alkuluku yleisen tapauksen sijasta. Valitaan $a + b = p$, missä $p$ on alkuluku. Haluamme löytää sellaiset $a$ ja $b$, joilla $p \mid m^a - n^b$. Lisäksi jos $p \nmid n$, riitää löytää $a$ ja $b$ niin, että $p \mid n^a(m^a - n^b) = (nm)^a - n^{a+b} \equiv (nm)^a - n$

Jotta luvuille $a, b$ olisi äärettömän monta vaihtoehtoa, tulisi myös $p$:lle olla. Siis lukujonolla $(nm)^a - n$ tulee olla äärettömän monta alkulukujakajaa, kun $a$ vaihtelee (unohdetaan hetkeksi ehto $a + b = p$). Tämä onnistuu Kobayashin lauseen nojalla (paitsi jos $nm = 1$, mutta tämä tapaus on onneksi helppo).

 Valitaan siis sellainen $p > nm$, jolla on olemassa jokin $c > 0$, jolla $p \mid (nm)^c - n$. Valitaan pienin tällainen $c$. Fermat'n pienen lauseen avulla voimme pienentää $c$:tä aina luvulla $p-1$, mikäli se on liian suuri. Siis pienimmälle ratkaisulle pätee $0 < c \le p-1$. Valitaan nyt $a = c$, $b = p - c$. Tällä valinnalla ehto $\syt(a, b) = 1$ pätee, sillä $\syt(a, b) \mid a + b = p$. Lisäksi jaollisuusehto pätee edellisen päättelyn nojalla.

**Harjoitustehtäviä**

Seuraavien harjoitustehtävien tulisi olla kohtalaisen helppoja. Ainakin jälkimmäiseen tehtävään on hyvä miettiä myös ratkaisu ilman Kobayashin lausetta.


**Iranin IMO-valintakoe, 2009, päivä 1, tehtävä 2**

Olkoon $a > 0$ kokonaisluku. Osoita, että joukon $2^{2^n} + a$, $n = 1, 2, \ldots$ alkutekijöiden joukko on ääretön.


**IMO-lyhytlista 2011, N2**

Olkoon $P(x) = (x + d_1)(x + d_2) \ldots (x + d_9)$, missä $d_1, d_2, \ldots d_9$ ovat $9$ erisuurta kokonaislukua. Osoita, että on olemassa $N$, niin että kaikilla $x \ge N$ luvulla $P(x)$ on alkutekijä, joka on suurempi kuin $20$.
