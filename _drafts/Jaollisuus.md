---
layout: post
author: "Olli Järviniemi"
title: "Jaollisuus rationaaliluvuissa"
math: true
excerpt_separator: "<!--jatkuu-->"

---

<div class="hidden">
$\newcommand{\syt}{\mathop{\rm syt}}$
</div>


Tässä postauksessa esitetään luonnollinen yleistys jaollisuudelle rationaaliluvuissa.

<!--jatkuu-->

Kovin yllättäviä tuloksia ei tulla näkemään: tarkoituksena on lähinnä vakuuttaa lukija siitä, että tavanomaiset ominaisuudet säilyvät rationaaliluvuilla.

Kaikkien postauksen rationaalilukujen oletetaan olevan supistetussa muodossa.

**Määritelmä 1**

Olkoon $r = \frac{a}{b}$, missä $a, b \in \mathbb{Z}$, ja olkoon $m \in \mathbb{Z_+}$. Sanotaan, että $m \mid r$, jos $\syt(m, b) = 1$ ja $m \mid a$.

Määritelmä on hyvin luonnollinen. Osoitetaan ensin perusfaktoja. Yksityiskohtien määrä todistuksissa vähenee loppua kohden.

**Perusominaisuus 1**

Olkoon $m \in \mathbb{Z_+}$ annettu, ja olkoot $s, r \in \mathbb{Q}$. Oletetaan, että $m \mid s$ ja $m \mid r$. Tällöin $m \mid s + r$, $m \mid s - r$.

**Todistus**

Kirjoitetaan $s = \frac{a}{b}$, $r = \frac{c}{d}$. On annettu $\syt(m, b) = \syt(m, d) = 1$, ja $m \mid a$, $m \mid c$. Täten $m \mid ad + bc$, joten $m \mid \frac{ad + bc}{bd} = s + r$. Vastaavasti saadaan osoitettua $m \mid s - r$.

**Perusominaisuus 2**

Olkoon $m \in \mathbb{Z_+}$ annettu, ja olkoot $s, r \in \mathbb{Q}$. Oletetaan, että $m \mid s$, ja että luvulla $m$ ei ole yhteisiä tekijöitä luvun $r$ nimittäjän kanssa. Tällöin $m \mid sr$.

**Todistus**

Kuten edellä, kirjoitetaan $s = \frac{a}{b}$, $r = \frac{c}{d}$. Annetuista ehdoista seuraa $m \mid ac$, joten $m \mid \frac{ac}{bd} = sr$.

**Perusominaisuus 3**

Olkoon $p$ alkuluku, ja olkoot $s, r \in \mathbb{Q}$ sellaisia, joiden nimittäjät eivät ole jaollisia luvulla $p$. Oletetaan, että $p \mid sr$. Tällöin $p \mid s$ tai $p \mid r$ (tai molemmat).

**Todistus**

Seuraa suoraan vastaavasta väitteestä kokonaisluvuille.

Kongruessit voidaan määritellä aivan kuten kokonaisluvuille:

**Määritelmä 2**

Olkoot $s, r \in \mathbb{Q}$, ja $m \in \mathbb{Z_+}$. Sanotaan, että $s \equiv r \pmod{m}$, jos $m \mid s - r$.

**Rationaaliluvut kokonaislukuina**

Olkoon $s = \frac{a}{b} \in \mathbb{Q}$, ja $m \in \mathbb{Z_+}$. Oletetaan, että $\syt(b, m) = 1$. Tällöin $s$ voidaan tulkita kokonaislukuna $c$ modulo $m$, missä $c$ valitaan luvuksi $ab^{-1}$. Tässä $b^{-1}$ on luvun $b$ käänteisalkio modulo $m$.

**Perustelu**

Olkoon $k = \phi(m)$. Eulerin lauseen nojalla $b^k \equiv 1 \pmod{m}$, eli $b^{-1} \equiv b^{k-1} \pmod{m}$. Siis $c = ab^{k-1}$. Nyt, $s - c = \frac{a}{b} - ab^{k-1} = \frac{a - ab^k}{b}$. Täten Eulerin lauseen nojalla $m \mid s - c$, eli $s \equiv c \pmod{m}$.

Rationaalilukujen tulkinta kokonaislukuina on monesti varsin kätevää. Esimerkiksi tutkittaessa tiettyä joukkoa rationaalilukuja modulo alkuluku $p$, voidaan tietyissä tilanteissa poissulkea ne äärellisen monta $p$, jotka jakavat jonkin annetun rationaaliluvun nimittäjän. Muissa tapauksissa ongelma palautuu kokonaislukujen käsittelyyn.

**Huomautus**

Rationaaliluvuille $s$ ja $r$ voi päteä $s \equiv r \pmod{m}$, vaikkei lukuja $s$ ja $r$ voitaisikaan tulkita kokonaislukuina modulo $m$. Yksinkertaisin esimerkki tästä on $s = r = \frac{1}{m}$, missä $m > 1$.

Perusominaisuuksia kongruensseista on jätetty todistettavaksi harjoitustehtävinä.

Huomautetaan vielä, että jaollisuus voidaan määritellä myös aritmetiikan peruslauseen kautta:

**Määritelmä 4**

Olkoot $p_1, p_2, \ldots$ alkuluvut pienimmästä suurimpaan. Jokainen nollasta eroava rationaaliluku voidaan aritmetiikan peruslauseen nojalla esittää lukujonolla $\alpha_1, \alpha_2, \ldots$, missä kaikki paitsi äärellisen moni $\alpha_i \in \mathbb{Z}$ on nolla. Olkoot $0 \neq r \in \mathbb{Q}$ ja $m \in \mathbb{Z_+}$. Olkoot $r_1, r_2, \ldots $ ja $m_1, m_2, \ldots $ lukuja $r$ ja $m$ vastaavat lukujonot. Sanotaan, että $m \mid r$, jos ja vain jos $m_i \le r_i$ kaikilla $i$.

**Huomautus**

Määritelmässä voisi hyvin olla kokonaisluvun $m$ tilalla mielivaltainen $0 \neq s \in \mathbb{Q}$.

Ja vielä yksi vaihtoehtoinen määritelmä:

**Määritelmä 5**

Olkoot $r = \frac{a}{b}$ ja $m \in \mathbb{Z_+}$ annettu. Kirjoitetaan $m \mid \frac{a}{b}$, jos $mb \mid a$.

Tässä määritelmässä ei tarvitse erikseen huolehtia siitä, ovatko $a$ ja $b$ yhteistekijättömiä. Vastaavasti voidaan myös määritellä $\frac{a}{b} \mid \frac{c}{d}$, jos $ad \mid bc$. Tämä jälleen vastaa kokonaislukujen jaollisuutta: $a \mid b$ jos $\frac{b}{a}$ on kokonaisluku, joten $\frac{a}{b} \mid \frac{c}{d}$ jos

$$\frac{\frac{c}{d}}{\frac{a}{b}} = \frac{bc}{ad}$$

on kokonaisluku.

Määritelmät rationaaliluvuille voivat tuntua suorastaan triviaaleilta, joten onko niistä hyötyä mihinkään? Valtavia hyötyjä ei liene, mutta jaollisuuden yleistetyn määritelmän avulla voidaan hieman yksinkertaistaa joitain argumentteja. Näin voi käydä esimerkiksi käsitellessä kokonaislukukertoimisia polynomeja:

**Esimerkki (Henselin lemma -blogipostaus, sovelluksen 1 yleistys)**

Olkoon $P \in \mathbb{Z}[x]$. Oletetaan, että yhtälöllä $P(x) \equiv 0 \pmod{p}$ on ratkaisu, missä $p$ on alkuluku. Kaikilla paitsi äärellisen monella $p$ yhtälöllä $P(x) \equiv 0 \pmod{p^k}$ on ratkaisu kaikilla $k \in \mathbb{Z_+}$.

**Todistus**

Väite on todistettu [Henselin lemma](https://blog.matematiikkakilpailut.fi/2018/09/23/Hensel.html) -postauksessa jakautumattomille polynomeille. Lienee selvää, että väite pätee myös jakautuvilla polynomeilla: kirjoitetaan jakautuva $P$ muodossa $P_1P_2 \ldots P_n$, missä $P_i$ ovat ei-vakioita jakautumattomia polynomeja. Tällöin, jos yhtälöllä $P(x) \equiv 0 \pmod{p}$ on ratkaisu, on yhtälöllä $P_i(x) \equiv 0 \pmod{p}$ ratkaisu, joten edellisen nojalla yhtälöllä $P_i(x) \equiv 0 \pmod{p^k}$ on ratkaisu kaikilla $k \in \mathbb{Z_+}$ (poislukien äärellisen monta $p$). Tämä todistaa väitteen, koska nyt yhtälöllä $P(x) \equiv 0 \pmod{p^k}$ on ratkaisu.

Yllä oleavssa argumentissa on kuitenkin pieniä yksityiskohtia, jotka eivät toimi kuten pitäisi. Ei liene triviaalia, että polynomit $P_i$ voidaan valita kokonaislukukertoimiksi, vaan ainoastaan rationaalilukukertoimisiksi. Tällöin väitettä ei voida soveltaa jakautumattomille tekijöille $P_i$, koska ne eivät ole kokonaislukukertoimisia.

Helpoin ratkaisu ongelmaan lienee todistaa väite suoraan kaikille $P \in \mathbb{Q}[x]$ vastaavalla tavalla, ensin osoittamalla väitteen jakautumattomille $P$. Tällöin kaikki toimii kuten aiemminkin, paitsi tekijöihinjaon kanssa ei tule ongelmaa.

**Huomautus**

$P_i$ voidaan aina valita kokonaislukukertoimisiksi $P$:n ollessa kokonaislukukertoiminen. Todistus tälle väitteelle löytyy esimerkiksi [täältä](https://math.dartmouth.edu/archive/m31w05/public_html/Q-Z-Reducibility.pdf).


**Harjoitustehtäviä**

**Kongruenssien perusominaisuuksia**

Olkoot $r, s \in \mathbb{Q}$ ja $m \in \mathbb{Z_+}$. Oletetaan, että $r \equiv s \pmod{m}$. Osoita, että

1. $r + x \equiv t + x \pmod{m}$ kaikilla $x \in \mathbb{Q}$.
2. $rx \equiv sx \pmod{m}$ kaikilla rationaaliluvuilla $x$, joiden nimittäjillä ei ole yhteisiä tekijöitä luvun $m$ kanssa. Erityisesti todetaan, että kongruenssiyhtälön saa kertoa puolittain kokonaisluvulla.


**Ei-säilyvä ominaisuus**

On tunnettua, että kokonaisluvuilla $a, b, c, d, m \in \mathbb{Z}$, joilla $a \equiv b \pmod{m}$, $c \equiv d \pmod{m}$ pätee  $ac \equiv bd \pmod{m}$. Erikoistapauksessa $a = c$, $b = d$ saadaan $a^2 \equiv b^2 \pmod{m}$. Osoita, että vastaava ominaisuus ei kuitenkaan päde rationaaliluvuilla, eli osoita, että on olemassa sellaiset rationaaliluvut $r, s$ ja kokonaisluku $m$, joilla $r \equiv s \pmod{m}$, mutta $r^2 \not\equiv s^2 \pmod{m}$.

**Polynomien arvot moduloissa**

On tunnetta, että kaikilla $P \in \mathbb{Z}[x]$ ja $a, b, m \in \mathbb{Z}$ pätee $a \equiv b \pmod{m} \implies P(a) \equiv P(b) \pmod{m}$. Edellisen tehtävän nojalla vastaava väite ei kuitenkaan päde, jos $a$ ja $b$ korvataan rationaaliluvuilla ($P(x) = x^2$). Osoita, että myös toinen vastaava ominaisuus ei päde, eli:

On olemassa sellaiset $P \in \mathbb{Q}[x]$, $a, b, m \in \mathbb{Z}$, joilla $a \equiv b \pmod{m}$, mutta $P(a) \not\equiv P(b) \pmod{m}$.

Osoita, että seuraava väite kuitenkin pätee:

Olkoon $P \in \mathbb{Q}[x]$, ja $a, b \in \mathbb{Z}[x]$. Olkoon $p$ alkuluku, ja $k \in \mathbb{Z_+}$ mielivaltainen. Olkoon vielä $c$ suurin kokonaisluku, jolla $p^c$ jakaa jonkin $P$:n kertoimien nimittäjistä. Osoita, että

$$a \equiv b \pmod{p^{c + k}} \implies P(a) \equiv P(b) \pmod{p^k}$$

Huomaa, että tämän väitteen avulla voidaan myös tutkia rationaalilukukertoimisia polynomeja missä tahansa moduloissa kiinalaisen jäännöslauseen avulla.
