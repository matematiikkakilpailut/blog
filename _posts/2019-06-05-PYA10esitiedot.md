---
layout: post
author: "Olli Järviniemi"
title: "Polynomien yhteiset alkutekijät, osa 2: esitiedot"
math: true
excerpt_separator: "<!--jatkuu-->"

---

Tässä postauksessa esitetään tutkielman kannalta tärkeitä esitietoja sekä notaatioita.

<!--jatkuu-->

**Sisällysluettelo**


1. [Osa 1 - johdanto](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA11johdanto.html)
2. Osa 2 - esitiedot
3. [Osa 3 - tulokset](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA09tulokset.html)
4. [Osa 4 - motivaatio](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA08motivaatio.html)
5. [Osa 5 - heikko versio](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA07heikko.html)
6. [Osa 6 - yleinen tapaus](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA06yleinen.html)
7. [Osa 7 - lause 2](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA05lause2.html)
8. [Osa 8 - lause 3](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA04lause3.html)
9. [Osa 9 - lause 4](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA03lause4.html)
10. [Osa 10 - sovelluksia](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA02sovelluksia.html)
11. [Osa 11 - lisäaiheita](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA01lisaaiheita.html)

Tämä on postaussarjan vaikein postaus, koska uusia asioita tulee paljon. Samalla postaus on hyvin pitkä, koska olen koittanut avata sisältöä esimerkkien kautta. Kannattaa edetä rauhassa. Netistä löytää helposti oheismateriaalia, joiden kautta voi etsiä lisäselitystä epäselviin kohtiini. Kaikkia esitietoja ei tulla käyttämään ihan heti, joten niihin voi olla hyvä palata myöhemmin.

# Perusjuttuja

**Notaatio**

Muuttujalla $p$ viitataan **aina** alkulukuun. Muuttujat $n, m, k$ viittaavat kokonaislukuihin, useimmiten positiivisiin kokonaislukuihin.

Kokonaislukukertoimisten polynomien joukkoa merkitään $\mathbb{Z}[x]$. Ei-vakioita kokonaislukukertoimia polynomeja merkitään $\mathbb{Z_c}[x]$ (tämä notaatio siksi, että vakiopolynomit eivät ole mielenkiintoisia).

Polynomin $P$ **alkutekijöiksi** kutsutaan niitä $p$, joilla yhtälöllä $P(x) \equiv 0 \pmod{p}$. $P$:n alkutekijöiden joukkoa merkitään notaatiolla $S(P)$. Yleisesti sanotaan, että $m \in \mathbb{Z_+}$ on $P$:n tekijä, jos yhtälöllä $P(x) \equiv 0 \pmod{m}$ on ratkaisu. Tekijöiden joukkoa merkitään $S_d(P)$. Vielä kolmas määritelmä: $p$:tä kutsutaan $P$:n **vahvaksi alkutekijäksi**, jos $p^k \in S_d(P)$ kaikilla $k \in \mathbb{Z_+}$. Vahvojen alkutekijöiden joukkoa merkitään $S_v(P)$. Ei ole ilmeistä, että vahvoja alkutekijöitä on olemassa, mutta **kaikki paitsi äärellisen moni alkutekijä on vahva alkutekijä**. Tämä ei ole triviaalia, ja tähän palataan myöhemmin itse todistuksessa.

Olkoot $S_1, S_2 \subset \mathbb{Z_+}$. Kirjoitetaan, että $S_1 \approx S_2$, ja sanotaan, että joukot $S_1$ ja $S_2$ ovat miltei samat, jos seuraava ehto pätee: on olemassa vain äärellisen monta alkulukua $p$, joita kohden on olemassa $k \in \mathbb{Z_+}$, jolla $p^k$ kuuluu vain toiseen joukoista $S_1, S_2$. Määritelmä voi tuntua tässä kohtaa oudolta. Määritelmän hyödyllisyys perustuu siihen, että joukon $S_d(P)$ alkiot määräytyvät joukon $S_d(P)$ niiden alkioiden perusteella, jotka ovat alkulukujen potensseja (tarkempi kuvaus myöhemmin), joten määritelmä antaa kätevän tavan verrata tällaisia joukkoja.

**Polynomit kongruensseissa**

Muistutetaan, että jos $a \equiv b \pmod{m}$, niin $P(a) \equiv P(b) \pmod{m}$ kaikilla $P \in \mathbb{Z}[x]$. Tätä tulosta tullaan käyttämään ilman, että sitä erikseen mainitaan. Tämä tulos on myös hyvin oleellinen kilpailumatematiikassa.

**Tekijöihinjako**

[On tunnettua](https://math.dartmouth.edu/archive/m31w05/public_html/Q-Z-Reducibility.pdf), että jos $P \in \mathbb{Z}[x]$ jakautuu rationaalilukukertoimisten polynomien tuloksi, niin se jakautuu myös kokonaislukukertoimisten polynomien tuloksi. Siispä kun työssä jaetaan jotain $P \in \mathbb{Z}[x]$ tekijöihin, valitaan tekijät kokonaislukukertoimisiksi.

**Laajennettu jaollisuus**

Työssä käytetään paikoittain jaollisuutta rationaaliluvuille. Tästä voi lukea tarkemmin [tästä postauksesta](https://blog.matematiikkakilpailut.fi/2018/11/09/Jaollisuus.html). Tässä on kyse enemmänkin yksinkertaisuudesta ja intuitiosta kuin siitä, että tällä saavutettaisiin mitään konkreettista. Esimerkiksi polynomi $P(x) = \frac{1}{2}x^2 - 1$ käyttäytyy työn kannalta käytännössä katsoen täsmälleen samalla tavalla kuin polynomi $2P(x) = x^2 - 2$. Yleisesti voitaisiin siis kertoa kaikki rationaalilukuja kertovat lausekkeet sopivalla kokonaisluvulla. Tätä ideaa käytetään vain parissa kohdassa, ja mainitsen siitä erikseen.

**Tiheys**

Aiemmin puhuttiin osuuksista: kysymyksenä 3 oli, kuinka suuri osuus alkuluvuista ovat polynomin $P$ alkutekijöitä. Määritellään tämä eksaktisti:

Olkoon $\mathbb{P}$ alkulukujen joukko, ja olkoon $S$ jokin sen osajoukko. Olkoon $S(x)$ joukon $S$ niiden alkioiden määrä, jotka ovat enintään $x$. Alkulukujen joukolle vastaavaa suuretta merkitään perinteisesti $\pi(x)$, eli $\pi(x)$ on niiden alkulukujen määrä, jotka ovat enintään $x$. Joukon $S$ luonnollinen **tiheys** (joukon $\mathbb{P}$ suhteen) määritellään raja-arvona

$$\lim_{x \to \infty} \frac{S(x)}{\pi(x)}$$

Tiheyttä merkitään $\delta(S)$. Huomaa, että tiheyden ei välttämättä tarvitse olla olemassa, mutta tässä työssä ei tällaisia joukkoja esiinny (keksitkö sellaisen joukon $S$, jonka tiheys ei ole olemassa?). Esimerkiksi kaikilla $P \in \mathbb{Z}[x]$ tiheys $\delta(S(P))$ on olemassa. Tämä todistetaan myöhemmin.

Tiheyksiä voidaan määritellä myös muiden joukkojen suhteen. On myös muunlaisia tiheyksiä, tunnetuin on Dirichlet'n tiheys (tätä ei tarvita tässä työssä, mutta mainitsen sen yleisen mielenkiinnon vuoksi). Tämä määritellään niin, että suhteen $\frac{S(x)}{\pi(x)}$ sijasta tutkitaankin joukon $S$ enintään $x$ olevien alkioiden käänteislukujen summaa, ja jaetaan tämä vastaavalla suureella kaikkien alkulukujen yli. Osoittautuu, että jos luonnollinen tiheys $\delta(S)$ on olemassa, niin myös Dirichlet'n tiheys on, ja nämä tiheydet ovat samat. Dirichlet'n tiheys voi olla olemassa myös silloin kun $\delta(S)$ ei ole, joten Dirichlet'n tiheyttä voidaan ajatella luonnollisen tiheyden yleistyksenä.

# Kovempi kama

Seuraavaksi ne asiat, joita moni lukija ei varmaankaan ole aiemmin nähnyt, mutta toivottavasti oppii tämän ja mahdollisesti muiden materiaalien kautta. Tämän osion asiat ovat se, mihin aiemmin viitattiin korkeammalla matematiikalla. Vastedes viittaan tämäntyyppisiin asioihin käsitteellä algebrallinen lukuteoria, vaikka tämä ei olekaan aivan korrektia.

Ennen teoriaa haluan mainita, että vaikka määritelmissä on monessa kohtaa rationaalilukuja $\mathbb{Q}$, voi määritelmät laajentaa vastaavasti myös muille kunnille. Kunnan määritelmän voi lukea vaikkapa [täältä](https://blog.matematiikkakilpailut.fi/2018/09/02/Algebralliset.html).

Lukua $\alpha$ kutsutaan **algebralliseksi luvuksi**, jos on olemassa sellainen polynomi $P \in \mathbb{Z_c}[x]$, jonka nollakohta se on. Usein algebrallisia lukuja merkitään kirjaimin $\alpha, \beta, \gamma, \ldots$, ja niin tehdään myös näissä blogipostauksissa.

### Minimaalinen polynomi

Jokaiselle algebralliselle luvulle $\alpha$ määritellään ns. **minimaalinen polynomi** $P \in \mathbb{Q}[x]$ olemaan se polynomi, joka toteuttaa seuraavat ehdot:

1. $P$:n korkeimman asteen termin kerroin on $1$. Englanniksi termi tällaiselle polynomille on "monic polynomial". Ilmeisesti suomennos tälle termille on "pääpolynomi".

2. $P(\alpha) = 0$.

3. $P$ on ehdon 2 täyttävistä polynomeista asteiltaan pienin, kun nollapolynomia ei huomioida.

Minimaalisella polynomilla pätee seuraava ominaisuus: jos $Q(\alpha) = 0$ jollain $\mathbb{Q}(\alpha)$, niin $P \mid Q$. Tämä jätetään harjoitustehtäväksi, vinkkinä mainittaan polynomien jakoyhtälö. **Fakta on erittäin tärkeä, ja sitä tullaan käyttämään myöhemmin.**

Esimerkiksi siis luvun $\sqrt{2}$ minimaalinen polynomi on $x^2 - 2$, ja luvun $\frac{\sqrt{2}}{100}$ minimaalinen polynomi on $x^2 - \frac{2}{100^2}$.

### Kuntalaajennus

Olkoon $\alpha$ jokin algebrallinen luku. Olkoon $K$ niiden lukujen joukko, jotka ovat muotoa $P(\alpha)$, missä $P$ käy läpi kaikki rationaalilukukertoimiset polynomit. $K$ on kunta, ja sitä merkitään notaatiolla $\mathbb{Q}(\alpha)$. Tätä kutsutaan kuntalaajennukseksi.

(Mitä tarkalleen kutsutaan kuntalaajennukseksi? Kuntalaajennus on kaksi kuntaa $A, B$, joilla pätee $A \subset B$, ja $A$:n laskutoimitukset ovat samat kuin $B$:n.)

**Esimerkki**

Jos $\alpha = \sqrt{2}$, on $K = \mathbb{Q}(\sqrt{2})$ luvut muotoa $a + b\sqrt{2}$, missä $a, b \in \mathbb{Q}$. On selvää, että tämä on yhteen- ja kertolaskun suhteen suljettu joukko. Ainoa arvelluttava asia on kunnan erityisominaisuus eli käänteisalkion olemassaolo. Tässä erikoistapauksessa ominaisuus on helppo tarkistaa: luvun $a + b\sqrt{2} \neq 0$ käänteisluvuksi käy

$$\frac{1}{a + b\sqrt{2}} = \frac{a - b\sqrt{2}}{(a + b\sqrt{2})(a - b\sqrt{2})} = \frac{a - b\sqrt{2}}{a^2 - 2b^2}  = \frac{a}{a^2 - 2b^2} + \frac{-b}{a^2 - 2b^2}\sqrt{2}\in \mathbb{Q}(\sqrt{2})$$

Kyseessä siis todella on kunta.

**Perustelu yleiselle tapaukselle**

Olkoon $K'$ niiden lukujen joukko, jotka ovat muotoa $q_0 + q_1\alpha + q_2\alpha^2 + \ldots + q_{n-1}\alpha^{n-1}$, missä $q_i$ ovat rationaalilukuja ja $n$ on luvun $\alpha$ minimaalisen polynomin aste. Toisin sanoen, $K'$ sisältää luvut muotoa $Q(\alpha)$, missä $\deg(Q) < n$. Osoitetaan ensin, että $K' = K$. Tämä on varsin tärkeää muistaa myös jatkossa, koska se helpottaa ajattelua.

Valitaan jokin joukon $K$ alkio, olkoon se $T(\alpha)$, missä $T \in \mathbb{Q}[x]$. Olkoon $P$ luvun $\alpha$ minimaalinen polynomi. Polynomien jakoyhtälöllä saadaan $T(x) = P(x)Q(x) + R(x)$ jollain sopivilla $Q, R \in \mathbb{Q}[x]$, joilla $\deg(R) < \deg(P)$. Siis $T(\alpha) = R(\alpha)$, eli $T(\alpha) = R(\alpha) \in K'$. Siis kaikki $K$:n alkiot ovat $K'$:n alkioita, joten $K$ on $K'$:n osajoukko. Mutta on triviaalia, että $K'$ on $K$:n osajoukko, joten $K = K'$.

Ehkä havainnollistavampi ja minulle mieluisampi tapa edellisen väitteen perustelulle on seuraava: olkoon $\alpha$ vaikkapa polynomin $P(x) = x^3 - x - 1$ juuri. Tällöin

$$\alpha^3 = \alpha + 1 \in K'$$

$$\alpha^4 = \alpha \cdot \alpha^3 = \alpha (\alpha + 1) = \alpha^2 + \alpha \in K'$$

$$\alpha^5 = \alpha \cdot \alpha^4 = \alpha (\alpha^2 + \alpha) = \alpha^3 + \alpha^2 = (\alpha + 1) + \alpha^2 = \alpha^2 + \alpha + 1 \in K'$$

$$\ldots$$


Ideana siis, että luku $\alpha^m$ voidaan aina esittää pienempien $\alpha$:n potenssien avulla redusoimalla potenssia annetun minimaalisen polynomin avulla. Jos kaikki luvut muotoa $\alpha^n, n \in \mathbb{N}$ kuuluvat joukkoon $K'$, niin varmasti $K = K'$.

On selvää, että $K$ on kertolaskun suhteen suljettu joukko: kahden polynomin tulo on polynomi. Koska $K = K'$, on myös $K'$ kertolaskun suhteen suljettu. Tämän voi myös ajatella niin, että kahden $K'$:n alkion tulo on polynomi $\alpha$:sta, jonka korkeat $\alpha$:n potenssit voidaan redusoida yllä kuvaillulla tavalla.

Tämä siis osoittaa, että $K$ on rengas. Mutta miksi se on kunta, eli miksi käänteisalkio on aina olemassa? En tiedä tälle yksinkertaista todistusta, minkä vuoksi perustelu tässä jää puutteelliseksi. Annan kuitenkin heuristisen perustelun ja teen tästä formaalin käyttäen ns. dimensiolausetta, mutta koska tämä ei oikein liity itse työhön, on tämä perustelu lykätty tämän postauksen loppuun.


### Kuntalaajennuksen aste

Huomautus: tätä osiota varten on hyvä lukea postaus [Algebrallisista luvuista ja vektoriavaruuksista](https://blog.matematiikkakilpailut.fi/2018/09/02/Algebralliset.html). Toisaalta, jos osaa olla välittämättä niistä kohdista mitä ei ymmärrä, ja poimii perusidean kuntalaajennuksen asteesta, niin voi pärjätä ihan hyvin.

Kuntalaajennus on siis kaksi kuntaa $A \subset B$. Kunta $B$ voidaan siis tulkita $A$-vektoriavaruutena: $B$ alkioita voidaan laskea yhteen, ja niitä voidaan kertoa $A$:n alkioilla. Olkoon tämän vektoriavaruuden kannan koko $d$. Koon $d$ ei tarvitse olla äärellinen, kuten tapauksessa $A = \mathbb{Q}$, $B = \mathbb{R}$, mutta meitä kiinnostavissa tapauksissa näin on. Tämän kuntalaajennuksen, jota merkitään $B / A$, asteeksi määritellään $d$.

Esimerkiksi jos $A = \mathbb{Q}$, $B = \mathbb{Q}(\sqrt{2})$: määritelmän mukaiseksi kannaksi kelpaa $\lbrace 1, \sqrt{2} \rbrace$, joten kuntalaajennuksen $B / A$ aste on $2$.

Kuntalaajennuksen aste käytännössä katsoen kertoo, kuinka suuri laajennus kyseessä on.

Yleisesti jos $\alpha$ on algebrallinen luku, niin kuntalaajennuksen $\mathbb{Q}(\alpha) / \mathbb{Q}$ aste on sama kuin $\alpha$:n minimaalisen polynomin aste. Tämä siksi, että kuntalaajennuksen asteen määritelmän mukaiseksi kannaksi $\mathbb{Q}$-vektoriavaruudelle $\mathbb{Q}(\alpha)$ voidaan valita joukko $S = \lbrace 1, \alpha, \alpha^2, \ldots , \alpha^{d-1} \rbrace$, missä $d$ on luvun $\alpha$ minimaalisen polynomin aste. Tämä on melko ilmeistä, mutta perustelen sen kuitenkin:

Joukon $S$ alkiot selvästi virittävät, edellisen osion merkintöjä käyttäen, joukon $K'$. Mutta koska $K' = K = \mathbb{Q}(\alpha)$, virittää joukko $S$ vektoriavaruuden $B = \mathbb{Q}(\alpha)$. Lisäksi $S$:n alkiot ovat keskenään lineaarisesti riippumattomia. Tämän osoittaminen jätetään harjoitustehtäväksi, vinkkinä vastaoletus ja minimaalisen polynomin määritelmä.

Mainitaan vielä uudestaan tärkein asia:

**Kuntalaajennuksen $\mathbb{Q}(\alpha) / \mathbb{Q}$ aste on luvun $\alpha$ minimaalisen polynomin aste.**

Kuntalaajennuksen $B / A$ astetta merkitään $[B : A]$.

### Kuntalaajennusten asteiden multiplikatiivisuus

Olkoot $A \subset B \subset C$ kuntia. Kuntalaajennusten asteille pätee seuraava kaava:

$$[C : A] = [C : B][B : A]$$

En todista väitettä tässä, vaikka todistus ei vaadikaan mitään kovin ihmeellistä. Tätä multiplikatiivista ominaisuutta ei käytetä itse päätuloksen todistuksessa, mutta sitä käytetään muiden tulosten osoittamisessa. Se ei siis ole aivan kriittisessä roolissa.

Kaava käytännössä kertoo, että $C$:n koko $A$:han verrattuna saadaan tutkimalla $C$:n kokoa $B$:hen verrattuna, ja $B$:n kokoa $A$:han verrattuna. Varsin intuitiivista.

Otetaan tästä vielä esimerkki, joka demonstroi samalla kahta peräkkäistä kuntalaajennusta.

**Esimerkki**

Olkoot $A = \mathbb{Q}$, $B = \mathbb{Q}(\sqrt{2})$, ja $C = B(\sqrt{3})$. Periaate kuntalaajennukselle $C / B$ toimii kuten rationaalilukujen tapauksessa:

1. Määritetään luvun $\sqrt{3}$ minimaalinen polynomi kunnassa $B$. eli se polynomi $P \in B[x]$, jolla $P(\sqrt{3}) = 0$, $P$ on pääpolynomi, ja $P$:n aste on minimaalinen. Ei ole vaikeaa todistaa, että $P$ ei voi olla ensimmäisen asteen polynomi. Siispä sen aste on vähintään 2, joten polynomi $P(x) = x^2 - 3$ on minimaalinen polynomi. Tässä tapauksessa minimaalinen polynomi kunnassa $B$ on sama kuin rationaaliluvuissa $\mathbb{Q}$, mutta aina näin ei ole.

2. $C$ voidaan ajatella $B$-vektoriavaruutena, jonka kanta on $\lbrace 1, \sqrt{3} \rbrace$. Toisin sanoen, $C$ sisältää luvut muotoa $x + y\sqrt{3}$, $x, y \in B$. Tämä on analogista rationaalilukuihin verrattuna.

3. Siispä $[C : B] = 2$.

On helppoa nähdä, että $[B : A] = 2$. Kaavan nojalla tulisi päteä $[C : A] = [C : B][B : A] = 2 \cdot 2 = 4$. Osoitetaan tämä tutkimalla joukon $C$ alkioita. Kohdan 2. nojalla $C$ sisältää luvut muotoa $x + y\sqrt{3}, x, y \in B$. Toisaalta, $B$ sisältää luvut muotoa $a + b\sqrt{2}, a, b \in \mathbb{Q}$. Olkoon siis $x = a + b\sqrt{2}$, $y = c + d\sqrt{3}$. $C$:n alkiot ovat muotoa

$$x + y\sqrt{3} = a + b\sqrt{2} + (c + d\sqrt{2})\sqrt{3} = a + b\sqrt{2} + c\sqrt{3} + d\sqrt{6}$$

$C$ on $A$-vektoriavaruus, jonka kantana on $\lbrace 1, \sqrt{2}, \sqrt{3}, \sqrt{6} \rbrace$ (on selvää, että nämä luvut virittävät $C$:n, mutta ei aivan ilmeistä, että ne ovat lineaarisesti riippumattomia. Tämän osoittaminen sivuutetaan, vaikkakin se on mahdollista tehdä täysin alkeellisesti). Siis $[C : A] = 4$, kuten kuuluukin.


### Primitive element theorem

Tutkitaan edellisen esimerkin mukaista $C$. $C$ on siis se kunta, joka saadaan lisäämällä rationaalilukuihin ensiksi luku $\sqrt{2}$ ja sitten luku $\sqrt{3}$. Tämä voidaan kirjoittaa muodossa $C = \mathbb{Q}(\sqrt{2}, \sqrt{3})$. Luonnollinen kysymys on, olisiko tämän laajennuksen voinut tehdä vain yhdellä alkiolla $\gamma$? Toisin sanoen, onko olemassa sellainen $\gamma$, jolla $\mathbb{Q}(\sqrt{2}, \sqrt{3}) = \mathbb{Q}(\gamma)$?

Vastaus on kyllä, esimerkiksi valinta $\gamma = \sqrt{2} + \sqrt{3}$ toimii. Esitetään tälle nopeasti todistus.

$$\frac{1}{\gamma} = \sqrt{3} - \sqrt{2} \in \mathbb{Q}(\gamma)$$

Siispä

$$\frac{1}{2}(\gamma + \frac{1}{\gamma}) = \sqrt{3} \in \mathbb{Q}(\gamma)$$

Täten $\sqrt{3} \in \mathbb{Q}(\gamma)$, joten $\sqrt{2} \in \mathbb{Q}(\gamma)$, joten $\mathbb{Q}(\sqrt{2}, \sqrt{3}) \subset \mathbb{Q}(\gamma)$. Toisaalta pätee tietysti $\mathbb{Q}(\gamma) \subset \mathbb{Q}(\sqrt{2}, \sqrt{3})$, joten nämä kunnat ovat samat.

Päteekö tämä yleisestikin? Eli onko kaikilla algebrallisilla luvuilla $\alpha, \beta$ olemassa $\gamma$, joilla $\mathbb{Q}(\alpha, \beta) = \mathbb{Q}(\gamma)$? On olemassa. Tämä tulos tunnetaan nimellä **prmitive element theorem**.

Tämä tulos on (minun mielestäni) niin mielenkiintoinen, että sille esitetään todistus, vaikkei tämä liitykään kovin vahvasti itse työhön (tulosta toki tullaan käyttämään hyvin monessa kohtaa). Todistus on melko vaikea, mutta se antaa lisäharjoitusta kuntalaajennuksista ja minimaalisista polynomeista.

Väite yleistyy suoraviivaisesti induktiolla $n$:lle luvulle, eli laajennus $\mathbb{Q}(\alpha_1, \alpha_2, \ldots , \alpha_n)$ voidaan tehdä yhdellä alkiolla. Toisin sanoen, **kaikki rationaalilukujen (äärelliset) laajennukset ovat muotoa $\mathbb{Q}(\alpha)$.**

Väitteen todistus perustuu [Ken Brownin luentomateriaaliin](http://pi.math.cornell.edu/~kbrown/6310/primitive.pdf).

### Todistus (Primitive element theorem)

Olkoot $\alpha, \beta$ algebrallisia lukuja, ja olkoot $f, g \in \mathbb{Q}[x]$ niiden minimaaliset polynomit. Olkoon $\gamma = \alpha + \lambda\beta$, missä $\lambda \in \mathbb{Q}$ on myöhemmin valittava vakio. Tulemme valitsemaan luvun $\lambda$ niin, että $\mathbb{Q}(\alpha, \beta) = \mathbb{Q}(\gamma)$.

Olkoon $g_{\gamma}$ luvun $\beta$ minimaalinen polynomi kunnassa $\mathbb{Q}(\gamma)$. Aiomme osoittaa, että $\deg(g_{\gamma}) = 1$. Tämä todistaa väitteen, koska silloin on olemassa $a, b \in \mathbb{Q}(\gamma)$, joilla $g_{\gamma}(x) = ax + b$, eli $0 = g_{\gamma}(\beta) = a\beta + b$, eli $\beta = -\frac{b}{a}$. Tällöin $\beta \in \mathbb{Q}(\gamma)$, eli myös $\alpha = \gamma - \lambda\beta \in \mathbb{Q}(\gamma)$.

**Idea:** Etsitään kaksi polynomia, jotka $g_{\gamma}$ jakaa. Osoitetaan, että näiden polynomien syt on 1.

Koska $g \in \mathbb{Q}[x]$, ovat $g$:n kertoimet rationaalilukuja ja täten kunnan $\mathbb{Q}(\gamma)$ alkioita. Voidaan siis kirjoittaa, hieman erikoisesti mutta hyödyllisesti, $g \in \mathbb{Q}(\gamma)[x]$. Lisäksi määritelmän nojalla $g(\beta) = 0$. $g$ on siis polynomi, jonka kertoimet ovat kunnassa $\mathbb{Q}(\gamma)$, ja jolla on nollakohta $\beta$. Sen siis tulee olla jaollinen luvun $\beta$ minimaalisella polynomilla kunnassa $\mathbb{Q}(\gamma)$, eli polynomilla $g_{\gamma}$. Tämä saattaa tuntua hämmentävältä, joten esitetään tämä vielä toisella tavalla:

Jaetaan polynomi $g \in \mathbb{Q}(\gamma)[x]$ polynomilla $g_{\gamma} \in \mathbb{Q}(\gamma)[x]$ jakokulmassa. Siis $g = g_{\gamma}A + B$, missä $\deg(B) < \deg(g_{\gamma})$, $B \in \mathbb{Q}(\gamma)[x]$. Sijoittamalla muuttujaksi $\beta$ saadaan $g(\beta) = g_{\gamma}(\beta)A(\beta) + B(\beta)$. Koska $g(\beta) = 0 = g_{\gamma}(\beta)$, pätee $B(\beta) = 0$. Mutta $g_{\gamma}$ määriteltiin olemaan luvun $\beta$ minimaalinen polynomi, ja pätee $\deg(B) < \deg(g')$. Tämä on määritelmien nojalla mahdollista vain, jos $B$ on nollapolynomi, eli $g_{\gamma} \mid g$.

Siis

$$g_{\gamma} \mid g.$$

Etsitään sitten, idean mukaisesti, vielä toinen polynomi $h$, jolla pätee $g_{\gamma} \mid h$. Tämä $h$ valitaan asettamalla $h(x) = f(\gamma - \lambda x)$. Tällöin $h(\beta) = f(\alpha) = 0$, ja $h \in \mathbb{Q}(\gamma)[x]$. Kuten edellä, tulee myös $h$:n olla jaollinen polynomilla $g_{\gamma}$. Siis

$$g_{\gamma} \mid h.$$

Osoittaaksemme $\deg(g_{\gamma}) = 1$ riittää siis osoittaa, että polynomien $g$ ja $h$ suurimman yhteisen tekijän aste on $1$ (huomaa, että tiedämme sytin asteen olevan vähintään $1$, koska $g(\beta) = h(\beta) = 0$). Osoitetaan tämä vastaoletuksella: polynomien $g$ ja $h$ suurimman yhteisen tekijän aste on vähintään $2$.

Tällöin on olemassa jokin algebrallinen luku $\beta'$, jolla $g(\beta') = h(\beta') = 0$. Osoitetaan, että $\beta' \neq \beta$, eli siis että $\beta$ ei ole $g$:n kaksinkertainen juuri, minkä jälkeen saatetaan todistus maaliin.

Oletetaan, että $\beta$ on $g$:n kaksinkertainen juuri. $g$ on rationaaliluvuissa jaoton (onhan se luvun $\beta$ minimaalinen polynomi). Mutta jos $\beta$ olisi $g$:n kaksinkertainen juuri, voitaisiin kirjoittaa $g(x) = (x - \beta)^2q(x)$ jollain polynomilla $q$. Derivoimalla ja sijoittamalla $x = \beta$ saadaan $g'(\beta) = 0$. Tämä on kuitenkin ristiriidassa sen kanssa, että $g$ on luvun $\beta$ minimaalinen polynomi.

On siis olemassa sellainen $\beta' \neq \beta$, joka on polynomien $g$ ja $h$ yhteinen nollakohta. Siis $h(\beta') = 0$. Polynomin $h$ määritelmän nojalla pätee $h(\beta') = f(\gamma - \lambda\beta')$. Kirjoitetaan $\alpha' = \gamma - \lambda\beta'$. Tällöin

$$\alpha' = \gamma - \lambda\beta' = \alpha + \lambda\beta - \lambda\beta' = \alpha + \lambda(\beta - \beta')$$

Täten

$$\lambda = \frac{\alpha' - \alpha}{\beta - \beta'}$$

Tässä yhtälössä $\alpha', \beta'$ ovat polynomien $f$ ja $g$ juuria, joten niille on vain äärellisen monta eri vaihtoehtoa. Siis jos $\lambda$ ei ole muotoa

$$\frac{\alpha' - \alpha}{\beta - \beta'}$$

olemme saaneet ristiriidan. Tämä todistaa väitteen.

**Siis kaikki paitsi äärellisen moni $\lambda$ kelpaa.**

Lopuksi vielä aiemmin luvattu perustelu sille, että $\mathbb{Q}(\alpha)$ on näillä määritelmillä kunta.

### Perustelu sille, että $\mathbb{Q}(\alpha)$ on kunta

Olkoon $d$ luvun $\alpha$ minimaalisen polynomin aste kunnan $\mathbb{Q}$ yli. Olkoon $R \in \mathbb{Q}[x]$ jokin polynomi, jolla $R(\alpha) \neq 0$. Tavoitteena on löytää sellainen polynomi $Q \in \mathbb{Q}[x]$, jolla $\frac{1}{R(\alpha)} = Q(\alpha)$. Toisin sanoen, $1 = R(\alpha)Q(\alpha)$.

Olkoon $K'$ kuten aiemmin, eli $\mathbb{Q}$-vektoriavaruus, jonka kanta on $\lbrace 1, \alpha, \alpha^2, \ldots , \alpha^{d-1} \rbrace$ (eli luvut muotoa $q_0 + q_1\alpha + \ldots + q_{d-1}\alpha^{d-1}$). Määritellään kuvaus $L : K' \to K'$ asettamalla $L(x) = R(\alpha)x$. Riittää osoittaa, että $L$ on surjektio, jolloin voidaan valita sellainen $x$, jolla $L(x) = 1$. Tämä antaa halutun lopputuloksen.

Ennen tätä: olkoon $S$ jokin äärellinen joukko, ja olkoon $f : S \to S$ jokin kuvaus. Vakuuta itsesi siitä, että $f$ on injektio jos ja vain jos se on surjektio.

Ideana $L$:n todistamiseksi surjektioksi on vastaava idea: $L$ on selvästi injektio, koska se on ensimmäisen asteen polynomi. Siispä se on surjektio?

Tämä ei ihan vakuuta. Tämä implikaatio kyllä pätee, mutta se vaatii hieman teoriaa.

$L$ on ns. lineaarikuvaus: $L(x + y) = L(x) + L(y)$ kaikilla $x, y \in K'$, ja $L(ax) = aL(x)$ kaikilla rationaaliluvuilla $a$. Yleisesti vektoriavaruuksille määritellään lineaarikuvaus vastaavasti.

Lineaarikuvaksilla vektoriavaruuksilta itselleen pätee väite "$L$ on injektio jos ja vain jos se on surjektio". Tämä on erikoistapaus vahvemmasta väitteestä, niin kutsutusta dimensiolauseesta:

**Dimensiolause**

Olkoon notaatio kuten edellä. Olkoon $A$ niiden $x \in K'$ joukko, joilla $L(x) = 0$ (engl. kernel). Olkoon $B$ niiden $y \in K'$ joukko, joilla on olemassa $x \in K'$, jolla $L(x) = y$ (kuva, engl. image). $A$ ja $B$ ovat $\mathbb{Q}$-vektoriavaruuksia (helppoa todistaa). Olkoot niiden ulottuvuudet $a$ ja $b$. Määritellään $d$ olemaan $\mathbb{Q}$-vektoriavaruuden $K'$ ulottuvuus. Pätee

$$d = a + b$$

Dimensiolause siis kertoo, että mitä lähempänä injektiivisyyttä $L$ on, sitä lähempänä se on surjektiivisuutta. Erityisesti, jos $A = \lbrace 0 \rbrace$, niin $B = K'$, eli $L$ on surjektio. Tämä todistaa, että $\mathbb{Q}(\alpha)$ on kunta.

Tässä [Wikipedia-sivu](https://en.wikipedia.org/wiki/Rank%E2%80%93nullity_theorem) dimensiolauseesta.



[Seuraava postaus.](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA09tulokset.html)
