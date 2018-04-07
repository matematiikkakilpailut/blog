---
layout: post
title: "Kombinatorinen tehtävä"
author: "Jouni Seppänen"
math: true
---

**Tehtävä:** Konvehtirasiassa on 36 paikkaa ja konvehteja on 10
erilaista.  Kuinka monta erilaista rasiaa voidaan tehdä, kun halutaan
että jokaisessa rasiassa on ainakin yksi konvehti kutakin laatua?
Konvehtien järjestyksellä rasiassa ei ole väliä, vain kunkin
konvehtilaadun lukumäärällä.

**Ratkaisu:** Sijoitellaan vierekkäin konvehtirasian 36
paikkaa. Asetetaan joihinkin 10 paikkaan 10 konvehtia järjestyksessä
vasemmalta oikealle $1, 2, \dots, 10$. Aika moni paikka jää vielä
tyhjäksi, mutta sovitaan, että täytetään kunkin konvehdin oikealle
puolelle jääneet tyhjät paikat tällä samalla konvehdilla. Konvehti 1
on pakko asettaa vasemmanpuoleiseen paikkaan, mutta muut konvehdit voi
asetella vapaasti. Jokaisella asettelutavalla saadaan tehtävän
mielessä erilainen rasia, ja toisaalta jokainen mahdollinen rasia
vastaa jotain tällaista asettelua. Koska konvehdin 1 paikka on kiinteä
mutta muut konvehdit voi asetella vapaasti, asettelutapoja on
$\binom{35}{9}$.

