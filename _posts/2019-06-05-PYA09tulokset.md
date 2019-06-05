---
layout: post
author: "Olli Järviniemi"
title: "Polynomien yhteiset alkutekijät, osa 3: tulokset"
math: true
excerpt_separator: "<!--jatkuu-->"

---


Tässä postauksessa esitetään tutkielman merkittävimmät tulokset.

<!--jatkuu-->

**Sisällysluettelo**


1. [Osa 1 - johdanto](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA11johdanto.html)
2. [Osa 2 - esitiedot](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA10esitiedot.html)
3. Osa 3 - tulokset
4. [Osa 4 - motivaatio](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA08motivaatio.html)
5. [Osa 5 - heikko versio](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA07heikko.html)
6. [Osa 6 - yleinen tapaus](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA06yleinen.html)
7. [Osa 7 - lause 2](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA05lause2.html)
8. [Osa 8 - lause 3](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA04lause3.html)
9. [Osa 9 - lause 4](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA03lause4.html)
10. [Osa 10 - sovelluksia](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA02sovelluksia.html)
11. [Osa 11 - lisäaiheita](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA01lisaaiheita.html)



Ennen kuin mennään varsinaisiin päätuloksiin, pidetään jännitystä yllä ja esitetään ensiksi kaksi lemmaa, jotka kertovat paljon polynomien tekijöistä. Syynä se, että tulokset aukeavat tämän jälkeen ehkä hieman paremmin.

## Lemma 1

Olkoon positiivisen kokonaisluvun $m$ alkutekijähajotelma $p_1^{\alpha_1}p_2^{\alpha_2} \ldots p_n^{\alpha_n}$, ja olkoon $P \in \mathbb{Z}[x]$. Tällöin $m \in S_d(P)$ jos ja vain jos $p_i^{\alpha_i} \in S_d(P)$ kaikilla $i$.

Lemma 1 on hyvin kilpailumatematiikkahenkinen, ja sopii hyvin helpohkoksi harjoitustehtäväksi. Lemma 1 siis kertoo, että täytyy vain tutkia joukon $S(P)$ alkuluvun potensseja, ja tätä kautta saadaan rakennettua koko joukko.

**Todistus**

Jos $m \in S_d(P)$, yhtälöllä $P(x) \equiv 0 \pmod{m}$ on ratkaisu $x = x_0$. Tällöin yhtälöillä $P(x) \equiv 0 \pmod{p_i^{\alpha_i}}$ on tietysti myös ratkaisu $x = x_0$. Tämä osoittaa väitteen "vain jos" -suunnan.

Sitten vaikeampi "jos"-suunta. Oletetaan siis, että $p_i^{\alpha_i} \in S_d(P)$ kaikilla $i$. Tällöin yhtälöillä $P(x) \equiv 0 \pmod{p_i^{\alpha_i}}$ on ratkaisu kaikilla $i$. Merkitään näiden yhtälöiden ratkaisuja $x_1, x_2, \ldots , x_n$. Muodostetaan näiden avulla ratkaisu yhtälölle $P(x) \equiv 0 \pmod{m}$.

Tutkitaan kongruenssiyhtälöryhmää $x \equiv x_i \pmod{p_i^{\alpha_i}}$ kaikilla $1 \le i \le n$. Tällä yhtälöryhmällä on kiinalaisen jäännöslauseen nojalla ratkaisu. Olkoon $y$ jokin ratkaisu. Tällä $y$ pätee

$$P(y) \equiv P(x_i) \equiv 0 \pmod{p_i^{\alpha_i}} \ \forall 1 \le i \le n$$

Siis luku $P(y)$ on jaollinen luvulla $p_i^{\alpha_i}$ kaikilla $i$. Täten $P(y)$ on jaollinen näiden lukujen tulolla, eli $m \mid P(y)$. Tämä osoittaa väitteen "jos"-suunnan.

## Lemma 2

Olkoon $P \in \mathbb{Z}[x]$. Kaikilla paitsi äärellisen monella $p$ pätee $p \in S(P) \implies p \in S_v(P)$. Käyttäen $\approx$-notaatiota (kts. edellinen postaus) voidaan sama ilmaista sanoen $S(P) \approx S_v(P)$.

Tämä tulos on postauksessa [Henselin lemma](https://blog.matematiikkakilpailut.fi/2018/09/23/Hensel.html) harjoitustehtävä "Sovelluksen 1 yleistys". Todistus käytännössä katsoen lukee kyseisessä blogipostauksessa, mutta esitetään se kuitenkin tässä.

**Todistus**

Osoitetaan väite ensin jos $P$ ei jakaudu rationaaliluvuissa. Olkoon $p \in S(P)$ jokin alkuluku, ja olkoon $n$ sellainen, että $p \mid P(n)$. Jos $p \nmid P'(n)$, Henselin lemman nojalla (katso em. postauksen korollaari) pätee $p \in S_v(P)$. Riittää siis osoittaa, että vain äärellisen monella $p$ on olemassa sellainen $n$, että $p \mid P(n)$ ja $p \mid P'(n)$. Tämä pätee ns. Bezout'n lemman nojalla: Bezout'n lemma sanoo, että mikäli $A, B \in \mathbb{Z}[x]$ ovat yhteistekijättömiä, niin on olemassa polynomit $X, Y \in \mathbb{Z}[x]$ ja kokonaisluku $N \neq 0$, joilla

$$AX + BY = N.$$

Polynomit $P$ ja $P'$ ovat yhteistekijättömiä, koska $P$ on jaoton ja $\deg(P) > \deg(P')$. Siis $PX + P'Y = N$ sopivilla $X, Y \in \mathbb{Z}[x]$ ja $N \in \mathbb{Z}$, $N \neq 0$. Täten jos $p \mid P(n)$ ja $p \mid P'(n)$, niin $p \mid P(n)X(n) + P'(n)Y(n) = N$, mikä pätee vain äärellisen monella $p$.

Olemme siis todistaneet väitteen jaottomille $P$. Osoitetaan se vielä, kun $P$ jakautuu.

Yleisessä tapauksessa hajotetaan $P$ jaottomien polynomien tuloksi: $P = P_1P_2 \ldots P_n$, missä $P_i \in \mathbb{Z}[x]$ eivät jakaudu. Polynomit $P_i$ voidaan siis valita kokonaislukukertoimisiksi, kuten todettiin edellisessä postauksessa. Nyt, jos $p \in S(P)$, pätee $p \in S(P_i)$ jollain $i$. Soveltaen edellisen kappaleen tulosta polynomille $P_i$ saadaan, että kaikilla paitsi äärellisen monella $p$ pätee $p \in S_v(P_i)$, joten $p \in S_v(P)$. Tämä osoittaa väitteen kaikille $P$.


# Tulokset

## Lause 1

Tutkielman päätulos on seuraava:

Olkoot $P_1, P_2, \ldots , P_n \in \mathbb{Z_c}[x]$. On olemassa sellainen $D \in \mathbb{Z_c}[x]$, jolla

$$S_d(D) = S_d(P_1) \cap S_d(P_2) \cap \ldots \cap S_d(P_n).$$


Todistus on konstruktiivinen, eli se antaa tavan löytää tällaisen $D$, eikä vain todista sen olemassaoloa. Lisäksi konstruoidun $D$ aste on $\deg(P_1)\deg(P_2) \ldots \deg(P_n)$. Aina ei ole olemassa pienempiasteista $D$, joka kelpaisi lauseen 1 mukaiseksi $S$. Konstruktio on siis jollain mittapuulla luonnollinen, "paras mahdollinen".

Selvästi riittää osoittaa väite tapauksessa $n = 2$, koska $n > 2$ seuraa suoraan induktiolla. Tämän vuoksi lauseen todistuksessa keskitytään vain tapaukseen $n = 2$.

Tutki-Kokeile-Kehitä -kilpailun finaalin jälkeen aloin tutkimaan seuraavaa lauseen 1 yleistystä: lause 1 voidaan tulkita niin, että yhtälöryhmällä $P_i(x_i) \equiv 0 \pmod{p}$ on ratkaisu modulo $p$ jos ja vain jos yhtälöllä $D(x) \equiv 0 \pmod{p}$ on ratkaisu modulo $p$. Tämä voidaan yleistää yleiselle polynomiyhtälöryhmälle:

## Lause 1'

Olkoot $F_1, F_2, \ldots , F_k$ kokonaislukukertoimisia polynomeja muuttujissa $x_1, x_2, \ldots , x_n$. On olemassa sellainen $D \in \mathbb{Z}[x]$, jolla pätee seuraava väite:

Yhtälöryhmällä

$$F_1(x_1, x_2, \ldots , x_n) \equiv 0 \pmod{p}$$

$$F_2(x_1, x_2, \ldots , x_n) \equiv 0 \pmod{p}$$

$$\ldots$$

$$F_k(x_1, x_2, \ldots , x_n) \equiv 0 \pmod{p}$$

on ratkaisu modulo $p$ jos ja vain jos yhtälöllä $D(x) \equiv 0 \pmod{p}$ on ratkaisu modulo $p$.

Polynomiyhtälöryhmän ratkeaminen voidaan siis redusoida yhden yhtälön tutkimiseksi. Kaunista.

Lause 1' seuraa suoraan lauseesta 1, sekä James Axin työn Solving Diophantine Problems Modulo Every Prime lauseesta 1. Tämä tulos on seuraava:

Olkoot $F_1, \ldots , F_k$ kuten yllä. Niiden $p$ joukko, joilla yllä esitetyllä yhtälöryhmällä $F_i(x_1, \ldots , x_n) \equiv 0 \pmod{p}$ on ratkaisu modulo $p$, voidaan esittää yhdistelmänä leikkauksia, unioneja ja komplementteja joukoista muotoa $S(P), P \in \mathbb{Z}[x]$.

Lause 1' seuraa siis James Axin lauseesta 1 sekä minun lauseesta 1, sekä seuraavista huomioista:

1. Olkoot $A, B \in \mathbb{Z}[x]$. On olemassa sellainen $D \in \mathbb{Z}[x]$, että $S(A) \cup S(B) = S(D)$. Tämä on triviaalia: valitaan $D = AB$.

2. Ax käyttää komplementteja vain käsitelläkseen äärellisen montaa alkulukua, eli hän haluaa poistaa äärellisen monta alkulukua jostain joukosta $S$, ja hän tekee sen tutkimalla joukkoa $S \cap S(nx + 1)^c$, missä $S(P)^c$ kuvaa joukon $S(P)$. Polynomilla $nx + 1$ on tietysti alkutekijöinään täsmälleen ne alkuluvut $p$, jotka eivät jaa lukua $n$.
Todistamme lauseen 1 todistuksessa, että tämä äärellisen monen alkutekijän poistaminen voidaan tehdä myös muulla tavalla ilman komplementteja.


## Lause 2

Lause 2 toimii yleistyksenä Schurin lauseelle.

Olkoot $P_1, P_2, \ldots , P_n \in \mathbb{Z_c}[x]$. Pätee

$$\delta(S_v(P_1) \cap S_v(P_2) \cap \ldots \cap S_v(P_n)) \ge \frac{1}{\deg(P_1)\deg(P_2) \ldots \deg(P_n)}$$

(Vasemman puolen tiheys on olemassa)

Lauseen 2 todistus seuraa suoraan lauseesta 1 ja lemmasta 2, kun osoitetaan, että $\delta(S(P)) \ge \frac{1}{\deg(P)}$ kaikilla $P \in \mathbb{Z_c}[x]$ (miksi? Muista raja $D$:n asteelle). Tämän osoittaminen ei ole kuitenkaan aivan triviaalia.

Lisäksi lauseen 2 alaraja on tiukka, eli se saavutetaan jollain polynomien $P_i$ valinnoilla (ja tarkemmin, monenlaisilla eri valinnoilla).


## Lause 3

Monessa tapauksessa polynomien $P_i$ yhteisten alkutekijöiden tiheys voidaan laskea. Lauseen väite on hieman tekninen, joten määritellään sitä ennen ns. juurikunta (engl. splitting field).

**Juurikunta**

Olkoon polynomin $P \in \mathbb{Z_c}[x]$ juuret $\alpha_1, \alpha_2, \ldots , \alpha_n$. Polynomin $P$ juurikunta määritellään olemaan kunta $\mathbb{Q}(\alpha_1, \alpha_2, \ldots , \alpha_n)$.

Juurikunta on siis pienin kunta, jossa $P$ jakautuu ensimmäisen asteen tekijöihin. Se on samalla pienin kunta, joka sisältää kaikki $P$:n juuret.

Lauseen 3 muotoilu on seuraava:

Olkoot $P_1, P_2, \ldots , P_n \in \mathbb{Z_c}[x]$. Olkoon $F_i$ polynomin $P_i$ juurikunta, ja olkoon $F$ polynomin $P_1P_2 \ldots P_n$ juurikunta (eli siis pienin kunta, joka sisältää kaikkien $P_i$ kaikki juuret). Oletetaan, että

$$[F : \mathbb{Q}] = [F_1 : \mathbb{Q}][F_2 : \mathbb{Q}] \cdots [F_n : \mathbb{Q}]$$

Tällöin pätee

$$\delta(S(P_1) \cap S(P_2) \cap \ldots \cap S(P_n)) = \delta(S(P_1))\delta(S(P_2)) \cdots \delta(S(P_n))$$

Mitä lause käytännössä kertoo? Ehtoa juurikuntien laajennuksien asteista voiadan ajatella ehtona siitä, että polynomit $P_i$ eivät "kommunikoi keskenään". Tällöin yhteisten alkutekijöiden tiheys on se, minkä sen olettaisikin olevan.

**Esimerkki**

Olkoot $P_1(x) = x^2 - 2$ ja $P_2(x) = x^2 - 3$. Juurikunnat $F_1$ ja $F_2$ ovat tällöin $\mathbb{Q}(\sqrt{2}, -\sqrt{2})$ ja $\mathbb{Q}(\sqrt{3}, -\sqrt{3})$. Mutta selvästi $\mathbb{Q}(\sqrt{2}, -\sqrt{2}) = \mathbb{Q}(\sqrt{2})$, koska luku $-\sqrt{2}$ kuuluu kuntaan $\mathbb{Q}(\sqrt{2})$. Täten

$$F_1 = \mathbb{Q}(\sqrt{2})$$

ja vastaavasti

$$F_2 = \mathbb{Q}(\sqrt{3})$$

Lisäksi

$$F = \mathbb{Q}(\sqrt{2}, -\sqrt{2}, \sqrt{3}, -\sqrt{3}) = \mathbb{Q}(\sqrt{2}, \sqrt{3})$$

Edellisessä postauksessa totesimme, että $[F : \mathbb{Q}] = 4$. Siispä

$$[F : \mathbb{Q}] = 4 = 2 \cdot 2 = [F_1 : \mathbb{Q}][F_2 : \mathbb{Q}]$$

Ehto siis toteutuu. Tiheydet $\delta(S(P_1)), \delta(S(P_2))$ ovat molemmat $\frac{1}{2}$, mikä on todistettu postauksessa [Neliönjäännökset](https://blog.matematiikkakilpailut.fi/2018/12/09/Nelionjaannos.html) (tälle esitetään myöhemmin toinen, parin rivin todistus käyttäen voimakasta Frobeniuksen lausetta). Lauseen 3 nojalla pätee

$$\delta(S(P_1) \cap S(P_2)) = \delta(S(P_1))\delta(S(P_2)) = \frac{1}{2} \cdot \frac{1}{2} = \frac{1}{4}$$

Tiheys vastaa heuristiikkaa, joka esitettiin [Neliönjäännökset](https://blog.matematiikkakilpailut.fi/2018/12/09/Nelionjaannos.html)-postauksessa. Lausetta voidaan oikeastaan pitää heuristiikan yleistyksenä (ja formaalina todistuksena):

Valitaan jokin satunnainen alkuluku $p$. Todennäköisyys tapahtumalle ""$p$ on polynomin $P_i$ alkutekijä" on $\delta(S(P_i))$. Jos oletamme, että nämä tapahtumat ovat toisistaan riippumattomia, niin tapahtuman "p on $P_i$:n alkutekijä kaikilla $i$" todennäköisyys on vain erillisten tapahtumien todennäköisyyksien tulo,

$$\delta(S(P_1))\delta(S(P_2)) \cdots \delta(S(P_n))$$

Lauseen ehto $[F : \mathbb{Q}] = [F_1 : \mathbb{Q}] \ldots [F_n : \mathbb{Q}]$ siis takaa tämän tapahtumien riippumattomuuden. Tämä voi tuntua absurdilta: miten polynomien juurikunnat kertovat yhtään mitään niiden alkutekijöistä? Tämä on loistava, syvällinen kysymys. Olen tutkielman tekemisen aikana lukuisten esimerkkien kautta saanut tähän jonkinnäköistä intuitiota, jota pyrin jakamaan lukijoille. Tähän kysymykseen pyritään vastaamaan pala palalta eri postauksissa.

Mainitaan vielä, että tapauksessa $n = 2$ ehto $[F : \mathbb{Q}] = [F_1 : \mathbb{Q}][F_2 : \mathbb{Q}]$ on ekvivalenttia ehdon $F_1 \cap F_2 = \mathbb{Q}$ kanssa. Jälkimmäinen ehto on minusta intuitiivisempi tapa ajatella riippumattomuutta.

Myöhemmässä postauksessa todistan lausetta 3 käyttäen [Neliönjäännökset](https://blog.matematiikkakilpailut.fi/2018/12/09/Nelionjaannos.html)-postauksessa esitettyjen heuristiikkojen tulosten paikkansapitävyyden. Ensimmäinen tulos on, tämän työn termistöä käyttäen, polynomien $x^2 - a_i$ yhteisten alkutekijöiden tiheys. Toinen tulos on viimeisen harjotustehtävän mukaisten polynomien $x^q - a$ alkutekijöiden tiheys, sekä tätä muotoa olevien polynomien yhteiset alkutekijät. Näitä asioita en tilanpuutteen vuoksi esittänyt varsinaisessa tutkielmassani.

## Lause 4

Mitä arvoja $\delta(S(P))$ voi saada? Lause 4 vastaa tähän kysymykseen:

Olkoon $r \in [0, 1]$. On olemassa sellainen $P$, jolla $\delta(S(P)) = r$, jos ja vain jos $r$ on rationaalinen.

Oikeastaan osoitin pelkästään "jos"-puolen - "vain jos"-puoli seuraa suoraan myöhemmin esitettävästä Frobeniuksen lauseesta.

Lause 4 on tuloksena mielenkiintoinen, mutta sillä ei tunnu olevan mielenkiintoisia seurauksia (jos keksit jotain, kerro minulle!). Se kuitenkin toimii esimerkkinä siitä, mitä työn tuloksilla voidaan todistaa.



**Sisällysluettelo**


1. [Osa 1 - johdanto](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA11johdanto.html)
2. [Osa 2 - esitiedot](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA10esitiedot.html)
3. Osa 3 - tulokset
4. [Osa 4 - motivaatio](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA08motivaatio.html)
5. [Osa 5 - heikko versio](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA07heikko.html)
6. [Osa 6 - yleinen tapaus](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA06yleinen.html)
7. [Osa 7 - lause 2](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA05lause2.html)
8. [Osa 8 - lause 3](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA04lause3.html)
9. [Osa 9 - lause 4](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA03lause4.html)
10. [Osa 10 - sovelluksia](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA02sovelluksia.html)
11. [Osa 11 - lisäaiheita](https://blog.matematiikkakilpailut.fi/2019/06/05/PYA01lisaaiheita.html)
