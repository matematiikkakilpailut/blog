---
layout: post
author: "Joonatan Honkamaa"
title: "Catalanin lukujen yleistys"
math: true
excerpt_separator: "<!--jatkuu-->"

---

Tässä postauksessa käydään läpi eräs Suomen loppukilpailutehtävä, joka osoittautuu [Catalanin lukujen](https://blog.matematiikkakilpailut.fi/2018/03/29/Catalanin-luvut.html) yleistykseksi.


**MAOL:n loppukilpailu 2014, Tehtävä 3**

Pisteet $P = (a, b)$ ja $Q = (c, d)$ ovat $xy$-tason ensimmäisessä neljänneksessä, ja $a, b, c$ sekä $d$ ovat kokonaislukuja, joille $a<b, a<c, b<d$ ja $c<d$. Reitti pisteestä $P$ pisteeseen $Q$ on positiivisten koordinaattiakselien suuntaisista, yksikön pituisista askelista muodostuva murtoviiva, ja sallittu reitti on reitti, joka ei leikkaa eikä kosketa suoraa $x = y$. Montako sallittua reittiä on?


<!--jatkuu-->


Tehtävänannon ymmärtämisen jälkeen kannattaa ensin miettiä tehtävään ratkaisua. Ensin kannattaa yrittää määrittää kaikkien reittien määrä. Myös oikean vastauksen arvaileminen on hyvä tapa lähestyä tehtävää, vaikka ei todistusta keksisikään.

**Ratkaisu 1 (malliratkaisu)**

Tämän ratkaisun ymmärtämistä auttaa ja tehtävän mielenkiintoisuutta lisää, jos tuntee Catalanin luvut, koska osoittautuu, että tehtävän asetelma on oikeastaan niiden yleistys.

Asetelmaa kannattaa ajatella suorakulmiona, jonka vasemmasta alakulmasta tulee päästä oikeaan yläkulmaan siten, että oikeasta alakulmasta on lohkaistu pois alue, jolle ei saa mennä. Unohdetaan nyt pois lohkaistu alue hetkeksi. Yhteensä askelia matkalla kulmasta kulmaan on $n=(c-a)+(d-b)$ kappaletta. Näistä $k=(d-b)$ on ylöspäin. Voimme ottaa nämä askeleet ylöspäin milloin vain haluamme, joten mahdollisia reittejä on nyt

$${n \choose k} = {c-a+d-b \choose d-b} $$
kappaletta.

Asetelmaa tarkastelemalla huomataan, että tämä vastaus on oikea vastaus myös koko tehtävään, jos $c<b$. Oletetaan sitten, että $b \le c$.

