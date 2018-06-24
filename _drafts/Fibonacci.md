---

layout: post
author: "Valtteri Aurela"
title: "Fibonaccin luvut ja binomikertoimet"
math: true

---

**Postauksen tarkoitus**\\
Tässä postauksessa käsitellään mielenkiintoista yhteyttä Fibonaccin lukujen ja binomikertoimien välillä. Saman tuloksen saamiseen on monta eri keinoa, mutta käymme tässä läpi mukavan kombinatorisen todistuksen ja hieman motiiveja välivaiheiden takana.

**1. Tarvittavat pohjatiedot**\\
Koska todistus on hyvin alkeellinen, ei paljoakaan etukäteistietoja tarvita. Jonkinlainen kästiys binomikertoimien käyttötarkoituksista tarvitaan, sillä ne ovat tärkeä osa todistettavaa väitettä ja ilman niitä viimeinen osa saattaa jäädä hieman epäselväksi.

Jos jokin asia jää mietityttämään, kannattaa käydä välivaihe itse läpi siten, että ymmärtää sen täysin. Tämäntyyppinen miettiminen on hyvin kehittävää.

**2. Todistettava muoto**\\
Kun keksin alunperin tämän todistuksen, en yrittänyt todistaa seuraavaksi esitettävää väitettä. Todistus tapahtui puoliksi vahingossa tutkiessani, mitä tapahtuisi, jos muuttaisin Fibonaccin lukuja kombinatoriseen muotoon. Haluan kuitenkin kertoa ensiksi mihin "tähtäämme", jotta olisi helpompi miettiä kokonaisuudessa, mitä tapahtuu.

Määritellään $F_n$ on $n$:nnes Fibonaccin luku. Nyt pätee, että $$F_n = \sum\limits_{i\leq \frac{n}{2} } {n-i \choose i} $$

**3. Todistus**\\
Todistus voi lähteä aluksi hieman erikoisen näköiseen suuntaan, mutta palaa kuitenkin asiaan. Tulokseen kyllä päästään tekstin loppuun mennessä.

**Lemma 1.**\\
$n$:nnes Fibonaccin luku voidaan ajatella tapojen määränä heittää kaksipuolisella nopalla silmälukujen summaksi $n$. Nopan silmäluvut ovat 1 ja 2, ja heittojen määrää ei ole rajoitettu. Eri permutaatiot ovat sallittuja.

**Todistus**\\
  Jotta olisi selvää, mitä tässä tapahtuu, käymme läpi esimerkin. Luku 3 voidaan heittää seuraavilla tavoilla
(1,1,1), (1,2), (2,1)

Kolmelle ensimmäiselle $n$:n arvolle tavat ovat:

0:  (): $1 = F_0$
1:  (1):  $1 = F_1$
2:  (1,1), (2): $2 = F_2$

Lista jatkuu samalla tavalla. Mutta miten tämä voidaan todistaa?

Luodaan lukujono $G$, jossa $G_n$ kertoo kuinka monella tavalla voidaan heittää $n$ lemman 1 mukaisesti. Pyritään saamaan tälle jokin rekursiivinen muoto. Huomaamme, että tämä onnistuu hyvin luontevasti. Tapoja heittää $n$ tällä tavalla on yhtä monta kuin tapoja heittää $n-1$ lisättynä tapoihin heittää $n-2$. Mistä tämä johtuu? Tulos tulee suoraan siitä, että summaan $n$ voidaan päästä ainoastaan kahdella tavalla, heittämällä 1 tilanteessa $n-1$ tai heittämällä 2 tilanteessa $n-2$. Saamme siis $G_n = G_{n-1} + G_{n-2}$.

Tämä näyttää tutulta. Jos katsomme Fibonaccin lukujen määritelmää, huomaamme samankaltaisuuden. Koska $F_n = F_{n-1} + F_{n-2}$ ja $F_0 = G_0$, $F_1 = G_1$, nämä lukujonot ovat identtisiä.

Mutta mitä hyötyä lemma 1:stä sitten on? Huomaamme, että kaikki kelvolliset silmälukujen 1 ja 2 heittojen määrät ovat yhtälön $2x + y = n$ kokonaislukuratkaisuja, kun $n$ on jokin vakio. Tästä saamme kaikki toimivat määrät, mutta permutaatiot ovat vielä läpikäymättä.

Oletetaan nyt, että olemme heittäneet $x$ kappaletta lukua kaksi ja $y$ kappaletta lukua yksi. Tämähän on vain erillaisten tapojen määrä järjestää kahden numeron lukujono, kun tiedämme paljonko kumpaakin numeroa on.  Vaihtoehtoja on ${ x+y \choose x } = \frac{(x+y)!}{x!\cdot y!}$. Summaamalla tälläiset luvut kaikilla toimivilla $x$ ja $y$, saamme kaikki permutaatioiden määrät eli siis myös Fibonaccin luvun.

Jos kuitenkin katsomme todistettavaa lauseketta, huomaamme, että siellä ei ollut muuttujaa $y$ tai muutenkaan kahta muuttujaa. On kuitenkin helppoa vähentää johtamastamme kaavasta muuttujien määrä yhteen muuttujaan (ja vakioon). Pätee nimittäin selvästi, että jos $2x + y = n$ niin $x + y = n - x$ ja nyt meillä on luvussa ${x+y \choose x}$ yläkerrassa oleva luku esitetty muodossa, missä on vain yksi muuttuja sekä $n$. Lopullinen yksittäinen termi on siis ${n-x \choose x}$.

Ratkaisuja, joissa $x > \frac{n}{2}$ ei ole, sillä $x$ ja $y$ ovat positiivisia kokonaislukuja. Tämän takia meidän täytyy summata vain ensimmäiset $\frac{n}{2}$ termiä. Katsotaan, miltä tämä summa näyttäisi. Haluammme summata kaikki ${n-x \choose x}$, jolloin saamme kaavan $$F_n = \sum\limits_{x\leq \frac{n}{2} } {n-x \choose x }$$

Mutta tämähän on oikea kaava! Olemme siis valmiita.

**4. Motiiveja todistuksen takana**\\
Koska alunperin en yrittänyt todistaa juuri tätä kaavaa, saatoin edetä todistuksessa kiinnostavalta näyttävään suuntaan, ilman pakkoa päästä tiettyyn tulokseen. Keksin siis oikeastaan väitteen todistuksen pohjalta. Todistus on loppujen lopuksi hyvin suoraviivainen, kun on löytänyt yhteyden nopan heittojen ja Fibonaccin lukujen välillä. Sen jälkeen tehtävä on vain vähän kombinatoriikkaa ja kaavan muotoilemista, jotta summa saataisiin todistettavan väitteen muotoon.
