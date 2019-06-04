---
layout: post
author: "Olli Järviniemi"
title: "Polynomien yhteiset alkutekijät, osa 11: lisäaiheita"
math: true
excerpt_separator: "<!--jatkuu-->"

---

Tässä postauksessa esitän lisäaiheita, jotka käsittelevät hieman syvemmin teoriaa kuin itse tutkielma.

<!--jatkuu-->

**Sisällysluettelo**

1. [Osa 1 - johdanto](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAjohdanto.html)
2. [Osa 2 - esitiedot](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAesitiedot.html)
3. [Osa 3 - tulokset](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAtulokset.html)
4. [Osa 4 - motivaatio](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAmotivaatio.html)
5. [Osa 5 - heikko versio](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAheikko.html)
6. [Osa 6 - yleinen tapaus](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAyleinen.html)
7. [Osa 7 - lause 2](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAlause2.html)
8. [Osa 8 - lause 3](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAlause3.html)
9. [Osa 9 - lause 4](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAlause4.html)
10. [Osa 10 - sovelluksia](https://blog.matematiikkakilpailut.fi/2019/06/4/PYAsovelluksia.html)
11. Osa 11 - lisäaiheita


## Alkulukujen jakautuminen kuntalaajennuksissa

Ennen kuin pääsen itse asiaan, määrittelen pari käsitettä.

**Algebrallinen kokonaisluku**

Algebrallista lukua $\alpha$ kutsutaan algebralliseksi kokonaisluvuksi, jos luvun $\alpha$ minimaalinen polynomi on kokonaislukukertoiminen.

**Esimerkki**

$i$ on algebrallinen kokonaisluku (min. pol. on $x^2 + 1$), mutta $\frac{i}{2}$ ei ole (min. pol. on $x^2 + \frac{1}{4}$). Rationaaliluku $r$ on algebrallinen kokonaisluku jos ja vain jos $r$ on kokonaisluku.

Jokaisella algebrallisella luvulla $\alpha$ on olemassa sellainen $n \in \mathbb{Z_+}$, jolla $n\alpha$ on algebrallinen kokonaisluku. Tämä jätetään helpohkoksi harjoitustehtäväksi.

**Ring of integers**

Olkoon $K = \mathbb{Q}(\alpha)$ jollain algebrallisella luvulla $\alpha$. Olkoon $O_K$ niiden $\beta \in K$ joukko, jotka ovat algebrallisia kokonaislukuja. $O_K$ on rengas (todistus on samankaltainen kuin [tämän postauksen](https://blog.matematiikkakilpailut.fi/2018/09/02/Algebralliset.html) todistus). Englanniksi sanotaan "$O_K$ is the ring of integers of $K$". Suomenkieliset termit ovat minulle hieman vieraita, joten käytän englanninkielisiä termejä.

**Esimerkki**

Olkoon $K = \mathbb{Q}(i)$. Tällöin $O_K$ ovat ns. Gaussin kokonaisluvut, eli luvut muotoa $a + bi, a, b \in \mathbb{Z}$.

Gaussin kokonaisluvuista lisää Esa Vesalaisen materiaalissa [Lyhyt johdatus alkeelliseen lukuteoriaan](https://matematiikkakilpailut.fi/kirjallisuus/laajalukuteoriamoniste.pdf), luku 7. Esan materiaalissa on osoitettu seuraava väite alkulukujen jakautumisesta Gaussin kokonaisluvuissa:

Olkoon $p$ alkuluku. $p$ ei jakaudu Gaussin kokonaisluvuissa $O_{\mathbb{Q}(i)}$ jos ja vain jos $p \equiv 3 \pmod{4}$.

Tässä kohtaa muistutan seuraavasta väitteestä:

Olkoon $p$ alkuluku. $p$ ei ole polynomin $x^2 + 1$ alkutekijä jos ja vain jos $p \equiv 3 \pmod{4}$.

Selvä analogia - onko sellainen olemassa yleisestikin? On. Olin hyvin tyytyväinen löytäessäni tämän tuloksen - olin miettinyt jo pidemmän aikaa tämän väitteen pätemistä (juurikin Gaussin kokonaislukujen vuoksi) ennen kuin löysin viitteen tulokselle. Väitettä kutsutaan Dedekindin tekijöihinjakokriteeriksi (Dedekind's factorization criterion), ja väitteestä voi lukea lisää kenenkä muunkaan kuin Keith Conradin [materiaalista](https://kconrad.math.uconn.edu/blurbs/gradnumthy/dedekindf.pdf).

**Jakautuminen**

Olkoon $K = \mathbb{Q}(\alpha)$ jollain algebrallisella luvulla $\alpha$, ja olkoon $O_K$ kuten edellä. Olkoon $f$ luvun $\alpha$ minimaalinen polynomi. Kaikilla paitsi äärellisen monella $p$ pätee seuraava väite:

$p$ jakautuu samalla tavalla renkaassa $O_K$ kuin $f$ jakautuu modulo $p$.

**Huomautus**

Puhun siitä, kuinka $p$ jakautuu joukossa $O_K$. Tämä on kuitenkin hieman virheellistä: $O_K$:ssa **ei välttämättä päde uniikki tekijöihinjako** kuten kokonaisluvuissa. Esim. jos $K = \mathbb{Q}(\sqrt{-5})$, niin $6 = 2 \cdot 3 = (1 - \sqrt{5})(1 + \sqrt{5})$ antaa kaksi eri tapaa jakaa luku $6$ tekijöihin, ja näitä tulontekijöitä ei voi jakaa eteenpäin tekijöihin.

Ongelma kierretään tutkimalla ns. ideaaleja. Ideaaleja voi jakaa tekijöihin, ja tällä kertaa tekijöihinjako on uniikki. Jokaista lukua vastaa jokin ideaali (mutta on myös muita ideaaleja). Yleisesti tutkitaan siis, miten $p$:tä vastaava ideaali jakautuu renkaassa $O_K$. Yllä oleva tulos koskee siis ideaalien jakautumista.

**Tämä muutos on todellisuudessa melko suuri.** Syynä siihen, miksi otin väitteen tästä huolimatta esille on se, että **muissa materiaaleissa puhutaan käytännössä aina ideaalien jakautumisesta eikä polynomien alkutekijöistä**. Nämä kuitenkin vastaavat toisiaan, eli kirjallisuuden tuloksia jakautumisesta voi käyttää suoraan polynomien alkutekijöiden käsittelyyn.

Lisäksi, usein valitaan $K = \mathbb{Q}(\alpha)$, missä $\alpha$ on algebrallinen kokonaisluku. Tällöin $f$ on kokonaislukukertoiminen. Tällä ei kuitenkaan ole väliä - $f$ voidaan, jälleen kerran, kertoa sopivalla vakiolla, jolloin se on kokonaislukukertoiminen.

**Esimerkki**

Gaussin kokonaislukujen tapauksessa $O_K$ käyttäytyy miellyttävästi. Tässä on jonkinlainen esimerkki väitteen vastaavuudesta.

$x^2 + 1$ ei jakaudu modulo $3$, ja $3$ ei jakaudu Gaussin kokonaisluvuissa (kts. yllä oleva tulos).

$x^2 + 1$ jakautuu kahdeksi erisuureksi polynomiksi modulo $5$, koska $x^2 + 1 \equiv (x - 2)(x + 2) \pmod{5}$. Vastaavasti, $5 = -(i - 2)(i + 2)$.

$x^2 + 1$ on neliö mod $2$, koska $x^2 + 1 \equiv (x + 1)^2 \pmod{2}$. Vastaavasti, $2 = -i(i+1)^2$. Huomaa, että tässä $-i$ vastaa vain etumerkkiä, jonka saa kumottua kertomalla sen luvulla $i$.




## Äärellisten kuntien kuntalaajennukset

Äärellinen kunta on kunta, jossa on vain äärellinen määrä alkioita. Yksinkertaisin esimerkki on kokonaisluvut modulo $p$.

Äärellisille kunnille pätee seuraavat ominaisuudet:

1. Äärellisen kunnan koko on aina alkuluvun potenssi. Jos kunnan koko on $p^k$, niin $p \cdot a = 0$ kaikilla $a$, jotka kuuluvat tähän kuntaan.

2. Kaikilla alkuluvun potensseilla $p^k$ on olemassa äärellinen kunta $\mathbb{F}_{p^k}$, jonka koko on $p^k$. **Tämä kunta on uniikki** isomorfisia kuntia lukuun ottamatta.

Äärellisten kuntien kuntalaajennuksista voidaan sanoa seuraavat asiat:

3. Olkoon $\mathbb{F}$ äärellinen kunta, ja olkoon $P$ kunnassa $\mathbb{F}$ jaoton polynomi, jonka aste on $d$. Olkoon $\alpha$ $P$:n juuri. Tällöin $[\mathbb{F}(\alpha) : \mathbb{F}] = d$.

4. Olkoot $\mathbb{F}, P, \alpha$ kuten edellä. $P$:n juurikunta $\mathbb{F}(\alpha_1, \alpha_2, \ldots , \alpha_d)$ on $\mathbb{F}(\alpha)$.

Ominaisuus 3. on täysin sama kuin rationaaliluvuissa. Näetkö, miten 4. seuraa väitteistä 2. ja 3.?

Seuraavaksi esitetään konkreettinen esimerkki kuntalaajennuksien soveltamisesta kilpailutehtävään. Toivon, että esimerkki on valaiseva.

###EGMO 2016, T6

Olkoon $S$ niiden positiivisten kokonaislukujen $n$ joukko, joilla luvulla $n^4$ on tekijä välillä $n^2 + 1, n^2 + 2, \ldots , n^2 + 2n$. Osoita, että on olemassa äärettömän monta $S$:n alkiota, jotka ovat kongruentteja $k \pmod{7}$ jos ja vain jos $k \not\equiv 3, 4 \pmod{7}$.

###Todistus

Tutkitaan ensin, milloin tapahtuu $n^2 + k \mid n^4$ jollain $1 \le k \le 2n$. Huomaamme

$$n^2 + k \mid n^4 \Leftrightarrow n^2 + k \mid n^4 - (n^2 + k)(n^2 - k) = k^2$$

Siis $n^2 + k \mid k^2$. Luku $k$ ei ole kovin iso: pätee $k \le 2n$, eli

$$k^2 < 4(n^2 + k).$$

Tutkitaan eri tapauksia:

1. $n^2 + k = k^2$. Tämä on mahdoton tapaus - jos $k \le n$, niin oikea puoli on pienempi kuin vasen, ja jos $k > n$, niin oikea puoli on isompi kuin vasen.

2. $2(n^2 + k) = k^2$. Tällöin $2n^2 = k^2 - 2k = (k-1)^2 - 1$, eli $(k-1)^2 - 2n^2 = 1$. Tämä on Pellin yhtälö.

3. $3(n^2 + k) = k^2$. Tämä saadaan muutettua myös Pellin yhtälöksi standardimenetelmin: $k$:n tulee olla jaollinen kolmella, joten olkoon $k = 3m$. Tällöin yhtälö on $3n^2 = 9m^2 - 9m$, eli $n^2 = 3(m^2 - m)$. Ja vielä, $n$:n tulee olla jaollinen kolmella, eli $n = 3t$, ja yhtälö on $3t^2 = m^2 - m$.
Kerrotaan yhtälö puolittain neljällä, eli $3(2t)^2 = 4m^2 - 4m = (2m-1)^2 - 1$. Saamme siis $x^2 - 3y^2 = 1$, missä $x = 2m-1$ ja $y = 2t$.


Tutkimme siis yhtälöitä $x^2 - 2y^2 = 1$ ja $x^2 - 3y^2 = 1$. Mikäli Pellin yhtälöt eivät ole tuttuja, kannattanee lukea Matti Lehtisen moniste [Pellin yhtälöistä](https://matematiikkakilpailut.fi/kirjallisuus/pell.pdf). Tulemme käyttämään seuraavia tietoja Pellin yhtälöistä, eli muotoa $x^2 - Dy^2 = 1$ oleviasta yhtälöistä, missä $D > 0$ ei ole neliö:

1. Tällä yhtälöllä on aina äärettömän monta ratkaisua.
2. Kaikki positiiviset ratkaisut saadaan löytämällä pienin positiivinen ratkaisu $(x_1, y_1)$, ja asettamalla $n$:nnessä ratkaisussa $x_n$ olemaan luvun $(x_1 + y_1\sqrt{D})^n$ kokonaislukuosa, ja $y_n$ olemaan tämän luvun $\sqrt{D}$-osa.

Tutkitaan ensiksi yhtälöä $x^2 - 2y^2 = 1$. Tämän yhtälön pienin (epätriviaali) ratkaisu on $x = 3, y = 2$. Siispä yleisesti $n$:nnen ratkaisun saa valitsemalla $x_n$ olemaan luvun $(3 + 2\sqrt{2})^n$ kokonaislukuosa, ja $y_n$ olemaan kyseisen luvun $\sqrt{2}$-osa. Tämän voi myös kirjoittaa eksplisiittisenä kaavana:

$$x_n = \frac{(3 + 2\sqrt{2})^n + (3 - 2\sqrt{2})^n}{2}.$$

Ideana siis se, että $\sqrt{2}$-osat kumoavat toisensa osoittajassa. Vastaavasti saadaan eksplisiittinen kaava $y_n$:lle.

Haluamme loppujen lopuksi tutkia lukuja $x_n$ ja $y_n$ modulo $7$. Tutkitaan yllä olevaa $x_n$:n lauseketta: se on, kuten totesimme, kokonaisluku. Jos tutkimme sitä modulo $7$, voidaan luvulla $2$ jakaminen ajatella vain luvulla $4$ kertomisena, koska luvun $2$ käänteisalkio modulo $7$ on $4$. Vastaavasti, $\sqrt{2}$ voidaan tulkita lukuna $3$ modulo $7$, koska $3^2 \equiv 2 \pmod{7}$. Siispä

$$x_n \equiv 4\Big((3 + 2\cdot 3)^n + (3 - 2\cdot 3)^n \Big) \equiv 4(2^n + 4^n) \pmod{7}.$$

Tästä on helppoa ratkaista kaikki $x_n$:n mahdolliset arvot modulo $7$, ja vastaavasti saamme $y_n$:n mahdolliset arvot. Menetelmä voi tuntua hieman arvelluttavalta, mutta se toimii kyllä.

Tutkitaan sitten tapausta $x^2 - 3y^2 = 1$. Tässä saamme pienimmän ratkaisun $x = 2, y = 1$, eli yleisesti

$$x_n = \frac{(2 + \sqrt{3})^n - (2 - \sqrt{3})^n}{2}.$$

Nyt ongelmaksi muodostuu se, että $\sqrt{3}$ ei olekaan kokonaisluku modulo $7$. Edellä tutkimme lukuja $x_n$ kunnassa $\mathbb{F}_7$, mutta nyt joudumme tutkimaan isompaa kuntaa $\mathbb{F}_7(\sqrt{3})$. Tämä kunta sisältää siis luvut muotoa $a + b\sqrt{3}$, missä $a, b \in \mathbb{F}_7$. Yhteenlasku ja kertolasku määritellään aivan kuten luulisikin, eli esimerkiksi kertolasku on

$$(a + b\sqrt{3})(c + d\sqrt{3}) = ac + (ad + bc)\sqrt{3} + bd\sqrt{3}^2 = (ac + 3bd) + (ad + bc)\sqrt{3}$$

Ajatusta voi helpottaa vertaamalla tilannetta kompleksilukuihin, joille määritellään kertolasku aivan vastaavasti. Sen sijaan, että laajentaisimme reaalilukuja $i$:llä, niin laajennamme kuntaa $\mathbb{F}_7$ luvulla $\sqrt{3}$.

Siispä, kun yhtäsuuruus tulkitaan kunnassa $\mathbb{F}_7(\sqrt{3})$, pätee

$$x_n = 4\Big( (2 + \sqrt{3})^n - (2 - \sqrt{3})^n \Big),$$

ja voimme laskea lukujen $2 \pm \sqrt{3}$ potensseja: $(2 + \sqrt{3})^0 = 1$, eksponentilla $1$ saadaan $(2 + \sqrt{3})^1 = 2 + \sqrt{3}$, eksponentilla $2$ taas $(2 + \sqrt{3})^2 = 4\sqrt{3}$, eksponentilla $3$ vielä $(2 + \sqrt{3})^3 = 5 + \sqrt{3}$, ja vielä $(2 + \sqrt{3})^4 = -1$. Tämän jälkeen potenssit ovat kuten edellä, mutta negaiitivismerkkisiä, ja lopulta $(2 + \sqrt{3})^8 = 1$.

Tällä idealla saamme laskettua luvun $x_n$ kaikki mahdolliset arvot.

Tekemällä yllä esitetyt ideat molemmille yhtälöistä $x^2 - 2y^2 = 1$ ja $x^2 - 3y^2 = 1$ sekä purkamalla tehdyt sijoitukset saadaan viimeisteltyä ratkaisu. Itse laskeminen ei ole kovin mielenkiintoista, ja se sivuutetaan.

###Huomautus (Fermat'n pieni lause)

Totesimme edellä. että $(2 + \sqrt{3})^4 = -1$, eli $(2 + \sqrt{3})^8 = 1$ kunnassa $\mathbb{F}_7(\sqrt{3})$. Ei ole yllättävää, että jossain kohtaa potenssiinkorotus johtaa lukuun $1$. Tälle on hyvin yksinkertainen selitys:

Fermat'n pieni lause todistetaan yleensä seuraavasti: olkoon $a \not\equiv 0 \pmod{p}$. Tällöin luvut $a, 2a, 3a, \ldots , (p-1)a$ ovat vain lukujen $1, 2, \ldots , p-1$ permutaatio. Siispä

$$a \cdot 2a \cdot 3a \cdot \ldots \cdot (p-1)a \equiv 1 \cdot 2 \cdot \ldots \cdot (p-1) \pmod{p}$$

Supistamalla termejä pois saadaan $a^{p-1} \equiv 1 \pmod{p}$.

Todistetaan nyt vastaavasti yleistys Fermat'n pienelle lauseelle mille tahansa äärelliselle kunnalle. Konkreettisena esimerkkinä kannattaa miettiä yllä esitettyä tapausta $\mathbb{F}_7(\sqrt{3})$.

**Fermat'n pienen lauseen yleistys**

Olkoon $\mathbb{F}_{p^k}$ (se) kunta, jonka koko on $p^k$. Tällöin $a^{p^k - 1} = 1$ kaikilla $a \in \mathbb{F}_{p^k}$, joilla $a \neq 0$.

**Todistus**

Olkoon $S$ joukko, joka sisältää luvut muotoa $at, t \in \mathbb{F}_{p^k}$, missä $t \neq 0$. Osoitetaan, että $S$ sisältää jokaisen joukon $\mathbb{F}_{p^k}$ nollasta eroavan luvun (täsmälleen kerran). Selvästi kaikilla $s \in S$ pätee $s \neq 0$ - muutenhan pätisi $s = at = 0$. Mutta koska $a, t \neq 0$, on niillä olemassa käänteisalkiot $a^{-1}$ ja $t^{-1}$ (käsittelemmehän kuntaa!), ja kertomalla yhtälön $at = 0$ puolittain tulolla $a^{-1}t^{-1}$ saamme $1 = 0$.

Oletetaan sitten, että $at = at'$ jollain $t, t' \in \mathbb{F}_{p^k}$. Kertomalla puolittain luvulla $a^{-1}$ saamme $t = t'$.

Siispä luvut $at, t \in \mathbb{F}_{p^k}$ ovat erisuuria, nollasta eroavia alkioita, mikä todistaa väitteen.

Ja nyt, kuten Fermat'n pienen lauseen todistuksessa, joukon $S$ alkioiden tulo on sama kuin kunnan $\mathbb{F}_{p^k}$ nollasta eroavien alkioiden tulo. Ja kuten edellisessä todistuksessa, sieventämällä saamme $a^{p^k - 1} = 1$.

###Huomautus (asteet)

Fermat'n pienen lauseen yleistys takaa, että $(2 + \sqrt{3})^{48} = 1$, mutta totesimme, että $(2 + \sqrt{3})^8 = 1$. Tämä ei ole ristiriita - Fermat'n pieni lause sanoo, että $2^6 \equiv 1 \pmod{7}$, mutta $2^3 \equiv 1 \pmod{7}$.

Kokonaisluvuille modulo $p$ määritellään usein ns. aste tai kertaluku: olkoon $ord_p(a)$ pienin positiivinen kokonaisluku $e$, jolla $a^e \equiv 1 \pmod{p}$, kun $a \not\equiv 0 \pmod{p}$. Tunnetusti jos $a^x \equiv 1 \pmod{p}$, niin $ord_p(a) \mid x$.

Voimme yleistää asteen määritelmää yleisesti äärellisille kunnille: esimerkiksi luvun $2 + \sqrt{3}$ asteeksi tulisi $8$ kunnassa $\mathbb{F}_{7}(\sqrt{3})$. Huomaamme, että tämä aste jakaa luvun $48$, jonka Fermat'n pienen lauseen yleistys antaa, kuten kuuluukin.

Hyvä tuuri, että luvun $2 + \sqrt{3}$ aste oli niinkin pieni kuin $8$ - muuten manuaalista laskemista olisi tullut paljon enemmän!


###Huomautus (kuntien isomorfisuus)

Puhumme todistuksessa kunnasta $\mathbb{F}_7(\sqrt{3})$. Tämä on hieman epätyypillistä: kuten yllä huomautettiin, äärelliset kunnat, joiden koot ovat samat, ovat isomorfisia. Yleensä siis kirjoitettaisiin vain $\mathbb{F}_{49}$.

Esimerkki isomorfisuudesta: $5$ ei ole neliönjäännös modulo $7$, joten kunnan $\mathbb{F}_7(\sqrt{5})$ koko on $49$, ja sen tulisi olla isomorfinen kunnan $\mathbb{F}_7(\sqrt{3})$ kanssa. Näin onkin: olkoon $f$ funktio, jolla $f(a + b\sqrt{3}) = a + 3b\sqrt{5}$. On helppoa varmistaa, että tämä on isomorfismi - tarkistetaan vaikein ehto eli multiplikatiivisuus $f(xy) = f(x)f(y)$:

$$f\Big((a+b\sqrt{3})(c + d\sqrt{3})\Big) = f\Big((ac + 3bd) + (ad + bc)\sqrt{3} \Big) =  ac + 3bd + 3(ad + bc)\sqrt{5}$$

ja

$$f(a+b\sqrt{3})f(c+d\sqrt{3}) = (a + 3b\sqrt{5})(c + 3d\sqrt{5}) = (ac + 3bd) + 3(ad + bc)\sqrt{5}.$$

###Huomautus (alkeellinen ratkaisu)

Pellin yhtälön ratkaisuille on olemassa myös yksinkertainen rekursio: jos yhtälön $x^2 - Dy^2 = 1$ pienin (positiivinen) ratkaisu on $(x_1, y_1)$, niin $n+1$:nneksi pienin (positiivinen) ratkaisu saadaan rekursioilla

$$x_{n+1} = x_nx_0 + Dy_ny_0$$

ja

$$y_{n+1} = x_ny_0 + y_nx_0.$$

Modulotarkastelun voi siis tehdä myös tätäkin kautta, eikä kuntalaajennuksia tarvita. Huomaa, että rekursioyhtälöt muistuttavat kertolaskua

$$(a + b\sqrt{D})(c + d\sqrt{D}) = (ac + Dbd) + (ad + bc)\sqrt{D}.$$

Siis $x_n$ vastaa kokonaislukuosaa ja $y_n$ vastaa $\sqrt{D}$-osaa.

Loppukädessä alkeellinen ratkaisu ja kuntalaajennusratkaisu vastaavat samaa asiaa, mutta eri tavalla muotoiltuna. Kuntalaajennusratkaisu esitettiinkin pääasiallisesti pedagogisista syistä.

###Yhteenveto

Äärelliset ja äärettömät kunnat siis toimivat hyvinkin samalla tavalla, ja toisessa ympäristössä toimivia ideoita voidaan usein käyttää toisessa. Lauseen 1 lemma 4 on tämän vuoksi hyvin luonnollinen.

Esitetään vielä toinen esimerkkitehtävä samassa hengessä.

## Esimerkkitehtävä

Lopuksi otan vielä yhden esimerkin.

**[Saksan joukkuevalintakoe 3, 2009, T2](https://artofproblemsolving.com/community/u328030h289403p11502215)**

Olkoon lukujono $a_1, a_2, \ldots$ määritelty asettamalla $a_1 = 1$ ja $a_{n+1} = a_n^4 - a_n^3 + 2a_n^2 + 1$ kaikilla $n \ge 1$. Osoita, että on olemassa äärettömän monta alkulukua, jotka eivät jaa mitään tämän lukujonon termiä.

**Ratkaisu (tai sen yritys)**

Ratkaisuni ei ole täysin toimiva. Tämä ei silti tarkoita, etteikö ratkaisusta voisi oppia jotain.

Olkoon $P(x) = x^4 - x^3 + 2x^2 + 1$. Osoitetaan, että on olemassa äärettömän monta $p$, jotka eivät ole $P$:n alkutekijöitä, mikä todistaa väitteen. En tiedä tälle mitään kovin yksinkertaista tapaa - yksi olisi todistaa Frobeniuksen lauseella, että vastaava väite pätee kaikille neljännen asteen polynomeille (lukujen $\lbrace 1, 2, 3, 4 \rbrace$ permutaatioita on vain $24$, ja osaryhmiä ei järkyttävän paljoa). Lähestymme ongelmaa kuitenkin toisella tavalla:

**Idea:** Hajotetaan $P$ kahden neliön summaksi.

**Mitä tästä hyötyisi?**

Kuvitellaan vaikka, että $Q(x) = x^2 + (x^2 + x + 1)^2$ jollain $Q$. Valitaan jokin $p \equiv 3 \pmod{4}$. Tällöin $p \in S(Q) \implies a^2 + b^2 \equiv 0 \pmod{p}$ jollain $a, b$, missä siis $a = x$ ja $b = x^2 + x + 1$. Mutta on tunnettua (eikä vaikeaa osoittaa), että tästä seuraa ehdon $p \equiv 3 \pmod{4}$ nojalla $a \equiv b \equiv 0 \pmod{p}$. Siis $x \equiv x^2 + x + 1 \equiv 0 \pmod{p}$. Tämä on selvästi mahdotonta.

**Toteutus**

Yritetään siis kirjoittaa $P$ kahden neliön summana. Yksi veikkaus olisi, että $P$ on muotoa $A(x)^2 + B(x)^2$, missä $A$ on toisen asteen polynomi ja $B$ on ensimmäisen asteen polynomi. Ei ole vaikeaa nähdä, että $A$:n tulee olla muotoa $x^2 - \frac{x}{2} + c$ jollain vakiolla $c$. Tehtävä palautuu siis sellaisten vakioiden $a, b, c$ löytämiseen, joilla

$$P(x) = (x^2 - \frac{x}{2} + c)^2 + (ax + b)^2.$$

Kerrotaan kaikki auki ja verrataan eri termien kertoimia. Toisen asteen termejä vertaamalla saadaan yhtälö

$$\frac{1}{4} + 2c + a^2 = 2.$$

Ensimmäisen asteen:

$$-c + 2ab = 0.$$

Vakiot:

$$c^2 + b^2 = 1.$$

Tämä on yhtälöryhmä, joka ei ole aivan triviaali muttei ihan mahdotonkaan. En kirjoita välivaiheita tähän. Ratkaisut ovat:

$b$ on yhtälön $64x^6 - 64x^4 + 1 = 0$ ratkaisu.

$$a = -\frac{1}{16b^3},$$

$$c = -\frac{1}{8b^2}.$$

Ei siis rationaaliratkaisuja. Tämä ei kuitenkaan ole ongelma: todellisuudessa haluamme ratkoa tämän yhtälöryhmän modulo $p$, koska haluamme kirjoittaa $P$:n kahden neliön summana mod $p$. Valitaan siis jokin $p$, joka on polynomin $64x^6 - 64x^4 + 1$ alkutekijä. Tällöin $p \neq 2$, eli $a, b, c$ ovat hyvin määriteltyjä kokonaislukuja mod $p$ (eli siis kunnan $\mathbb{F}_p$ alkioita).

Näillä $p$ pätee $p \in S(P) \implies x^2 - \frac{x}{2} + c \equiv ax + b \equiv 0 \pmod{p}$ jollain kokonaisluvulla $x$, olettaen $p \equiv 3 \pmod{4}$. Ei ole vaikeaa muodostaa tästä ehto $T(b) \equiv 0 \pmod{p}$ polynomille $T$, voimmehan kirjoittaa muuttujat $x, a, c$ muuttujan $b$ avulla.

Polynomien $T$ ja $64x^6 - 64x^4 + 1$ suurin yhteinen tekijä on 1 (tämä saadaan määrittämällä $T$ ja sytin laskemisella), joten Bezout'n lemman nojalla argumentti menee läpi suurilla $p$.

Ainoa ongelma on sen takaaminen, että on olemassa äärettömän monta $p$, joilla $p \equiv 3 \pmod{4}$ ja $p$ on polynomin $64x^6 - 64x^4 + 1$ alkutekijä. En näe mitään helppoa tapaa tämän todistamiseksi (tosin tämä väite vaikuttaa pätevän, ainakin tietokoneen mukaan), minkä vuoksi ratkaisu on puutteellinen. Ratkaisu kuitenkin demonstroi keinon hyödyntää vastaavuutta äärettömien ja äärellisten kuntien välillä - ratkaistaan yhtälöryhmä rationaalilukujen laajennuksessa, josta se voidaan tuoda äärettömän moneen eri äärelliseen kuntaan $\mathbb{F}_p$.

Siirrytään sitten muihin aiheisiin.

## Karakterisointi kongruenssiehdoin

Lähtökohtana toimii seuraava kysymys:

Millä polynomeilla $P \in \mathbb{Z_*}[x]$ on olemassa kokonaisluvut $m, a_1, a_2, \ldots , a_k$, joilla pätee seuraava ehto:

$$p \in S(P) \Leftrightarrow \exists i: p \equiv a_i \pmod{m}$$

Toisin sanoen, milloin $P$:n alkutekijät voidaan esittää kongruenssiehdoin?

Esimerkiksi $P(x) = x^2 + 1$ on tällainen polynomi, koska $p \in S(P)$ joss $p$ on $1$ tai $2$ (mod $4$).

Arvind Suresh on todistanut työssään [On the Characterization of Prime Sets of Polynomials by Congruence Conditions](https://scholarship.claremont.edu/cgi/viewcontent.cgi?article=2095&context=cmc_theses), että mikäli $P$ on jaoton pääpolynomi, jonka Galois'n ryhmä on Abelin ryhmä, niin tämä toteutuu. Keskitytään tähän hieman tarkemmin.

**Abelin ryhmä**

Ryhmää $G$ sanotaan Abelin ryhmäksi, jos $ab = ba$ kaikilla $a, b \in G$.

Näitä ryhmiä voisi kutsua myös kommutatiivisiksi ryhmiksi, koska mainittu ehto on kommutatiivisuus. Jostain syystä Abelin ryhmä on se termi, jota käytetään kaikkialla. Ainakin se on lyhyempi.

**Galois'n ryhmät Abelin ryhminä**

Aiemmista esimerkeistä on selvää, että $x^2 - 2$:n Galois'n ryhmä on Abelin ryhmä. Polynomin $x^3 - 2$ Galois'n ryhmä ei kuitenkaan ole Abelin ryhmä:

Polynomin $P(x) = x^3 - 2$ juurikunta on $\mathbb{Q}(\sqrt[3]{2}, \omega)$, missä $\omega = \zeta_3$ totetuttaa yhtälön $\omega^2 + \omega + 1 = 0$. Voimme esittää $P$:n juuret muodossa $\sqrt[3]{2}, \sqrt[3]{2}\omega, \sqrt[3]{2}\omega^2$.

Mitä $P$:n Galois'n ryhmä sisältää? Tätä käsiteltiin edellisessä postauksessa yleisemmin polynomeille muotoa $x^n - a$. Tässä tapauksessa on kuusi eri vaihtoehtoa. Ensinnäkin, luku $\sqrt[3]{2}$ voidaan kuvata mille tahansa juurelle $\sqrt[3]{2}\omega^i$, missä $i = 0, 1, 2$. Lisäksi $\omega$ voidaan kuvata joko itselleen tai yhtälön $x^2 + x + 1 = 0$ toiselle juurelle, joka on $\omega$:n kompleksikonjugaatti $\overline \omega$.

Eli siis: $P$:n Galois'n ryhmä vastaa kaikkia joukon $\lbrace 1, 2, 3 \rbrace$ permutaatioita.

Permutaatioryhmät eivät yleisesti ole Abelin ryhmiä. Esimerkki: olkoon $\sigma_1$ permutaatio, jolla $\sigma_1(1) = 2, \sigma_1(2) = 1, \sigma_1(3) = 3$, ja olkoon $\sigma_2$ permutaatio, jolla $\sigma_2(1) = 2, \sigma_2(2) = 3, \sigma_2(3) = 1$. Muodostetaan permutaatiot $\sigma_3$ ja $\sigma_4$ asettamalla $\sigma_3(x) = \sigma_1(\sigma_2(x))$ ja $\sigma_4(x) = \sigma_2(\sigma_1(x))$. (Huomaa siis, että permutaatioryhmien laskutoimitus on "composition", eli suoritetaan permutaatiot peräkkäin). Osoittautuu, että $\sigma_3 \neq \sigma_4$. Nimittäin,

$$\sigma_3(1) = \sigma_1(\sigma_2(1)) = \sigma_1(2) = 1$$

ja

$$\sigma_4(1) = \sigma_2(\sigma_1(1)) = \sigma_2(2) = 3.$$

Kaikkien polynomien Galois'n ryhmät eivät siis ole Abelin ryhmiä.

Sureshin tulos toimii myös muille kuin pääpolynomeille lemman 8 nojalla. Väite yleistyy myös muille kuin jaottomille polynomeille - relevantti lähde tähän löytyy [täältä](https://math.stackexchange.com/questions/126771/proof-subextension-of-abelian-extension-is-also-abelian).

Hyvin mielenkiintoinen kysymys on seuraava, jonka Suresh on esittänyt jatkotutkimusaiheena:

Oletetaan, että $P$:n alkutekijät voidaan esittää kongruenssiehdoilla. Onko $P$:n Galois'n ryhmä Abelin ryhmä?

Jos tutkielman aiheet kiinnostavat vielä tämän postaussarjan jälkeenkin, suosittelen vahvasti lukemaan Sureshin työn. Kappale 1 esittelee yleisesti polynomien alkutekijöitä, ja ratkaisee toisen asteen polynomin tapauksen. Kappaleessa 2 esitetään kohtuullisen nopeasti mutta hyvin selkeästi tärkeimpiä asioita polynomien alkutekijöiden kytköksistä syvällisempään teoriaan. Kappaleessa 3 osoitetaan työn päätulos. Sureshin työ on erinomainen lähde, jos on kiinnostunut lukemaan syvemmin algebrallisesta lukuteoriasta. Toinen, aloittelevalle ehkäpä helpompi, materiaali on Evan Chenin [Napkin-materiaalin](http://web.evanchen.cc/napkin.html) algebrallista lukuteoriaa käsittelevät luvut.


##Jatkotutkimusaihe: eksponenttiyhtälöt

Luonnollinen jatkotutkimusaihe on siirtyä polynomiyhtälöistä eksponenttiyhtälöihin. Mitä voidaan sanoa niistä alkuluvuista $p$, joilla yhtälöllä

$$2^x \equiv 3 \pmod{p}$$

on ratkaisu?

Eksponentiaalisiin rakenteisiin liittyen tunnetuin konjektuuri on Artinin primitiivijuurikonjektuuri:

**Konjektuuri**

Olkoon $a$ kokonaisluku, jonka itseisarvo on suurempaa kuin $1$, ja joka ei ole neliöluku. On olemassa äärettömän monta alkulukua $p$, joilla $a$ on primitiivijuuri modulo $p$.

Ehkä hieman yllättäen, tämä väite todella on konjektuuri eikä lause.

Aivan loistava materiaali eksponentiaalisista rakenteista on Pieter Mooren teksti [Artin's primitive root conjecture](http://guests.mpim-bonn.mpg.de/moree/surva.pdf). Kyseessä on survey-tyyppinen materiaali, eli Moore on esitellyt hyvin laajasti nykyistä kirjallisuutta aiheeseen liittyen.

Erityisesti yhtälöitä $a^x \equiv b \pmod{p}$ varten hyvä materiaali edellisen lisäksi on Pieter Mooren ja Peter Stevenhagenin artikkeli [A Two-Variable Artin Conjecture](https://core.ac.uk/download/pdf/81106660.pdf).

Tulen itse työstämään ainakin jonkin verran eksponentiaalisiin rakenteisiin liittyviä ajatuksia lähiaikoina.
