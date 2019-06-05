---
layout: post
author: "Olli Järviniemi"
title: "Polynomien yhteiset alkutekijät, osa 10: sovelluksia"
math: true
excerpt_separator: "<!--jatkuu-->"

---
Tässä postauksessa esitetään työn sovelluksia neliönjäännöksiä ja korkeampien potenssien jäännöksiä käsitteleviin kysymyksiin.


<!--jatkuu-->

**Sisällysluettelo**


1. [Osa 1 - johdanto](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA11johdanto.html)
2. [Osa 2 - esitiedot](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA10esitiedot.html)
3. [Osa 3 - tulokset](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA09tulokset.html)
4. [Osa 4 - motivaatio](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA08motivaatio.html)
5. [Osa 5 - heikko versio](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA07heikko.html)
6. [Osa 6 - yleinen tapaus](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA06yleinen.html)
7. [Osa 7 - lause 2](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA05lause2.html)
8. [Osa 8 - lause 3](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA04lause3.html)
9. [Osa 9 - lause 4](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA03lause4.html)
10. Osa 10 - sovelluksia
11. [Osa 11 - lisäaiheita](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA01lisaaiheita.html)


Tämän postauksen sisältöä ei tilanpuutteen vuoksi kirjoitettu lopulliseen tutkielmaan. Pidän tämän postauksen tuloksia hyvin mielenkiintoisina (vaikkakin todistuksia aavistuksen puuduttavina), joten esitän ne tässä.

Ensimmäisenä neliönjäännöksistä tulos, jota olen sivunnut [aiemminkin](https://blog.matematiikkakilpailut.fi/2018/12/09/Nelionjaannos.html).

# Lause

Olkoot $a_1, a_2, \ldots , a_n \in \mathbb{Z}$ sellaisia, ettei minkään joukon $\lbrace a_1, a_2, \ldots , a_n \rbrace$ epätyhjän osajoukon alkioiden tulo ole neliöluku. Olkoon $S \subset \lbrace 1, 2, \ldots , n \rbrace$. Olkoon $T_S$ niiden $p$ joukko, joilla on seuraava ominaisuus:

$a_i$ on neliönjäännös modulo $p$ jos ja vain jos $i \in S$.

Tällöin

$$\delta(T_S) = \frac{1}{2^n}.$$


## Todistus

Tutkimme siis polynomien $P_i(x) = x^2 - a_i$ alkutekijöitä.

Osoitetaan ensiksi, että voimme soveltaa lauseen 3 tulosta.

**Lemma**

Olkoon $F$ polynomin $P_1P_2 \ldots P_n$ juurikunta. $[F : \mathbb{Q}] = 2^n$.

**Todistus**

Olkoon $B$ joukko, joka sisältää kaikki joukon $\lbrace a_1, a_2, \ldots , a_n \rbrace$ osajoukkojen alkioiden tulot, eli $B$ sisältää $2^n$ alkiota.

Olkoon $C$ joukko, joka sisältää luvut muotoa $\sqrt{b}, b \in B$.

Riittää osoittaa, että $C$:n alkiot ovat lineaarisesti riippumattomia rationaalilukujen yli. Toisin sanoen, **ei** ole olemassa nollasta eroavia rationaalilukua $q_1, q_2, \ldots , q_k$ ja pareittain erisuuria $C$:n alkioita $c_1, c_2, \ldots , c_k$, joilla

$$q_1c_1 + q_2c_2 + \ldots + q_kc_k = 0$$

Miksi tämä on riittävä ehto? Oletetaan, että $[F : \mathbb{Q}] < 2^n$, tavoitteena vastaoletus yllä esitetyn ehdon kanssa. Käyttäen vastaavanlaista ideaa kuin lauseen 3 todistuksessa, saadaan

$$[F : \mathbb{Q}] = [\mathbb{Q}(\sqrt{a_1}, \ldots , \sqrt{a_n}) : \mathbb{Q}(\sqrt{a_1}, \ldots , \sqrt{a_{n-1}})] \cdots [\mathbb{Q}(\sqrt{a_1}, \sqrt{a_2}) : \mathbb{Q}(\sqrt{a_1})][\mathbb{Q}(\sqrt{a_1}) : \mathbb{Q}].$$

Oikean puolen tulon jokainen termi on selvästi enintään $2$. Jos kaikki termit olisivat $2$, pätisi $[F : \mathbb{Q}] = 2^n$, mikä ei ole mielenkiintoista. Oletetaan siis, että jokin tulontekijä on $1$. Täten on olemassa sellainen $i$, jolla luvun $\sqrt{a_i}$ minimaalisen polynomin aste kunnassa $\mathbb{Q}(\sqrt{a_1}, \ldots \sqrt{a_{i-1}})$ on $1$, eli $\sqrt{a_i}$ kuuluu tähän kuntaan. Siispä $\sqrt{a_i}$ voidaan esitää polynomina luvuista $\sqrt{a_1}, \ldots , \sqrt{a_{i-1}}$. Nähdään, että tämä on ristiriita lineaarisesti riippumattomuuden kanssa.

On melko tunnettua, vaikkeikaan helppoa todistaa, että neliöjuuret ovat lineaarisesti riippumattomia rationaalilukujen yli (epätriviaaleissa tapauksissa). Lyhyt ja kohtuullisen helppo todistus käyttäen juurikuntien isomorfismeja löytyy Paul Garrettin monisteesta [Linear independence of roots](http://www-users.math.umn.edu/~garrett/m/v/linear_indep_roots.pdf).

**Toteutus**

Åalapelin palaset on nyt koottu, ja ideana on soveltaa lausetta 3 väitteen todistamiseen, ehkä käyttäen inkluusio-ekskluusiota ja induktiota. Tätä kautta saa todistuksen (lukija voi itse vaikka yrittää), mutta lähestyn ongelmaa eri näkökulmasta.

Olkoon $F$ polynomien $P_1, P_2, \ldots , P_n$ juurikuntien compositum, eli olkoon $F$ pienin kunta, joka sisältää kaikkien polynomien $P_i$ juurikunnat. Edellisestä päättelystä ei ole vaikeaa nähdä, että $C$ on kanta $\mathbb{Q}$-vektoriavaruudelle $F$. Jokainen $F$:n alkio voidaan siis kirjoittaa muodossa

$$\sum q_ic_i,$$

missä $q_i \in \mathbb{Q}$ ja $c_i \in C$, ja tämä esitys on yksikäsitteinen.

Tutkitaan $F$:n Galois'n ryhmää $G$. Jokainen $\sigma \in G$ kuvaa $C$:n alkion $c$ joko $c$:ksi tai $-c$:ksi. Ideana on seuraava:

Olkoot $s_1, s_2, \ldots , s_n$ kokonaislukuja, jotka ovat jokainen joko $-1$ tai $1$. On olemassa sellainen $\sigma \in G$, jolla $\sigma(\sqrt{a_i}) = s_i\sqrt{a_i}$ kaikilla $i$.

Todistus on triviaali: määritellään $f(\sqrt{a_i}) = s_ia_i$. Voimme vain laajentaa $f$:n olemaan isomorfismi $F \to F$. Se, miksi tämä toimii, johtuu siitä, että $[F : \mathbb{Q}] = 2^n$ - tästä seuraa yllä esitetty $C$:n alkioiden lineaarinen riippumattomuus, ja meillä ei synny ristiriitaista määrittelyä.

(Esimerkki tilanteesta, jossa tulisi ristiriitainen määrittely: vaadimme, että $\sigma(\sqrt{2}) = \sqrt{2}, \sigma(\sqrt{3}) = \sqrt{3}$ ja $\sigma(\sqrt{6}) = -\sqrt{6}$.)

Tämä idea todistaa, että $F$:n Galois'n ryhmän $G$ koko on $2^n$. Lisäksi, on olemassa täsmälleen yksi $\sigma \in G$, jolla $\sigma(\sqrt{a_i}) = \sqrt{a_i}$ jos ja vain jos $i \in S$.

Frobeniuksen lause todistaa väitteen vaikkapa näin: olkoon $P_T$ niiden $P_i$ tulo, joilla $i \not\in S$. Soveltamalla yllä todistettua tulosta polynomille $P_T$ saadaan sen alkutekijöiden tiheydeksi

$$1 - \frac{1}{2^{n - |S|}},$$

koska ainoa $P_T$:n Galois'n ryhmän alkio $\sigma$, joka ei kuvaa jotain $P_T$:n juurta itselleen, on se $\sigma$ jolla $\sigma(\sqrt{a_i}) = -\sqrt{a_i}$ kaikilla $i \not\in S$.

Soveltamalla lausetta 3 saamme polynomien $P_i, i \in S$ ja $P_T$ yhteisten alkutekijöiden tiheydeksi

$$\frac{1}{2^{|S|}}\Big(1 - \frac{1}{2^{n - |S|}}\Big).$$

Haluamme vähentää tämän tiheyden tiheydestä

$$\delta\Big(\bigcap_{i \in S} S(P_i)) \Big).$$

Viimeksi mainittu on lauseen 3 avulla $2^{-\mid S \mid}$, ja väite seuraa.

Tämä todistus on tietyssä mielessä oikea tapa ajatella lausetta 3 - lauseen ehto varmistaa, että polynomin $P_1P_2 \cdots P_n$ Galois'n ryhmä on vain $G_1 \times G_2 \times \cdots \times G_n$, missä $G_i$ on $P_i$:n Galois'n ryhmä. Tämän vuoksi lauseen väite seuraa Frobeniuksen lauseesta.

Tämän idean avulla seuraava väite on ilmeinen:

Olkoot $P_1, P_2, \ldots , P_n$ sellaisia, jotka toteuttavat lauseen 3 ehdot. Olkoon $S$ joukon $\lbrace 1, 2, \ldots , n \rbrace$ jokin osajoukko. Olkoon $T$ niiden $p$ joukko, joilla $p \in S(P_i)$ jos ja vain jos $i \in S$. Tällöin

$$\delta(T) = \prod_{i \in S} \delta(S(P_i)) \prod_{j \not\in S} 1 - \delta(S(P_j)).$$

Ei kovin yllättävää, mutta miellyttävää, että tämä voidaan todistaa.

# Korkeampien potenssien jäännökset

Neliönjäännökset-postauksen viimeisessä harjoitustehtävässä pyydettiin esittämään heuristiikka väitteelle $\delta(S(x^p - a)) = \frac{p-1}{p}$, kun $p$ on alkuluku ja $a$ ei ole kokonaisluvun $p$:nnes potenssi. Esitän ensin oman heuristiikkani, minkä jälkeen todistan väitteen Frobeniuksen lauseella.

## Heuristiikka

Valitaan jokin satunnainen alkuluku $q$. Tutkitaan kahta eri tapausta.

1. $q \not\equiv 1 \pmod{p}$. Funktio $f(x) = x^p$ on injektiivinen modulo $p$ postauksen [Juuren ottaminen moduloissa](https://blog.matematiikkakilpailut.fi/2018/05/17/Juuri.html) nojalla. Täten se on myös surjektiivinen, eli yhtälöllä $f(x) \equiv c \pmod{q}$ on ratkaisu kaikilla $c$. Tässä tapauksessa todennäköisyys sille, että $q \in S(x^p - a)$, on $1$.

2. $q \equiv 1 \pmod{p}$. Olkoon $g$ primitiivijuuri modulo $q$. Kaikki $p$:nnet potenssit modulo $q$ ovat muotoa $g^{ip}$, $i \in \mathbb{Z}$ (ja luku $0$). Käyttäen vaikkapa Fermat'n pientä lausetta nähdään, että $p$:nsiä potensseja on $\frac{q-1}{p}$ kappaletta, kun lukua $0$ ei lasketa.
Siis osuus $\frac{1}{p}$ luvuista $1, 2, \ldots , q-1$ on $p$:nsiä potensseja. Todennäköisyys sille, että juuri luku $a$ on $p$:nnes potenssi on heuristisesti $\frac{1}{p}$.

Tapauksen $1$ mukaiset $q$ muodostavat Dirichlet'n lauseen tiheysversion nojalla osuuden $\frac{p-2}{p-1}$ alkuluvuista, ja tapauksen $2$ mukaisia $q$ on $\frac{1}{p-1}$. Kertomalla tapauksien todennäköisyydet todennäköisyydellä sille, että $a$ on $p$:nnes potenssi, saadaan lopullinen todennäköisyys:

$$\frac{p-2}{p-1} \cdot 1 + \frac{1}{p-1} \cdot \frac{1}{p} = \frac{p-1}{p}.$$


## Todistus

Polynomin $P(x) = x^p - a$ juuret ovat

$$\sqrt[p]{a}, \sqrt[p]{a}\zeta_p, \sqrt[p]{a}\zeta_p^2 , \ldots , \sqrt[p]{a}\zeta_p^{p-1}.$$

Huomaamme, että $P$:n juurikunta $F$ on $\mathbb{Q}(\sqrt[p]{a}, \zeta_p)$.

Tutkitaan $P$:n Galois'n ryhmää $G$. Jokainen $\sigma \in G$ määräytyy lukujen $\sigma(\sqrt[p]{a})$ ja $\sigma(\zeta_p)$ avulla. Lisäksi $G$ sisältää kaikki ne kuvakset, mitä voisi olettaa:

**Lemma 1**

Olkoon $0 \le b < p$ kokonaisluku, ja olkoon $0 < c < p$ kokonaisluku. On olemassa sellainen $\sigma \in G$, jolla pätee:

1. $\sigma(\sqrt[p]{a}) = \sqrt[p]{a}\zeta_p^b.$

2. $\sigma(\zeta_p) = \zeta_p^c.$

Lisäksi jokaista $\sigma \in G$ vastaa edellä kuvaillut $b, c$.

**Todistus**

Väite pätee myös muillekin luvuille kuin alkuluvuille $p$:

**Vahvempi versio**

Olkoon $m$ positiviinen kokonaisluku, ja olkoon $G$ polynomin $x^m - a$ Galois'n ryhmä. Oletetaan, että $m$ on pariton ja $x^m - a$ ei jakaudu rationaaliluvuissa.

Olkoot $0 \le b, c < p$ kokonaislukuja, joilla $syt(c, m) = 1$. On olemassa sellainen $\sigma \in G$, jolla:

1. $\sigma(\sqrt[m]{a}) = \sqrt[m]{a}\zeta_m^b.$

2. $\sigma(\zeta_m) = \zeta_m^c.$

Lisäksi jokaista $\sigma \in G$ vastaa edellä kuvaillut $b, c$.

**Todistus vahvemmalle versiolle**

On selvää, että jokaisella $\sigma \in G$ on edellä kuvaillut $b, c$. Enää tulee osoittaa toinen suunta. Tämä seuraa, jos osoitetaan, että $\mid G \mid = m\phi(m)$ (miksi?). Tämän on todistanut David Gluck ja I. M. Isaacs artikkelissaan [Radical and cyclotomic extensions of the rational numbers](https://www.ams.org/journals/proc/2007-135-11/S0002-9939-07-08864-8/S0002-9939-07-08864-8.pdf) (lause 3.1.).


Lemman 1 avulla tiedämme siis polynomin $x^p - a$ Galois'n ryhmän koon (voimme käyttää vahvempaa versiota, kts. jaottomuuskriteeri alla). Lisäksi ei ole enää vaikeaa laskea niiden kuvausten $\sigma \in G$ määrää, jotka kuvaavat jonkin polynomin $x^p - a$ juuren itselleen. Käyttäen Frobeniuksen lausetta saadaan haluttu väite. En mene yksityiskohtiin tässä, koska en näe niitä kovin kiinnostavina.

## Variantteja

Voimme myös laskea vaikkapa polynomien $x^3 - 2$, $x^3 - 3$ yhteisien alkutekijöiden tiheyden. Emme kuitenkaan voi käyttää lausetta 3, koska näiden polynomien juurikuunat sisältävät luvun $\zeta_3$. Voimme kuitenkin tutkia vaikkapa tulon $(x^3 - 2)(x^3 - 3)$ Galois'n ryhmän käyttäytymistä, ja saada sieltä halutun tiheyden.

Polynomit muotoa $x^{p^k} - a$ ovat myös mielenkiintoisia. Esimerkiksi polynomien $x^{p^2} - 2$ ja $x^{p^2} - 2^p$ alkutekijöiden tiheyden tutkiminen antaa jotain uutta.

En mene näihin aiheisiin sen syvemmin. Pointtina on kuitenkin se, että näitä tiheyksiä voidaan laskea. Lisäksi tiheys $1 - \frac{1}{n}$ voidaan saavuttaa kaikilla alkuluvun potensseilla $n$, ainakin jos $n$ ei ole kakkosen potenssi (syy alla).

Vahvemman version käyttäminen vaatii jaottomuuskriteerin:

**Polynomin $x^n - a$ jaottomuus**

Olkoon $P(x) = x^n - a$, $a \in \mathbb{Q}$. $P$ jakautuu rationaaliluvuissa jos ja vain jos jompikumpi seuraavista ehdoista pätee:

1. Jollain $p \mid n$ luku $a$ on jonkin rationaaliluvun $p$:nness potenssi

2. $4 \mid n$ ja $a$ on muotoa $-4c^4$ jollain $c \in \mathbb{Q}$. Tämä johtuu Sophie-Germainin identiteetistä. Kts. esim. [tämä postaus](https://blog.matematiikkakilpailut.fi/2018/04/16/Tekijoita.html).

Todistus ei ole missään nimessä triviaali, mutta netistä pitäisi löytyä todistus väitteelle.

Lisäksi mainitaan vielä helppo kilpailumatematiikkahenkinen fakta joilla ongelman saa redusoitua alkulukujen potensseihin:

**Lemma 4**

Olkoot $m, n \in \mathbb{Z_+}$, ja olkoon $d$ niiden syt. Olkoon vielä $a \in \mathbb{Z}$. Pätee:

$$S(x^m - a) \cap S(x^n - a) = S(x^d - a).$$

Kiinnostunut lukija voi itse kokeilla, millaisia tuloksia saa irti näillä tiedoilla. Hyvä harjoitustethävä onkin todistaa, että tiheyden yläraja $1 - \frac{1}{n}$ on saavutettavissa.

[Seuraava postaus.](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA01lisaaiheita.html)
