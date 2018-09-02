---
layout: post
author: "Olli Järviniemi"
title: "Algebrallisista luvuista ja vektoriavaruuksista"
math: true
excerpt_separator: "<!--jatkuu-->"

---

Tässä postauksessa esitetään yksi todistus sille, miksi kahden algebrallisen luvun summa/tulo on myös algebrallinen. Tämän todistamiseksi määritellään vektoriavaruus ja kanta.

<!--jatkuu-->

**Määritelmä**

Lukua $\alpha$ sanotaan algebralliseksi, jos se on jonkin kokonaislukukertoimisen (ei-vakion) polynomin nollakohta. Ekvivalentti määritelmä on, että $\alpha$ on jonkin rationaalikertoimisen polynomin nollakohta.


Todistus perustuu vektoriavaruuksiin ja niiden kantoihin. Tekstin rakenne on seuraava:

1. Kunnan määritelmä
2. Esimerkki vektoriavaruudesta
3. Vektoriavaruuden määritelmä
4. Esimerkki vektoriavaruudesta
5. Esimerkki kannasta
6. Kannan määritelmä
7. Esimerkki kannasta
8. Väitteen todistus
9. Harjoitustehtävä

Ne, jotka tietävät ennestään vektoriavaruuksien ja kantojen perusteet, voivat edetä suoraan väitteen todistukseen. Muussa tapauksessa kannattaa keskittyä koko postaukseen, sillä vektoriavaruudet ja kunnat ovat kohtalaisen yleisiä käsitteitä.

**Määritelmä (kunta)**

Olkoon $K$ joukko, ja $\cdot$ sekä $+$ operaatioita. Sanotaan, että $(K, \cdot, +)$ on kunta (tai $K$ on kunta, jos operaatioiden määrittelyt ovat selviä kontekstista), jos seuraavat ehdot pätevät:

1. Kaikilla $a, b \in K$ pätee $a + b = b + a$ ja $a\cdot b = b \cdot a$.
2. On olemassa sellainen $0 \in K$, jolla $a + 0 = a$ kaikilla $a \in K$. Vastaavasti, on olemassa sellainen $1 \in K$, jolla $1 \cdot a = a$ kaikilla $a \in K$.
3. Kaikilla $a, b, c \in K$ pätee $a + (b + c) = (a + b) + c$ ja $a \cdot (b \cdot c) = (a \cdot b) \cdot c$
4. Kaikilla $a \in K$ on olemassa sellainen $b \in K$, jolla $a + b = 0$. Vastaavasti, kaikilla $a \in K, a \neq 0$ on olemassa sellainen $b \in K$, jolla $a \cdot b = 1$.
5. Kaikilla $a, b, c \in K$ pätee $a(b+c) = ab + ac$.

Esimerkiksi rationaalilukujen joukko on kunta, kun $\cdot$ ja $+$ määritellään tavallisesti. Samoin reaali- ja kompleksiluvut ovat kunta. Huomaa, että kokonaisluvut eivät ole kunta, koska ehto 4 ei päde kertolaskulle: esimerkiksi luvulla $2$ ei ole olemassa sellaista kokonaislukua $b$, jolla $2b = 1$.

**Huomautus**

Tässä postauksessa kaikkein tärkein esimerkki kunnista on rationaalilukujen kunta $\mathbb{Q}$, ja kannattaa monessa tilanteessa ajatellan kunnan $K$ sijasta helppoa esimerkkiä $\mathbb{Q}$. Ehdot ovat lisäksi loppujen lopuksi hyvin intuitiivisia, eli ei kannata liikaa ajatella, että ne pitäisi "opetella ulkoa". Jos mietit kysymystä "kuuluuko ehto x kunnan määritelmiin", intuitiivisin vastaus on todennäköisesti oikein.

**Huomautus**

Ehdoille on annettu omat "nimensä". Ehtoa 1 kutsutaan kommutatiivisuudeksi, ehtoo 2 on neutraalialkion olemassaolo, 3 on assosiatiivisuus, 4 on käänteisalkion olemassaolo, 5 on osittelulaki.

**Huomautus**

On olemassa muitakin mielenkiintoisia algebrallisia rakenteita kuin kunnat. Esimerkiksi unohtamalla ehdon 4 operaatiolle $\cdot$ (mutta säilyttämällä sen opreaatiolle $+$) saadaan ns. renkaat. Kokonaisluvut ovat rengas. Joissain lähteissä jätetään pois ehto 1 operaatiolle $\cdot$, mikä myös yleistää kunnan määritelmää (esimerkiksi kääntyvät matriisit ovat tällä laajennetulla määritelmällä kunta). Tässä postauksessa emme kuitenkaan tee näin.

**Huomautus**

Jos $K$ on reaalilukujen osajoukko, tässä postauksessa $\cdot$ ja $+$ määritellään kuten tavallinen kertolasku ja yhteenlasku.



Ennen kuin määritellään vektoriavaruus, otetaan esimerkki vektoriavaruudesta.

**Esimerkki (vektoriavaruus)**

Olkoon $\mathbb{R}$ reaalilukujen joukko, ja olkoon $V$ kaksiulotteisen tason vektorien joukko. $V$:n alkioita voidaan kertoa mielivaltaisilla reaaliluvuilla, vektoreita voidaan laskea yhteen, ja $(a + b)v = av + bv$ kaikilla $a, b \in \mathbb{R}, v \in V$. $V$:n alkioita ei kuitenkaan suoraan voi kertoa keskenään (paitsi ehkäpä pistetulolla, mutta ei välitetä tästä). Sanomme, että $V$ on $R$-vektoriavaruus.

**Määritelmä (vektoriavaruus)**

Olkoon $(K, \cdot, +)$ kunta (esimerkiksi rationaaliluvut). Olkoon $V$ jokin joukko, jolla on operaatio $\bigoplus$. Lisäksi olkoon $\bigodot$ operaatio, joka kuvaa jokaiselle parille $(a, v)$ vektorin $w$, missä $a \in K, v, w \in V$. Sanotaan, että $V$ (eli $(V, \bigoplus)$) on $K$-vektoriavaruus, jos seuraavat ehdot pätevät:

1. $(V, \bigoplus)$ toteuttaa kunnan määritelmistä 1-4 ne, jotka koskevat operaatiota $+$.

2. $(a + b) \bigodot v = (a \bigodot v) \bigoplus (b \bigodot v)$, kaikilla $a, b \in K, v \in v$.

3. $a \bigodot (b \bigodot v) = (a \cdot b) \bigodot v$, kaikilla $a, b \in K, v \in v$.

4. $1 \bigodot v = v$ kaikilla $v \in V$, missä $1$ on $K$:n kertolaskun neutraalialkio,

5. $a \bigodot (v \bigoplus w) = (a \bigodot v) \bigoplus (a \bigodot w$).

**Huomautus**

Usein operaatiot $\bigoplus$ ja $\bigodot$ ovat hyvin samanlaisia kuin operaatiot $+$ ja $\cdot$. Nyrkkisääntö: jos $\bigoplus$ tai $\bigodot$ valitaan jollain muulla kuin kaikkein selkeimmällä tavalla, se mainitaan erikseen.


Jälleen, määritelmät ovat intuitiivisia, vaikkeikaan ehkä niin luonnollisia kuin kunnan tapauksessa. Otetaan vielä toinen esimerkki.



**Esimerkki (vektoriavaruus)**

Olkoon $\mathbb{Q}$ rationaalilukujen joukko, ja olkoon $V$ funktioiden $f : \mathbb{Q} \to \mathbb{Q}$ joukko. Voimme määritellä $f \bigodot g$ luonnollisesti funktioksi $h$, jolla $h(a) = f(a) + g(a)$ kaikilla $a \in \mathbb{Q}$. Vastaavasti määritellään kertolasku rationaaliluvulla: $V$:n alkio $a \bigodot f$ on se funktio $h$, jolla $h(b) = a \cdot f(b)$ kaikilla $b \in \mathbb{Q}$.

On helppoa todistaa, että $V$ on $\mathbb{Q}$-avaruus käymällä jokaisen tarvittavan ehdon läpi (tämän pitäisi myös olla melko intuitiivista). Huomaa, että jälleen ei ole määritelty, millainen olisi "kertolasku" $V$:n alkioiden välillä, eikä tarvitsekaan.


Kuten edellä, käydään ensin läpi esimerkki vektoriavaruuden kannasta ennen määritelmää.

**Esimerkki (kanta)**

Olkoon $V$ joukko, joka sisältää luvut muotoa $a + b\sqrt{2}$, missä $a, b \in \mathbb{Q}$. Määritellään yhteenlasku $V$:n alkioiden välillä samalla tavalla kuin yhteenlasku reaaliluvuille. Tällöin $V$ on $\mathbb{Q}$-vektoriavaruus, kun määrittelemme vektoriavaruuden määritelmässä esiintyvän operaation $\bigodot$ kuten kertolaskun reaaliluvuilla (ei kovin yllättäen).

$\{1, \sqrt{2}\}$ on kanta vektoriavaruudelle $V$, koska jokainen $V$:n alkio voidaan kirjoittaa muodossa $a \cdot 1 + b \cdot \sqrt{2}$, missä $a$ ja $b$ ovat kunnan $\mathbb{Q}$ alkioita. Tämä ei ole ainoa kanta, esimerkiksi $\{3, 1 + 2\sqrt{2} \}$ on myös kanta, koska jokainen $V$:n alkio voidaan kirjoittaa muodossa $a \cdot 3 + b \cdot (1 + 2\sqrt{2})$, missä $a, b \in \mathbb{Q}$. Tämä kanta ei ole


**Määritelmä (kanta)**

Olkoon $V$ $K$-vektoriavaruus. Sanotaan, että $V$:n alkiot $\{v_1, v_2, \ldots , v_n \}$ ovat vektoriavaruuden $V$ kanta, jos seuraavat kaksi ehtoa pätevät:

1. Jokainen $w \in V$ voidaan muodossa $a_1v_1 + a_2v_2 + \ldots + a_nv_n$, missä $a_i \in K$, eli siis $w = a_1v_1 + \ldots + a_nv_n$.

2. Jos joukosta $\{v_1, v_2, \ldots , v_n \}$ poistaa minkä tahansa alkion, ei ehto 1 enää päde. Tämä on ekvivalenttia (miksi?) sen kanssa, että jokin $v_i$ voidaan esittää muodossa $a_1v_1 + a_2v_2 + \ldots + a_{i-1}v_{i-1} + a_{i+1}v_{i+1} + \ldots + a_nv_n$, missä $a_i \in K$.

**Huomautus**

Ehto 2 käytännössä tarkoittaa sitä, että kanta ei sisällä "turhia" alkioita.

**Huomautus**

Näillekin ehdoille on omat nimensä. Ehtoon 1 viitataan sanomalla, että vektorit $v_1, \ldots , v_n$ virittävät vektoriavaruuden $V$. Lisäksi sanotaan, että $w$ voidaan esittää vektorien $v_1, \ldots , v_n$ lineaarikombinaationa. Ehtoa 2 nimitetään sanomalla, että vektorit $v_1, v_2, \ldots , v_n$ ovat lineaarisesti riippumattomia.


**Esimerkki (kanta)**

Olkoon $S$ niiden enintään toisen asteen polynomien joukko (myös vakiopolynomit), joiden kertoimet ovat rationaalilukuja. Tällöin $S$ on $\mathbb{Q}$-vektoriavaruus, ja sillä on kanta $\{1, x, x^2\}$. On helppoa nähdä, että molemmat ehdot toteutuvat. Jälleen, kanta ei ole uniikki, sillä esimerkiksi $\{x^2 - 1, x^2, x\}$ on myös kanta.


**Todistus (kahden algebrallisen luvun summa on algebrallinen)**

Olkoot $\alpha$ ja $\beta$ joidenkin kahden polynomin $P, Q$ nollakohtia, missä $P$ ja $Q$ ovat kokonaislukukertoimisia. Olkoon $n = \deg(P)$ ja $m = \deg(Q)$. Olkoon $V$ se \mathbb{Q}-vektoriavaruus, joka sisältää kaikki luvut muotoa $q_0 + q_1\alpha + q_2\alpha^2 + \ldots $, missä $q_i \in \mathbb{Q}$. On selvää, että $\{1, \alpha, \alpha^2, \ldots \}$ virittää $V$:n, mutta tämä ei ole kanta: luku $\alpha^n$ voidaan esittää lukujen $1, \alpha, \ldots , \alpha^{n-1}$ avulla. Vastaavasti millä tahansa $k \ge n$ luku $\alpha^k$ voidaan esittää lukujen $1, \alpha, \ldots , \alpha^{n-1}$ lineaarikombinaationa. Tämän vuoksi $\{1, \alpha, \alpha^2, \ldots \alpha^{n-1}\}$ virittää vektoriavaruuden $V$. Tämäkään ei vielä välttämättä ole kanta, mutta ei välitetä siitä. Määritellään $W$ vastaavasti luvulle $\beta$, jolloin $\{1, \beta, \ldots , \beta^{m-1} \}$ virittää $W$:n.

Olkoon nyt $U$ niiden lukujen joukko, jotka voidaan esittää termien muotoa $q \alpha^i \beta^j$, missä $q \in \mathbb{Q}$, $i, j \in \mathbb{Z_{\ge 0}}$. Tämä $U$ voidaan virittää lukujoukolla $B$, joka sisältää luvut muotoa $\alpha^i \beta^j$, missä $i < n$ ja $j < m$. Miksi? On selvää, että jos unohdamme ehdon $i < n$, $j < $m, niin väite pätee. Jos $i \ge n$, voidaan luku $\alpha^i\beta^j$ kirjoittaa lukujen $\alpha^k\beta^j$ lineaarikombinaationa, missä $0 \le k < n$. Tämän takia luvut muotoa $\alpha^i\beta^j$, missä $i \ge n$ tai $j \ge m$, ovat "turhia", sillä ne voidaan esittää em. luvuilla.

Osoitetaan nyt, että $\alpha + \beta$ on algebrallinen. Olkoon $T$ se $\mathbb{Q}$-vektoriavaruus, joka sisältää luvut muotoa $(\alpha + \beta)^i$, $i \in \mathbb{Z_{\ge 0}}$. Tämä $T$ on $U$:n osajoukko, joten $T$:n voi virittää äärellisellä määrällä (oikeastaan, $nm$ kappalella) alkioita. Tämä tarkoittaa, että $(\alpha + \beta)^{nm}$, voidaan esittää luvun $\alpha + \beta$ pienempien potenssien lineaarikombinaationa, eli $(\alpha + \beta)^k = q_0 + q_1(\alpha + \beta)^1 + \ldots + q_{nm-1}(\alpha + \beta)^{nm - 1}$ jollain rationaaliluvuilla $q_i$. Tämä antaa suoraan polynomin, jonka nollakohtana on $\alpha + \beta$. Siis $\alpha + \beta$ on algebrallinen.


**Huomautus**

Jos todistuksen viimeisen kappaleen termit $\alpha + \beta$ korvaa termeillä $\alpha \beta$, on meillä valmis todistus sille, että $\alpha \beta$ on algebrallinen.



**Harjoitustehtävä**

1. Olkoon $\alpha \neq 0$ algebrallinen. Osoita, että $\frac{1}{\alpha}$ on algebrallinen. Tämä todistaa, että algebrallisten lukujen joukko on kunta.

2. Sanotaan, että algebrallinen luku $\alpha$ on algebrallinen kokonaisluku, jos on olemassa sellainen kokonaislukukertoiminen polynomi $P$, jonka nollakohta $\alpha$ on, ja $P$:n korkeimman asteen termin kerroin on 1. Esimerkiksi $\sqrt{2}$ on algebrallinen kokonaisluku, koska se on polynomin $x^2 - 2$ nollakohta, mutta $\frac{\sqrt{2}}{2}$ ei kuitenkaan ole algebrallinen kokonaisluku. Osoita, että kaikilla algebrallisilla luvuilla $\alpha$ on olemassa sellainen $n \in \mathbb{Z_{> 0}}$, jolla $n\alpha$ on algebrallinen kokonaisluku.
