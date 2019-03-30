---
layout: post
author: Olli Järviniemi
title: "Neliönjäännökset"
math: true
excerpt_separator: "<!--jatkuu-->"

---


Tässä postauksessa käsitellään neliönjäännöksiä. Tarkemmin sanoen käsitellään, milloin luku on neliönjäännös äärettömän monella alkuluvulla, sekä muita samanhenkisiä kysymyksiä.

<!--jatkuu-->

Ensin kerrataan neliönjäännöksiin liittyvä teoria. Väitteitä ei todisteta tässä, ja kiinnostuneen lukijan kehotetaan siirtymään [Esa Vesalaisen lukuteoriamonisteen](https://matematiikkakilpailut.fi/kirjallisuus/laajalukuteoriamoniste.pdf) pariin (luku 5).

**Määritelnä (neliönjäännös)**

Olkoon $p$ alkuluku. Sanotaan, että $a$ on neliönjäännös modulo $p$, jos $p \not\mid a$, ja yhtälöllä $x^2 \equiv a \pmod{p}$ on ratkaisu. Jos $p \not\mid a$, ja tällä yhtälöllä ei ole ratkaisua, kutsutaan $a$:ta neliönepäjäännökseksi. Luvut $a$, joilla $p \mid a$, eivät ole neliönjäännöksiä eivätkä -epäjäännöksiä.

Parittomilla $p$ neliönjäännöksiä ovat täsmälleen puolet luvuista $1, 2, \ldots , p-1$.

**Määritelmä (Legendren symboli)**

Olkoon Legendren symboli määritelty asettamalla $L(a, p) = 1$, jos $a$ on neliönjäännös modulo $p$, $L(a, p) = -1$ jos $a$ on neliönepäjäännös, ja muuten $L(a, p) = 0$.

Tässä postauksessa käytetään ulkonäkösyistä yllä esitettyä tavallisuudesta poikkeavaa merkintään Legendren symbolille.

Tämän postauksen kannalta tärkeimmät tulokset neliönjäännökset ovat seuraavat:

**Multiplikatiivisuus**

$L(ab, p) = L(a, p)L(b, p)$ kaikilla $a, b \in \mathbb{Z}$.

**Neliönjäännösten resiprookkilaki**

Olkoot $p$ ja $q$ parittomia alkulukuja. Oletetaan, että joko $p \equiv 1 \pmod{4}$ tai $q \equiv 1 \pmod{4}$. Tällöin $L(q, p) = L(p, q)$. Jos taas $p \equiv q \equiv 3 \pmod{4}$, pätee $L(q, p) = -L(p, q)$.

Resiprookkilaki ei kerro, milloin luvut $-1$ ja $2$ ovat neliönjäännöksiä. Näitä varten on seuraavat tulokset:

**Tapaus $a = -1$**

$L(-1, p) = 1$ jos ja vain jos $p \equiv 1 \pmod{4}$ (tai $p = 2$).

**Tapaus $a = 2$**

$L(2, p) = 1$ jos ja vain jos $p \equiv \pm 1 \pmod{8}$.


Näillä esitiedoilla pääsemme postauksen keskeisiin teemoihin.

**Ongelma 1**

Olkoon $a \neq 0$ kokonaisluku. Onko olemassa äärettömän monta alkulukua $p$, joilla $L(a, p) = 1$?

**Ongelma 2**

Olkoon $a \neq 0$ kokonaisluku. Onko olemassa äärettömän monta alkulukua $p$, joilla $L(a, p) = -1$?


On uskottavaa, että ongelmassa 1 vastaus on aina myönteinen. Ongelmassa 2 näin ei ole jos $a$ on neliöluku, mutta muissa tapauksissa vastaus lienee myönteinen. Intuitiiviset vastaukset ovat oikeat. Seuraavaksi esitetään todistukset tuloksille. Lukijan on hyvä koittaa ratkaista tehtäviä ennen ratkaisujen lukemista.


**Ratkaisu 1**

Ongelmassa tutkitaan sitä, milloin jokin luku on neliönjäännös mod $p$. Ideana on kääntää ongelma muotoon, jossa tutkitaan, milloin $p$ on neliönjäännös modulo jokin luku tai jotkin luvut. Tämä muoto on helpompi käsitellä, ja antaa ratkaisun ongelmaan.

Tutkitaan vain niitä alkulukuja $p$, joilla $p \equiv 1 \pmod{8}$. Näitä on Dirichlet'n lauseen nojalla äärettömän monta. Syynä tähän valintaan on se, että tällöin $L(-1, p) = L(2, p) = 1$, joten todistus yksinkertaistuu hieman.

**Lemma 1**

Olkoon $k \in \mathbb{Z}$ sellainen, jolla $k \neq 0$. Olkoon $\mid k \mid \ = 2^{a}p_1^{a_1}p_2^{a_2} \ldots p_n^{a_n}q_1^{b_1} \ldots q_m^{b_m}$, missä parittomat alkuluvut $p_i, q_j$ ovat erisuuria, $a_i \equiv 0 \pmod{2}$ ja $b_j \equiv 1 \pmod{2}$. Tällöin kaikilla $p \equiv 1 \pmod{8}$, joilla $p \not\mid k$, pätee

$L(k, p) = L(q_1, p)L(q_2, p) \ldots L(q_m, p)$

**Huomautus**

Jos $\mid k \mid$ on luvun $2$ potenssi, on kyseessä tyhjä tulo, eli $L(k, p) = 1$.

**Todistus**

Ideana on käyttää Legendren symbolin multiplikatiivisuutta, jonka avulla ongelma voidaan hajoittaa pieniin palasiin. Valinnasta $p \equiv 1 \pmod{8}$ ja multiplikatiivisuudesta johtuen

$$L(k, p) = L(\mid k \mid, p) = L(2^a, p)L(p_1^{a_1}, p) \ldots L(q_m^{b_m}, p)$$

Tätä voidaan sieventää seuraavin keinoin:

1. Koska $p \equiv 1 \pmod{8}$, pätee $L(2^a, p) = L(2, p)L(2, p) \ldots L(2, p) = 1^a = 1$.

2. Luvut $p_i^{a_i}$ ovat neliölukuja, koska $a_i \equiv 0 \pmod{2}$. Siis ne ovat neliönjäännöksiä modulo $p$, joten $L(p_i^{a_i}, p) = 1$ kaikilla $i$.

3. $b_i \equiv 1 \pmod{2}$, joten voidaan kirjoittaa $b_i = 2c_i + 1$, $c_i \in \mathbb{Z}$. Tällöin $L(q_i^{b_i}, p) = L(q_i^{2c_i}q_i, p) = L(q_i^{2c_i}, p)L(q_i, p)$. Mutta $q_i^{2c_i}$ on neliöluku, joten tämä sieventyy muotoon $L(q_i, p)$.

Edellisten huomioiden nojalla saadaan $L(k, p) = L(q_1, p) \ldots L(q_m, p)$. Tämä todistaa lemman väitteen.

**Ratkaisun 1 viimeistely**

Lemman avulla voidaan siirtyä ratkaisun alussa kuvailtuun vaiheeseen, jossa käännetään symbolin $L(a, p)$ tutkiminen siihen, milloin $p$ on neliönjäännös. Kirjoitetaan $L(a, p) = L(q_1, p) \ldots L(q_m, p)$, missä $q_i$ ovat parittomia alkulukuja. Koska valinnan mukaan $p \equiv 1 \pmod{8}$, on $p \equiv 1 \pmod{4}$, joten voimme käyttää neliönjäännösten resiprookkilakia ilman etumerkkien vaihtumista:

$$L(a, p) = L(q_1, p) \ldots L(q_m, p) = L(p, q_1) \ldots L(p, q_m)$$

Enää tulee siis varmistaa, että yhtälön oikeanpuoleisin lauseke on $1$. Mutta tämä on helppoa: voidaan esimerkiksi valita $p \equiv 1 \pmod{8q_1q_2 \ldots q_m}$. Tällöin $p \equiv 1 \pmod{8}$ kuten kuuluukin. Lisäksi tärkeimpänä huomiona $p \equiv 1 \pmod{q_i}$ kaikilla $i$, joten $p$ on neliönjäännös modulo $q_i$ kaikilla $i$. Tämä osoittaa, että kaikki tätä muotoa olevat $p$ (poislukien ne, joilla $p \mid a$) ovat sellaisia, joilla $L(a, p) = 1$. Dirichlet'n lauseen nojalla näitä $p$ on äärettömän monta, mikä todistaa väitteen.


Huomaa, että ongelma 1 voidaan ratkaista suoraan [Schurin lauseella](https://blog.matematiikkakilpailut.fi/2018/05/27/Schur.html). Yllä esitetty ratkaisu on kuitenkin tietyssä mielessä parempi, koska se antaa informaatiota siitä, "millaisia" ne $p$ ovat, joilla $L(a, p) = 1$. Tähän keskitytään tarkemmin myöhemmin tässä postauksessa.

Esitetään sitten vastaavassa hengessä ratkaisu ongelmaan 2.

**Ratkaisu 2**

Ratkaisu tähän ongelmaan ei poikkea suuresti edellisen tehtävän ratkaisusta, mutta vaikeutena on se, että edellisessä ongelmassa ainoa erikoinen tapaus oli $a = 0$, ja tässä eri tavalla käyttäytyviä lukuja on äärettömän monta.

Ongelman 1 ratkaisu antaa miltei suoraan ratkaisun siinä tapauksessa, että $\pm a$:lla on sellainen pariton alkulukutekijä $q$, jonka eksponentti $\pm a$:n alkutekijähajotelmassa on pariton. Tutkitaan tämä tapaus ensimmäisenä.

Olkoon siis ratkaisun 1 mukaisesti $p \equiv 1 \pmod{8}$, ja $L(a, p) = L(q_1, p)L(q_2, p) \ldots L(q_m, p)$. Oletuksen nojalla $m \ge 1$, eli kyseessä ei ole tyhjä tulo. Jälleen voidaan käyttää neliönjäännösten resiprookilakia:

$$L(a, p) = L(p, q_1) \ldots L(p, q_m)$$

Koska $q_1$ on pariton alkuluku, on olemassa sellainen $t \in \mathbb{Z}$, jolla $L(t, q_1) = -1$. Valitaan nyt $p$ niin, että seuraavat ehdot toteutuvat:

1. $p \equiv 1 \pmod{8}$
2. $p \equiv t \pmod{q_1}$
3. $p \equiv 1 \pmod{q_i}$ kaikilla $2 \le i \le m$. Jos $m = 1$, ei tätä ehtoa tarvitse huomioida.

Kiinalaisen jäännöslauseen ja Dirchlet'n lauseen nojalla tällaisia $p$ on äärettömän monta. Näillä $p$ pätee $L(p, q_i) = 1$ jos ja vain jos $i \neq 1$. Siis täsmälleen yksi tulon $L(p, q_1)L(p, q_2) \ldots L(p, q_m)$ luvuista on $-1$, joten koko tulo on $-1$. Tämä osoittaa väitteen.


Tutkitaan sitten se tapaus, jossa $\mid a \mid$:lla ei ole parittomia alkulukutekijöitä. Tämä tarkoittaa, että $\mid a \mid = 2^b$ jollain $b \ge 0$. Siis $a = \pm 2^b$. Tapaus $b \ge 2$ voidaan redusoida lemman 1 todistuksen kaltaisilla menetelmillä tapaukseen $0 \le b < 2$. Näiden äärellisen monen tapauksen käsittely jätetään lukijalle.


**Yleistäminen**

Todistetut tulokset ovat varsin kauniita, mutta voiko niitä vielä laajentaa? Luonnollisia kysymyksiä ovat esimerkiksi seuraavat:

1. Päteekö ongelman 1 variantti, jossa vaaditaan $L(a_i, p) = 1$ kaikilla $i$ ja äärettömän monella $p$, missä $a_1, a_2, \ldots a_n$ ovat annettuja nollasta eroavia kokonaislukuja?

2. Entä ongelman 2 vastaava variantti, missä $a_i$ eivät ole neliölukuja?

3. Ratkaisuissa 1 ja 2 luodut $p$ ovat melko harvassa, esimerkiksi ratkaisun 1 $p$ toteuttavat ehdon $p \equiv 1 \pmod{8q_1q_2 \ldots q_m}$. Kuinka "tiheästi" ongelman 1 tai 2 mukaisia $p$ todellisuudessa on?

Ensimmäisen kysymyksen vastaus on melko ilmeinen: käytännössä sama argumentti käsittelee monen muuttujan tapauksen kuin mitä käytettiin ratkaisussa 1.

Kysymyksen 2 vastaus ei ole niin ilmeinen: olkoot $a_1 = 2 \cdot 3$, $a_2 = 3 \cdot 5$ ja $a_3 = 2 \cdot 5$. Jos olisi olemassa $p$, jolla $L(a_i, p) = -1$ kaikilla $i$, niin pätisi $-1 = L(a_1, p)L(a_2, p)L(a_3, p) = L(a_1a_2a_3, p) = L((2\cdot3\cdot5)^2, p) = 1$. Tämä on selvästi mahdotonta. Yleisesti voidaan todistaa vastaavasti, että minkään parittoman määrän lukuja $a_i$ tulo ei saa olla neliöluku. Onko tämä riittävä ehto, eli jos tämä ehto täyttyy, niin onko olemassa äärettömän monta kelpaavaa $p$? Osoittautuu, että on. Heuristinen selitys tälle esitetään kysymyksen 3 käsittelyn jälkeen. Kirjoittajan formaali todistus on liian pitkä tähän postaukseen, mutta se saatetaan nähdä myöhemmässä postauksessa.

**Kysymys 3**

Kysymys 3 ei ole mielenkiintoinen neliölukujen $a$ tapauksessa: tällöin $a$ on neliönjäännös kaikilla $p$. Muussa tapauksessa intuitiivinen veikkaus voisi olla, että "puolet" alkuluvuista on sellaisia, että $a$ on neliönjäännös, ja loput puolet ovat sellaisia, joilla $a$ on neliönepäjäännös, koska jokaista $p$ kohden puolet luvuista ovat neliönjäännöksiä ja puolet eivät.

Ennen tämän väitteen todistamista määritellään tiheys. Olkoon $S$ jokin alkulukujen $\mathbb{P}$ osajoukko. Merkitään joukon $S \subset \mathbb{P}$ lukua $x$ pienempien alkioiden määrä $S(x)$, ja merkitään vastaavasti $\mathbb{P}(x)$. Joukon $S$ tiheys määritellään raja-arvona

$$\delta(S) = \lim_{x \to \infty} \frac{S(x)}{\mathbb{P}(x)}$$

Kaikilla joukoilla $S$ tämä raja-arvo ei ole olemassa, mutta tässä postauksessa tutkittavat tiheydet ovat olemassa. Dirichlet'n lauseesta on usein kilpailumatematiikan yhteydessä mainittua versiota voimakkaampi väite, joka kertoo, että niiden $p$ tiheys, joilla $p \equiv a \pmod{m}$, on $\frac{1}{\phi(m)}$ kaikilla $a, m$, jotka ovat yhteistekijättömiä.

Käyttäen Dirichlet'n lausetta ei ole kovin vaikeaa osoittaa ratkaisun 1 kaltaisesti, että niiden $p$ tiheys, joilla $L(a, p) = 1$, on $\frac{1}{2}$. Tämä voidaan toteuttaa vaikkapa seuraavasti:

Ttkitaan ensin niitä $p$, joilla $p \equiv 1 \pmod{8}$. Näitä $p$ on neljäsosa alkuluvuista, ja näillä $p$ pätee $L(a, p) = L(p, q_1) \ldots L(p, q_m)$.

Olkoon $T = (t_1, t_2, \ldots , t_m)$ jokin $m$ luvun jono, joka koostuu luvusta $-1$ ja $1$. Kiinalaisen jäännöslauseen ja Dirichlet'n lauseen tiheysversion avulla saadaan, että niiden $p$ tiheys, joilla $L(p, q_i) = t_i$ kaikilla $i$ on $2^{-m}$. Niitä $T$, jotka sisältävät parillisen määrän lukua $-1$ on $2^{m-1}$ kappaletta. Tästä saadaan, että yhteensä niitä $p$, joilla $L(a, p) = 1$ on tapauksessa $p \equiv 1 \pmod{8}$ puolet alkuluvuista.

Tutkiessa tapauksia $p \equiv 3, 5, 7 \pmod{8}$ päädytään yhtälöön $L(a, p) = \pm L(p, q_1) \ldots L(p, q_m)$, missä etumerkki riippuu vain siitä, mitä $p$ on modulo $8$. Tällöin saadaan edellisen argumentin kaltaisesti jokaisen tapauksen alkutekijöiden tiheydelle arvo $\frac{1}{2}$. Siispä kokonaisuudessaan niitä $p$, joilla $L(a, p) = 1$, on puolet alkuluvuista.

**Huomautus**

Missä kohtaa käytettiin tietoa siitä, ettei $a$ ole neliöluku?


**Kysymys 2**

Perustellaan ensiksi se, että riittää tutkia tapausta, joissa kertomalla lukuja $a_i$ sopivasti keskenään ei saa neliölukua. Nimittäin, oletetaan että lukujen $a_1, a_2, \ldots , a_t$ tulo on neliöluku $T^2$. Oletuksen nojalla $t$ on parillinen. Siis $a_1a_2 \ldots a_t = T^2$, joten $a_1^2a_2 a_3 \ldots a_t = T^2a_1$. Ottamalla Legendren symbolin puolittain saadaan, että

$$L(a_2, p)L(a_3, p) \ldots L(a_t, p) = L(a_1, p)$$

Siis jos $a_2, a_3, \ldots , a_t$ ovat kaikki neliönepäjäännöksiä, seuraa tästä $L(a_1, p) = -1$, koska $t$:n oletettiin olevan parillinen.

Tämä idea soveltuu neliönepäjäännösten lisäksi tietysti myös neliönjäännösten tutkimiseen. Tehdään tämä oletus, ja esitetään heuristiikka, johon kysymyksen 2 ilmiö perustuu.

**Heuristiikka**

Olkoot $a_1, a_2, \ldots , a_n$ kokonaislukuja. Oletetaan, että ei ole olemassa epätyhjää osajoukkoa näistä luvuista, jonka alkioiden tulo olisi neliöluku. Heuristisesti niiden $p$ tiheys, joilla $L(a_i, p) = 1$ kaikilla $i$, on $2^{-n}$.

**Perustelu**

Väite todistettiin kysymyksen 3 tapauksessa arvolla $n = 1$. Tutkitaan konkreettisuuden vuoksi tapausta $n = 2$, $a_1 = 2$, $a_2 = 3$. Tiedetään, että puolet alkuluvuista ovat sellaisia, joilla $2$ on neliönjäännös, ja vastaavasti luvulle $3$. Ei ole ilmeistä syytä, miksi nämä tapahtumat riippuisivat toisistaan: tieto siitä, että $2$ on neliönjäännös ei vaikuta kertovan mitään siitä, onko $3$ neliönjäännös vai ei. Voidaan siis ajatella, että tapahtumat "$2$ on neliönjäännös" ja "$3$ on neliönjäännös" ovat toisistaan riippumattomia, ja tapahtuvat molemmat $50\%$ ajasta. Siis neljäsosa alkuluvuista on sellaisia, joilla $2$ ja $3$ molemmat ovat neliönjäännöksiä modulo $p$.

Yleinen tapaus voidaan perustella vastaavasti.

Heuristiikkaa voi soveltaa aivan vastaavasti myös neliönepäjäännöksille (ja myös sekoituksille jäännöksiä ja epäjäännöksiä). Tämä perustelee väitteen.

**Huomautus**

Lienee mahdollista osoittaa heuristiikan paikkansapätevyys formaalisti kysymyksen 3 ratkaisun kaltaisin menetelmin. Erikoistapauksia voi ratkoa kohtuullisen yksinkertaisesti (esimerkiksi se tapaus, että $a_i$ ovat erisuuria alkulukuja), mutta yleinen tapaus vaatii uusia ideoita.

**Harjoitustehtäviä**

**Yleinen toisen asteen polynomi**

Olkoon $P(x) = ax^2 + bx + c$ kokonaislukukertoimien toisen asteen polynomi. Osoita, että äärellisen montaa $p$ lukuun ottamatta yhtälöllä $P(x) \equiv 0 \pmod{p}$ on ratkaisu jos ja vain jos $b^2 - 4ac$ on neliönjäännös modulo $p$ (tai $b^2 - 4ac \equiv 0 \pmod{p}$).

**Erikoistapaus**

Olkoot $a_1, a_2, \ldots , a_n$ pareittain yhteistekijättömiä positiivisia kokonaislukuja, jotka eivät ole neliölukuja. Olkoon $S$ jokin osajoukko joukosta $\lbrace 1, 2, \ldots , n \rbrace$, ja olkoon $T$ niiden $p$ joukko, joilla $L(a_i, p) = 1$ jos ja vain jos $i \in S$. Osoita, että $\delta(T) = 2^{-n}$.

**Korkeammat potenssit**

Neliönjäännöksiä on puolet luvuista tiettyä $p$ kohden, joten heuristisesti $a$ on neliönjäännös modulo puolet alkuluvuista, ellei alkuluvut "suosisi" $a$:ta olemaan neliönjäännös. Tämä tapahtuu postauksen tulosten nojalla täsmälleen silloin, kun $a$ on neliöluku, eli vain ilmeisessä tapauksessa.

Esitä heuristinen perustelu sille, että $a$ on kuutionjäännös modulo $p$ (eli yhtälöllä $x^3 \equiv a \pmod{p}$ on ratkaisu) $\frac{2}{3}$ alkuluvuista $p$ kun $a$ ei ole kuutioluku. Esitä vastaava perustelu eksponentin $3$ sijasta alkulukueksponentille $q$, jolloin tiheyden tulisi olla $\frac{q-1}{q}$.

Huomautetaan, että heuristiikat todella antavat oikean tuloksen, mutta väitteiden todistaminen vaatii järeämpää kalustoa. Vinkkinä tehtävään toimii tämän [monisteen](https://matematiikkakilpailut.fi/kirjallisuus/primitiivijuuret.pdf) aihe.
