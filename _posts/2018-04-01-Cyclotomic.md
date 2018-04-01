---
layout: post
author: "Valtteri Aurela"
title: "Cyclotomisten polynomien soveltaminen valmennustehtävään"
math: true
---
<div class="hidden">
$\newcommand{\gcd}{\mathop{\rm gcd}}$
</div>

**Tehtävä** _tammikuun valmennustehtävät, tehtävä 14_

Olkoon $n$ positiivinen kokonaisluku ja $\sigma(n)$ luvun $n$ tekijöiden summa. Osoita, että on olemassa ääretön määrä positiivisia kokonaislukuja $n$, joille $n$ jakaa luvun $2^{\sigma(n)}-1$

**Tarvittavat tiedot ratkaisuun**

1. Cyclotomic polynomials
    * tarvittavat tiedot löytyvät pdf:stä
    http://web.evanchen.cc/handouts/ORPR/ORPR.pdf
2. perustietämys lukuteoriasta
    * tarvittavat tiedot löytyvät esimerkiksi pdf:stä https://matematiikkakilpailut.fi/kirjallisuus/tormayskurssi.pdf

**Tarkennusta cyclotomisista polynomeista**
Tämä Evan Chenin moniste on aika haastava, mutta suosittelen vahvasti lukemista. Kerron kuitenkin nyt tässä ilman todistusta tässä ratkaisussa tarvittavat asiat.

Merkataan $n$:nnettä $x$:n cyclotoomista polynomia $\Phi_n(x)$

Mitä ne ovat:
Cyclotomiset polynomit ovat kokonaislukukertoimisia polynomeja, joilla on mielenkiintoisia ominaisuuksia. Itse olen sitä mieltä, että niistä kannattaa jonkin verran tietää, sillä ne voivat helpottaa tehtäviä erikoisilla tavoilla.
Tulomuoto:
Cyclotomiset polynomit antavat meille tulomuodon $a^n-1=\prod_{d \mid n}\Phi_d(a)$
kakkosten potenssit:
Kaikilla $n$ pätee  $\Phi_{2^n}(x)=x^{2^{n-1}}+1$
**Ratkaisu**

Muunnetaan tehtävänannon $2^{\sigma(n)}-1$ muotoon. $\prod_{d|\sigma(n)}\Phi_d(2)$</br>
Tekijöiden summan voi laskea  kaavalla
$$\sigma(n) =\frac{{p_1}^{a_1+1}-1}{p_1-1} \frac{{p_2}^{a_2+1}-1}{p_2-1}\cdots \frac{{p_k}^{a_k+1}-1}{p_k-1}$$
</br>
missä $p_i$ on $n$:n alkutekijä ja  $a_i$ on $p_i$:n exponentti saadaan
Nyt katsotaan, mitä tapatuu kun syötämme tehtävään $n=3$
</br>
Koska $\sigma(3)=\frac{3^2-1}{3-1}=\frac{8}{2}=4$
</br>
siis ${2^{\sigma(3)}}-1=2^4-1=\Phi_1(2)\Phi_2(2)\Phi_4(2) = (2-1)(2^1+1)(2^2+1)=1 \cdot 3 \cdot 5$<br>
Nähdään selvästi, että tämä luku on jaollinen 3:lla ja 5:llä<br>
Nyt katsotaan, millä voimme kertoa tuon edellisen $n$:n, joka tässä tapauksessa on 3 siten, että uusi luku on edelleen tehtävänannon mukainen.
Jos kerromme 3:n 5:llä ja otamme siitä tekijöiden summan, tulos on yksinkertaisesti $\sigma(3\cdot5)=\sigma(3)\cdot\sigma(5)=24$, koska $\gcd(3,5)=1$
Asetetaan $n=15$ saamme $2^{\sigma(15)}-1=2^{24}-1= \Phi_1(2)\Phi_2(2)\Phi_4(2)k=3\cdot5\cdot k$
jollain arvolla $k$. Tämä muoto saatiin käyttämällä cyclotomisten polynomien tuomaa tulomuotoa luvuille muotoa $x^n-1$. Selvästi tämä luku on jaollinen luvuilla 3 ja 5. Koska $\gcd(3,5)=1$ tiedämme, että luku on myös jaollinen luvulla 15. Tämän ansioista tiedämme, että 15 on myös tehtävänannon mukainen $n$. </br>
Eli jos kerromme $n$:n 5:llä saamme uuden tehtävänantoon sopivan luvun. Entä jos olisimme kertoneet $n$:n 3:lla, mikä oli toinen vaihtoehto aikaisemmin? Silloin saisimme $\sigma(3\cdot3) \neq \sigma(3) \cdot \sigma(3)$, koska $\gcd(3,3) \neq 1$. Tämä siis ei ole tehtävänannon mukainen $n$.

Tästä huomaamme tärkeän asian:
</br>
Jos meillä on luku $n$, jolla $2^{\sigma(n)}-1$ on jaollinen $n$:llä ja $m$ jakaa luvun $2^{\sigma(n)}-1$ ja jolla $\gcd(n,m)=1$ niin pätee, että $2^{\sigma(nm)}-1$ on jaollinen $nm$:llä

Tämän todistus menee cyclotomisilla polynomeilla:</br>
Oletetaan, että $n$ jakaa luvun $2^{\sigma(n)}-1$ ja $m$ jakaa saman luvun.
Tutkitaan lukua $2^{\sigma(nm)}-1=\prod_{d|\sigma(nm)}\Phi_d(2)$. Tämä luku voidaan esittää nyt tulomuodossa, jossa on selvästi kaikki samat tekijät kuin luvulla $2^{\sigma(n)}-1$. Tämä on helppo nähdä, sillä $\sigma(nm)=\sigma(n)\cdot\sigma(m)$, kun $\gcd(n,m)=1$, joten kaikki luvut, jotka jakavat $\sigma(n)$ jakavat myös luvun $\sigma(mn)$
Luku on siis selvästi jaollinen $n$:llä ja $m$:llä. Luku on siis myös jaollinen $nm$:llä

Nyt meidän pitää löytää jokin luku $n_0$ siten, että sen jälkeen voimme aina valita luvun $m$ niin, että $m$ jakaa $2^{\sigma(n_{i})}-1$ ja $\gcd(m,n_i)$ on 1. Sen jälkeen voimme sanoa, että $n_{i+1} = m \cdot n_i$
Tässä $n_i$ on tehtävänannon mukainen kaikilla $i$.
</br>
Tässä meitä auttaa Fermat'n luvut.</br>
Fermat'n luvut ovat muotoa $2^{2^n}+1$. Merkataan $i$:tä Fermat'n lukuja $F_i$. On yleisesti tunnettua, että $gcd(F_i,F_j)=1$ kaikilla $i$ ja $j$, kun $i \neq j$ Tämä jätetäänkin lukijalle harjoitustehtäväksi.

Huomataan, että $\Phi_{2^n}(2)=2^{(2^{(n-1)})}+1$ eli $\Phi_{2^n}(2)$ on Fermat'n luku jokaisella $n$. Haluamme valita luvun $m$ jolla pätee   $\gcd(m,n)=1$ ja $m \mid 2^{\sigma(n)-1}$.
Se mitä seuraavaksi aiomme tehdä on hyvin yksinkertaista. Aiomme valita tämän luvun $n_0$, joka on tehtävänannon mukainen ja Fermat'n luku. Sitten aiomme todistaa, että voimme joka askeleella valita uuden Fermat'n luvun $m$ siten, että myös $n_{i-1}\cdot m$ on tehtävänannon mukainen luku. Voimme nyt määritellä $n_i=n_{i-1}\cdot m$. $n_i$ on tehtävänannon mukainen luku kaikilla $i \ge 0$

Etsimme nyt siis sellaista $m$:ää jolla pätee, että $\gcd(m,n)=1$ ja $m\cdot n$ on tehtävänannon mukainen.

Aiemmasta esimerkistä huomaamme, että 3 on toimiva $n$:n arvo ja 3 on myös Fermat'n luku. Koska $\sigma(3)=4$ huomaamme, että $\sigma(3)$ on jaollinen kahdella kakkosen (positiivisella) potenssilla. Nämä luvut ovat 2 ja 4 joten $2^{\sigma(3)}-1=2^4-1=k\cdot\Phi_2(2)\cdot \Phi_4(2)$ jollain kokonaisluvulla $k$, jolla ei ole nyt suurta väliä. Se millä on väliä on se, että tämä luku on selvästikin jaollinen "käyttämättömällä" Fermat'n luvulla eli $\Phi_4(2)=5$. Jos siis kerrome 3:n 5:llä saamme $\sigma(3\cdot5) = \sigma(3) \cdot \sigma(5) = 4\cdot6 = 24$. Nyt $3\cdot 5$ on tehtävänannon mukainen $n$</br>
Huomataan, että 24 on jaollinen luvulla $8 = 2^3$. Tämä johtaa siihen, että kolme Fermat'n lukua jakaa luvun $2^{8}-1$. Nämä luvut ovat $\Phi_2(2)$,$\Phi_4(2)$ ja $\Phi_8(2)$. Tässä tapauksessa "uusi" Fermat'n luku on $\Phi_8(2)=2^4+1=17$</br>
Saatatte huomata, että olemme tässä valinneet $n_0=3$ ja $m=5$ eli $n_1=15$.
Tämä ei ole mikään erikoistapaus vaan saamme uuden Fermat'n luvun joka kerta, kun "valitsemme" uuden Fermat'n luvun $m$:n, jolle pätee ylempänä näkyvät ehdot.

Tämä johtuu siitä, että $\sigma(n) \equiv 0 \pmod{2}$, jos ja ja vain jos $n$ ei ole muotoa $2^ab^2$ ja Fermat'n luvut eivät ole muotoa $2^ab^2$. Tämä todistus on helppo ja jätetään harjoitustehtäväksi. Tämän ansioista aina kun valitsemme uuden luvun $m$, saamme uuden kakkosen potenssin, joka jakaa luvun $\sigma(nm)=\sigma(n)\sigma(m)$.

Valitaan $n_0=3$. Nyt saamme myös, joka kerta valittua uuden Fermat'n luvun $m$, jolla pätee, että $n_{i+1}=n_i\cdot m$.
Nyt $n_i$ on tehtävänannon mukainen luku jokaisella positiivisella kokonaisluvulla $i$.
Koska voimme toistaa tämän äärettömän monta kertaa, saamme äärettömän monta $n$ jolle pätee, että $2^{\sigma(n)}-1$ on jaollinen $n$:llä.
Olemme näin todistaneet tehtävänannon väitteen.
