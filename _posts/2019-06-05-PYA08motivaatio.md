---
layout: post
author: "Olli Järviniemi"
title: "Polynomien yhteiset alkutekijät, osa 4: motivaatio"
math: true
excerpt_separator: "<!--jatkuu-->"

---

Tässä postauksessa esitetään motivaatio lauseen 1 todistuksen takana.

<!--jatkuu-->

**Sisällysluettelo**


1. [Osa 1 - johdanto](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA11johdanto.html)
2. [Osa 2 - esitiedot](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA10esitiedot.html)
3. [Osa 3 - tulokset](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA09tulokset.html)
4. Osa 4 - motivaatio
5. [Osa 5 - heikko versio](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA07heikko.html)
6. [Osa 6 - yleinen tapaus](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA06yleinen.html)
7. [Osa 7 - lause 2](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA05lause2.html)
8. [Osa 8 - lause 3](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA04lause3.html)
9. [Osa 9 - lause 4](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA03lause4.html)
10. [Osa 10 - sovelluksia](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA02sovelluksia.html)
11. [Osa 11 - lisäaiheita](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA01lisaaiheita.html)


## Kysymys 2

Kysymyksenä 2 oli: onko $S(A) \cap S(B)$ ääretön kaikilla $A, B \in \mathbb{Z_c}[x]$? Esitetään tälle väitteelle todistus. Todistus ei ole minun, vaan voidaan löytää esimerkiksi artikkelista [On the prime divisors of polynomials](https://www.jstor.org/stable/2317521?seq=1#page_scan_tab_contents) (Irving Grest, John Brillhart).

**Todistus**

Olkoot $\alpha, \beta$ jotkin $A$:n ja $B$:n juuret. Olkoon $\gamma$ sellainen, että $\mathbb{Q}(\alpha, \beta) = \mathbb{Q}(\gamma)$ (mahdollista Primitive element theoremin nojalla, kts. esitiedot). Olkoon $D$ luvun $\gamma$ minimaalinen polynomi. Osoitetaan, että $D$:llä on seuraava ominaisuus:

Kaikki paitsi äärellisen moni $D$:n alkutekijä on sekä $A$:n että $B$:n alkutekijä.

Huomaa, että $D$ ei ole välttämättä kokonaislukukertoiminen, mutta $D$:tä voidaan kertoa sopivalla kokonaisluvulla, eikä todistettava väite muutu. Tämä on esimerkki laajennetun jaollisuuden määritelmän kiertämisestä. Oletetaan siis, että $D$ on kokonaislukukertoiminen.

Koska $\alpha \in \mathbb{Q}(\alpha) \subset \mathbb{Q}(\alpha, \beta) = \mathbb{Q}(\gamma)$, voidaan $\alpha$ esittää polynomina luvusta $\gamma$. Siis $\alpha = q_0 + q_1\gamma + \ldots + q_{n-1}\gamma^{n-1}$ jollain rationaaliluvuilla $q_i$ ja kokonaisluvulla $n$. Olkoon $A_1(x) = q_0 + q_1x + \ldots + q_{n-1}x^{n-1}$. Tällöin

$$A(A_1(\gamma)) = A(\alpha) = 0$$

Polynomilla $A(A_1(\gamma))$ on siis juuri kohdassa $\gamma$, joten se on jaollinen luvun $\gamma$ minimaalisella polynomilla (kts. esitiedot), eli polynomilla $D$. Täten

$$D(x) \mid A(A_1(x))$$

On siis olemassa polynomi $R \in \mathbb{Q}[x]$, jolla $A(A_1(x)) = D(x)R(x)$. Nyt olemme melkein valmiit. Tutkitaan niitä $p \in S(D)$, jotka eivät jaa polynomien $A_1, R$ minkään kertoimen nimittäjää, eli siis kaikkia paitsi äärellisen montaa $S(D)$:n alkiota. Koska $p \in S(D)$, on olemassa sellainen $n \in \mathbb{Z}$, jolla $D(n) \equiv 0 \pmod{p}$.

Luku $R(n)$ on rationaaliluku, jonka nimittäjä ei ole jaollinen $p$:llä. Siispä se voidaan tulkita kokonaislukuna modulo $p$ (kts. jaollisuus rationaaliluvuissa). Siispä

$$D(n)R(n) \equiv 0 \pmod{p}$$

Mutta $D(n)R(n) = A(A_1(n))$, joten

$$A(A_1(n)) \equiv 0 \pmod{p}$$

Siis yhtälöllä $A(x) \equiv 0 \pmod{p}$ on ratkaisu $x = A_1(n)$. Ongelmaksi kuitenkin muodostuu se, että $A_1(n)$ ei välttämättä ole kokonaisluku. Mutta $A_1(n)$ on rationaaliluku, jonka nimittäjä ei ole jaollinen $p$:llä (kosta tutkimme vain niitä $p$, joilla $A_1$:n kertoimien nimittäjät eivät ole jaollisia $p$:llä). Siispä se voidaan tulkita kokonaislukuna modulo $p$, joten yhtälöllä $A(x) \equiv 0 \pmod{p}$ on kokonaislukuratkaisu $x$. Siispä $p \in S(A)$. Vastaavasti osoitetaan, että kaikilla paitsi äärellisen monella $p$ pätee $p \in S(D) \implies p \in S(B)$. Tämä osoittaa väitteen.


**Lukijan vakuuttaminen**

Lukijaa voi arvelluttaa edellisen todistuksen rationaalilukujen tulkitseminen kokonaislukuina. Kuten aiemmin todettiin, laajennettu jaollisuuden määritelmä voidaan poistaa todistuksista, mutta tämä muuttaa niitä hieman vaivalloiseksi. Esitän tässä ideat, joilla muunnokset voi yllä olevaan todistukseen tehdä, mutta myöhempien todistuksien yhteydessä en enää näin tee. Kannattaa siis luottaa laajennettuun määritelmään.

Muunnokset ovat tässä tapauksessa vaikeita. Usein riittää vain kertoa polynomeja joillain vakioilla, mutta tässä pitää tehdä paljon enemmän. Seuraava todistus voi tuntua hieman puuduttavalta, ja sen voi halutessaan sivuuttaa.

Olkoon $d = \deg(A)$ ja $c$ polynomin $R$ kertoimien nimittäjien tulo. Olkoon $A_1(n) = \frac{f(n)}{g(n)}$, missä murtoluku on supistetussa muodossa. Huomaa, että $g$ on rajoitettu funktio, koska $g(n)$ jakaa polynomin $A_1$ kertoimien nimittäjien tulon kaikilla $n$. Olkoon vielä $R_1(x) = cR(x)$.

Olkoon $p \nmid cg(n)$ jokin $D$:n alkutekijä, ja olkoon $D(n) \equiv 0 \pmod{p}$. Koska $g$ on rajoitettu, tarkastelemme kaikkia paitsi äärellisen montaa $D$:n alkutekijää.

**Idea:** Luku $A_1(n)$ tulkittuna kokonaislukuna modulo $p$ on vain $f(n)g(n)^{p-2}$. Osoitetaan suoraan, ilman huijauksia muotoa "tulkitaan kokonaislukuna modulo $p$", että $A(f(n)g(n)^{p-2}) \equiv 0 \pmod{p}$.

Sijoitetaan yhtälöön $A(A_1(x)) = D(x)R(x)$ arvo $x = n$.

$$A(A_1(n)) = D(n)R(n)$$

Kerrotaan molemmat puolet luvulla $cg(n)^d$. Saadaan

$$cg(n)^dA(A_1(n)) = D(n)R_1(n)g(n)^d$$

Tutkitaan vasemman puolen lauseketta. Saamme


$$cg(n)^dA(A_1(n)) = cg(n)^dA\Big( \frac{f(n)}{g(n)} \Big) = cg(n)^d\Big( a_d\frac{f(n)^d}{g(n)^d} + \ldots + a_0 \Big)$$

$$= c(a_df(n)^d + a_{d-1}f(n)^{d-1}g(n) + \ldots + a_0g(n)^d)$$

Tämä on edelleen yhtä suuri kuin $D(n)R_1(n)g(n)^d$.

 Koksa $D(n) \equiv 0 \pmod{p}$, on siis $D(n)R_1(n)g(n)^d$ jaollinen $p$:llä, ja niin on myös yllä oleva lauseke. Koska $p \nmid cg(n)$, eli erityisesti $p \nmid c$, pätee

$$a_df(n)^d + a_{d-1}f(n)^{d-1}g(n) + \ldots + a_0g(n)^d \equiv 0 \pmod{p}$$

Kerrotaan tämä puolittain luvulla $g(n)^{(p-1) - d}$. Saadaan

$$a_df(n)^dg(n)^{(p-1) - d} + a_{d-1}f(n)^{d-1}g(n)^{(p-1) - (d - 1)} + \ldots + a_0g(n)^{p-1} \equiv 0 \pmod{p}$$

Kaikilla $i$ pätee $(p-1) - (d-i) \equiv (p-2)(d-i) \pmod{p-1}$. Fermat'n pienen lauseen nojalla

$g(n)^{(p-1) - (d - i)} \equiv g(n)^{(p-2)(d - i)} \pmod{p}$ 

Siis edellinen yhtälö voidaan kirjoittaa muodossa

$$a_df(n)^dg(n)^{(p-2)d} + a_{d-1}f(n)^{d-1}g(n)^{(p-2)(d-1)} + \ldots + a_0 \equiv 0 \pmod{p}$$

Mutta yhtälön vasen puoli on vain $A(f(n)g(n)^{p-2})$. Siis $A(f(n)g(n)^{p-2}) \equiv 0 \pmod{p}$, joten $p \in S(A)$.


# Suunnitelma

Esitetään suunnitelma, jolla lause 1 todistetaan.

## Esimerkki

Matemaatikko David Hilbertille omistetaan lainaus "The art of doing mathematics is finding that special case that contains all the germs of generality.". Toimimme niin tässä.

Olkoon $A(x) = x^2 + 1$, $B(x) = x^2 - 2$. Edellisessä todistuksessa voidaan valita vaikkapa $\alpha = i$, $\beta = \sqrt{2}$, ja $\gamma = \alpha + \beta$. Tällöin luvun $\gamma$ minimaalinen polynomi on $D(x) = x^4 - 2x^2 + 9$ (minimaalisen polynomin laskeminen ei ole aivan triviaalia, eikä siihen keskitytä nyt). Todistus osoittaa, että $S(D) \subset S(A) \cap S(B)$ (poislukien äärellisen monta poikkeustapausta).

Todistuksesta tulee helposti mieleen seuraava kysymys: onko polynomeilla $A, B$ muita yhteisiä alkutekijöitä kuin $D$:n alkutekijät? Testasin konkreettisia esimerkkejä tietokoneella, ja vastaus vaikutti olevan tässä, ja monessa muussakin, tapauksessa kielteinen. Mitä tapahtuu?

Olkoot $A_1, B_1$ kuten todistuksessa. Nämä voitaisiin laskea, mutta tämä ei ole kovin kiinnostavaa eikä tarpeellista. Todistus osoittaa, että äärellisen montaa $p$ lukuun ottamatta pätee $D(n) \equiv 0 \pmod{p} \implies A(A_1(n)) \equiv B(B_1(n)) \equiv 0 \pmod{p}$. On siis olemassa polynomit $A_1, B_1$, joiden avulla $D$:n nollakohdasta (modulo $p$) voidaan generoida $A$:lle ja $B$:lle nollakohdat.

Olisi mukavaa, jos olisi olemassa sellainen kahden muuttujan polynomi, jolla $A$:n ja $B$:n nollakohdista $a, b$ (modulo $p$) voitaisiin generoida $D$:n nollakohta (modulo $p$). Helppo veikkaus tälle polynomille olisi $P(a, b) = a + b$, sama kuin mitä käytettiin $\gamma$:n generoimiseen luvuista $\alpha, \beta$. Huomaa, että sama toimi aiemmin jo toiseen suuntaan: voidaan ajatella, että $\alpha, \beta$ on generoitu luvusta $\gamma$ polynomeilla $A_1, B_1$, ja $a$ ja $b$ on generoitu luvusta $n$ polynomeilla $A_1$ ja $B_1$.

Osoitetaan siis seuraava väite:

Jos $A(a) \equiv B(b) \equiv 0 \pmod{p}$, niin $D(a+b) \equiv 0 \pmod{p}$.

Tämän voi tehdä manuaalisilla laskuilla aivan suoraan. Tarvitsemme vain tietoja $A(a) \equiv B(b) \equiv 0 \pmod{p}$, eli $a^2 \equiv -1 \pmod{p}$, $b^2 \equiv 2 \pmod{p}$.

Käytän pientä kikkaa, jolla laskut saa pidettyä melko siisteinä: olkoon $t = (a+b)^2$. Tällöin

$$t = a^2 + 2ab + b^2 \equiv -1 + 2ab + 2 \equiv 2ab + 1 \pmod{p}$$

Nyt,

$$D(a+b) = (a+b)^4 - 2(a+b)^2 + 9 = t^2 - 2t + 9 \equiv (2ab + 1)^2 - 2(2ab + 1) + 9$$

$$ \equiv 4a^2 b^2 + 4ab + 1 - (4ab + 2) + 9 \equiv 4 \cdot (-1) \cdot 2 + 8 \equiv 0 \pmod{p}$$

Kysymys kuuluu: voidaanko näin tehdä aina? Yleisessä tapauksessa tulee ongelmia, joihin keskitytään sen jälkeen, kun kerätään hieman intuitiota.

**Idea**

Luvut $a, b$ ajavat samaa asiaa modulo $p$ kuin luvut $i, \sqrt{2}$ kompleksiluvuissa. Nimittäin, $a^2 \equiv -1 \pmod{p}$, $i^2 = -1$. Vastaavasti $b^2 \equiv 2 \pmod{p}$, $\sqrt{2}^2 = 2$.

Huomaa, että täsmälleen edellisten laskujen kaltaisesti voidaan osoittaa, että $D(\alpha + \beta)$ todella on $0$. Idean mukainen vastaavuus tuntuu olevan vahva.


**Idea**

Kysymyksen 2 vastaus osoittaa siis seuraavan väitteen:

Olkoot $A, B$ jaottomia polynomeja, ja olkoot niillä juuret $\alpha, \beta$. Oletetaan, että $\mathbb{Q}(\alpha) \subset \mathbb{Q}(\beta)$. Tällöin $S(B) \subset S(A)$ (poislukien äärellisen monta $p \in S(B)$, joilla voi päteä $p \not\in S(A)$).

(Tämä tehtiin kysymyksen 2 ratkaisussa polynomeille $A$ ja $D$)

Tapauksessa $\mathbb{Q}(\alpha) = \mathbb{Q}(\beta)$ pätee siis sekä $S(B) \subset S(A)$ että $S(A) \subset S(B)$. Täten $S(A) \approx S(B)$.

Juuret siis todella kertovat alkutekijöistä, mikä omilta osin perustelee lauseen 3 ehtoa. Tämä on kantava teema, ja yksi työn tärkeimmistä ideoista: **polynomin juuret kertovat sen alkutekijöistä.** Tämä näkyy lauseiden todistuksissa, ja olen lisäksi kirjoittanut viimeiseen blogipostaukseen hieman erilaisia tapoja demonstroida tätä.

### Ongelmia

Olkoot $A(x) = (x^2 - 2)(x^2 - 3)$ ja $B(x) = x^2 - 5$. Intuitiivisesti yllä oleva menettely ei toimi (ja se oikeasti ei toimi): varmaankin on väliä, valitaanko $A$:lta juuri $\alpha = \sqrt{2}$ vai $\alpha' = \sqrt{3}$: näiden muodostamat kunnat $\mathbb{Q}(\alpha), \mathbb{Q}(\alpha')$ eivät ole samat.

Todistuksessa tulee siis ongelma, jos $A$ tai $B$ jakautuu. Kunnat $\mathbb{Q}(\alpha')$ ja $\mathbb{Q}(\alpha)$ ovat kuitenkin isomorfiset, jos $A$ ei jakaudu (esim. $A = x^2 - 2$, niin $\mathbb{Q}(\sqrt{2})$ ja $\mathbb{Q}(-\sqrt{2})$ ovat isomorfisia). Kuntia $K_1, K_2$ sanotaan isomorfisiksi, jos on olemassa funktio $f : K_1 \to K_2$, jolla on seuraavat ominaisuudet:

1. $f(xy) = f(x)f(y)$ kaikilla $x, y \in K_1$.
2. $f(x + y) = f(x) + f(y)$ kaikilla $x, y \in K_1$.
3. $f(1) = 1$.
4. $f$ on bijektio.

Isomorfisuus käytännössä tarkoittaa sitä, että kuntien rakenne on sama, mutta alkiot on vain nimetty eri tavalla.

Jaottomilla polynomeilla $A$ pätee se, että $\mathbb{Q}(\alpha)$ ja $\mathbb{Q}(\alpha')$ ovat isomorfisia, kun $\alpha, \alpha'$ ovat $A$:n juuria. Tämän takia todistuksessa ei ole väliä sillä, mikä näistä valitaan.

Intuitio sanoo, että valittuamme todistuksessa juuren $\alpha$ haluaisimme, että $\mathbb{Q}(\alpha, \beta)$ ja $\mathbb{Q}(\alpha, \beta')$ ovat isomorfisia kaikilla $B$:n juurilla $\beta, \beta'$ - emme halua, että sillä on väliä, minkä juuren $B$:ltä valitsemme.

Tämä ei kuitenkaan aina päde, vaikka $A$ ja $B$ eivät jakautuisi rationaaliluvuissa.

**Mistä ongelma johtuu?**

Ongelma esiintyy silloin, kun $B$ jakautuu kunnassa $\mathbb{Q}(\alpha)$ (aivan kuten ongelma esiintyy, jos $A$ jakautuu kunnassa $\mathbb{Q}$). Yksinkertainen esimerkki: $A(x) = x^2 - 2$, $B(x) = x^4 - 2$. Tällöin $B(x) = (x^2 - \alpha)(x^2 + \alpha)$.

**Miten tämä näkyy käytännössä?**

Olkoon $A(x) = (x^2 - 123)^2 - 2$ ja $B(x) = (x^2 - 456)^2 - 2$. Olkoon $D$ luvun $\gamma$ minimaalinen polynomi, missä $\gamma$ on kuten kysymyksen 2 ratkaisussa. Oletetaan yksinkertaisuuden vuoksi, että $\gamma$ voidaan valita olemaan muotoa $\alpha + \beta$, missä $A(\alpha) = B(\beta) = 0$ ovat joitain $A$:n ja $B$:n juuria.

Ongelmaksi tulee se, että ehdoista $A(a) \equiv B(b) \equiv 0 \pmod{p}$ ei suoraan edellisen esimerkin kaltaisten laskujen kautta saada yhtälöä $D(a+b) \equiv 0 \pmod{p}$ todistettua.

Yhtälöä $D(\alpha + \beta) = 0$ ei voi todistaa suoraan vastaavien sievennyksien kautta todeksi. Tämä johtuu siitä, että juurien $\alpha$ ja $\beta$ välillä vallitsee epätriviaali yhtälö: jos vaikkapa

$$\alpha = \sqrt{\sqrt{2} + 123}$$

ja

$$\beta = \sqrt{\sqrt{2} + 456}$$

niin pätee yhtälö

$$\alpha^2 = \beta^2 - 333$$

Jos tätä tietoa käyttää sievennyksissä apuna, argumentti menee läpi, mutta ilman tätä sieventäminen ei toimi.

Huomaa, että yhtälö $\alpha^2 = \beta^2 - 333$ tarkoittaa, että luvun $\beta$ minimaalinen polynomi $B_1(x) = x^2 + (\alpha^2 - 333)$ kunnassa $\mathbb{Q}(\alpha)$ ei ole sama kuin minimaalinen polynomi $B$ kunnassa $\mathbb{Q}$. Toisin sanoen, $B$ jakautuu kunnassa $\mathbb{Q}(\alpha)$, ja tästä tulee ongelmia - meidän tulee käyttää tätä ehtoa hyväksi, ja tämä vaatii asian tiedostamista.


**Miten ongelma ratkaistaan?**

Ratkaisu ongelmaan on varsin yksinkertainen (vaikkakin tähän päätyminen vei paljon aikaa): olkoon $\alpha$ jokin $A$:n juuri. Olkoon $B = E_1E_2 \ldots E_t$, missä $E_i \in \mathbb{Q}(\alpha)[x]$ ovat kunnassa $\mathbb{Q}(\alpha)$ jaottomia. Olkoon $\beta_i$ jokin polynomin $E_i$ juuri kaikilla $i$. Ideana on jokaista $i$ kohden valita $\gamma_i$, jolla $\mathbb{Q}(\alpha, \beta_i) = \mathbb{Q}(\gamma_i)$, ja kertoa lukujen $\gamma_i$ minimaaliset polynomit keskenään. Tämä konstruktio toimii.


### Todistuksen rakenne

Jaoin todistuksen heti alusta lähtien kahteen osaan:

1. Osoitetaan, että saadaan luotua "melkein toimiva" $D$.
2. "Korjataan" tätä $D$.

Edellisissä osioissa on monessa kohtaa poissuljettu jotkin äärellisen monta poikkeustapausta. Tämä ei ole ongelma, koska yksittäisen polynomin alkutekijöitä voidaan muuttaa tiettyjen alkeellisten operaatioiden kautta. Osassa 2. käsitellään nämä korjaukset, joten riittää löytää miltei toimiva $D$.

Kutsun osan 1 todistusta lauseen 1 **heikoksi versioksi**. Heikon version todistus perustuu yllä esitetyn konstruktion toimivuuden todistamiseen. Tämä tehdään todistamalla, että on olemassa vastaavuus "polynomin juuret $\to$ nollakohta modulo $p$". Lopullinen todistus on aika paljon yksinkertaisempi (ja toimivampi) kuin se, jonka keksin ensimmäisenä.

Osan 2 todistus, eli **yleisen tapauksen todistus**, on täysin alkeellinen, eli se ei käytä algebrallista lukuteoriaa. Lemmat ovat enemmän tai vähemmän kisamatematiikkahenkisiä. Suosittelen yrittämään lemmojen todistamista itse.
