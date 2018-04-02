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

### Luonnoksen tekeminen ja muokkaaminen

Luo hakemistoon `_drafts` uusi tiedosto, jonka nimi on esimerkiksi
`oma-hieno-kirjoitus.md`, joka sisältää otsikon tai joitakin URLiin
sopivia sanoja siitä.
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
Githubiin, odota muutama minuutti (seuraa tilannetta [Travisista][travis])
ja kun uusin build on vihreänä, luonnoksen pitäisi löytyä valmiiden postausten
yläpuolelta osoitteesta https://blog-drafts.matematiikkakilpailu.fi/posts/.
Jos build on punaisena, sen lokitiedostoista saattaa löytyä virheilmoitus,
joka kertoo mikä meni pieleen. Tätä iteroimalla voit korjata rauhassa
mahdolliset muotoiluvirheet ennen julkaisua.

Tiedoston muokkauksessa saattaa auttaa [Prose.io][prose], jossa on
esikatselu, mutta se ei tue kaavoja.

Edistyneille komentorivikäyttäjille: voit tehdä esikatselun paikallisesti
asentamalla Rubyn ja Bundlerin ja komentamalla

```
bundle install
bundle exec jekyll serve
```

### Julkaiseminen

Kun teksti on valmis, siirrä tiedosto hakemistosta `_drafts`
hakemistoon `_posts` ja muuta samalla sen nimeksi
`2018-04-02-oma-hieno-kirjoitus.md`, jossa on alussa päivämäärä
muodossa vuosi-kuukausi-päivä. Siirto onnistuu näppärästi käyttämällä
askelpalautinta (backspace) Githubin tiedostonimikentän alussa (kuva
on linkki videoon):

[![Miten tiedoston nimi muutetaan][gfy-kuva]][gfy-video]


[gh]: https://guides.github.com/
[md]: https://commonmark.org/help/
[math]: https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference
[prose]: https://prose.io
[travis]: https://travis-ci.org/matematiikkakilpailut/blog/builds
[gfy-kuva]: https://thumbs.gfycat.com/RipeTallAtlanticspadefish-poster.jpg
[gfy-video]: https://gfycat.com/RipeTallAtlanticspadefish

## Detaljeja

### Tiivistelmät

Kirjoitusten luetteloon tulee kirjoituksesta ote ensimmäiseen tyhjään
riviin asti. Jos tämä ei edusta kirjoitusta sopivasti, on pari vaihtoehtoa:

- lisää alkurivien joukkoon `excerpt_separator: "<!--jatkuu-->"` ja sijoita
  sopivaan kohtaan kirjoitustasi merkkijono `<!--jatkuu-->`
- lisää alkurivien joukkoon

```
excerpt: >
  Tähän voit kirjoittaa sopivasti muotoillun tiivistelmän,
  vaikka usealle riville jaettuna kunhan kaikkia rivejä on
  sisennetty saman verran.
```

### Omat matemaattiset operaattorit

Kaavoissa on tapana käyttää muuttujille kursiivia ja operaattoreille
”tavallisia” kirjasimia. TeXissä ja MathJaxissa tavalliset peräkkäin
kirjoitetut kirjaimet kuten ”pyj” tuottavat huonosti välistettyä
kursiivitekstiä, jonka merkitys olisi että muuttujat <i>p</i>, <i>y</i> ja <i>j</i>
kerrotaan keskenään. Parempia tapoja kirjoittaa ”pyj” on erilaisia,
mutta kaikkein näppärin on ehkä määritellä omat `\pyj`- ja `\syt`-operaattorit:

```
<div class="hidden">
$\newcommand{\pyj}{\mathop{\rm pyj}}\newcommand{\syt}{\mathop{\rm syt}}$
</div>
```

Useille tavallisille funktioille määritelmät on tehty valmiiksi:
`\sin`, `\cos`, `\tan`, `\log` jne.
Kongruenssin modulin voi kirjoittaa näin: `$a^{\lambda(n)} \equiv 1 \pmod{n}$`.

### Jakorelaatio

Väittämä ”<i>a</i> jakaa <i>b</i>:n” lienee kätevintä kirjoittaa `$a \mid b$`.
Tämän negaatio taas on `$a \nmid b$`.

### Binomikertoimet ja jakoviivat

TeXin syntaksi `{a \choose b}`, `{a \over b}` tuottaa vaikeuksia.
Kirjoita mieluummin `\binom{a}{b}`, `\frac{a}{b}`.

### Pienempi kuin

Pienempi kuin -merkillä on erityismerkitys HTML:ssä ja siten Markdownissa.
Sitä voi silti usein käyttää kaavoissa, mutta jos tulee ongelmia, kirjoita
sen sijasta `\lt`.
