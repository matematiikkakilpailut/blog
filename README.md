matematiikkakilpailut.fi blog
=============================

## Kirjoittajat

Kirjoittajina on joitakin matematiikkavalmennuksen osallistujia.

## Miten voin kirjoittaa blogiin?

Ensiksi: muista, että Internetiin kirjoitettuja juttuja ei koskaan
saa kokonaan poistettua. Varsinkin Github tallentaa historiaa
vaikka tiedoston poistaisi, samoin erilaiset arkistosivustot.
Älä loukkaa ketään, älä julkaise henkilötietoja luvatta äläkä
riko mitään lakeja.

**Vaihtoehto 1:** Lähetä kirjoituksesi Jouni Seppäselle <jks@iki.fi>
ja jää odottamaan.

**Vaihtoehto 2:** Rekisteröidy Githubin käyttäjäksi ja lähetä 
käyttäjätunnuksesi Jouni Seppäselle. Tutustu [Githubin käyttöön][gh],
[Markdown-syntaksiin][md] ja [Mathjax-syntaksiin][math].
Luo hakemistoon `_posts` uusi tiedosto, jonka nimi on esimerkiksi
`2018-03-17-oma-hieno-kirjoitus.md` mikä sisältää päivämäärän
ja otsikon (tai joitakin sanoja otsikosta).
Tiedoston alkuun tulee rivit

```
---
layout: post
title: "Tähän otsikko"
author: "Kirjoittajan Nimi"
math: true
---
```

Viimeisen rivin voit jättää pois, jos et käytä kaavoja.  Tämän
alukkeen perään kirjoita artikkelisi Markdownilla.  Lähetä tiedosto
Githubiin, odota noin minuutti, lataa blogi selaimella ja korjaa
nopeasti mahdolliset muotoiluvirheet.  Tiedoston muokkauksessa saattaa
auttaa [Prose.io][prose], jossa on esikatselu, mutta se ei tue
kaavoja.

Edistyneille komentorivikäyttäjille: voit tehdä esikatselun paikallisesti
asentamalla Rubyn ja Bundlerin ja komentamalla

```
bundle install
bundle exec jekyll serve
```


[gh]: https://guides.github.com/
[md]: https://commonmark.org/help/
[math]: https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference
[prose]: https://prose.io
