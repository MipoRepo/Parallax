# Parallax Scrolling Demo

Tämä projekti esittelee yksinkertaisen **parallax scrolling** -efektin HTML:n ja CSS:n avulla. Sivulla käytetään kerroksittaisia kuvia ja syvyysefektejä luomaan visuaalisesti vaikuttava vierityskokemus ilman JavaScriptiä.

## 🔧 Rakenne

Projekti koostuu kahdesta pääosasta:

- `index.html` – HTML-rakenne ja sisältö
- `styles.css` – ulkoasu ja parallax-efektin määrittely CSS:n avulla

### `index.html`

- `<header>`-elementti sisältää kaksi päällekkäistä kuvaa:
  - `.background` – taustakuva
  - `.foreground` – etualakuva
- `<div class="wrapper">` määrittää vieritettävän näkymän ja siihen liittyvän perspektiivin (`perspective`)
- `<section>` sisältää tekstisisällön, joka vieritetään parallax-elementtien päällä

### `styles.css`

- `.wrapper`:
  - `height: 100vh` – täyttää näkymän korkeuden
  - `overflow-y: auto` – mahdollistaa pystysuuntaisen vierityksen
  - `perspective: 11px` – luo syvyysvaikutelman kolmiulotteiseen näkymään

- `header`:
  - `transform-style: preserve-3d` – säilyttää lasten kolmiulotteisen asettelun
  - `position: relative` – tarvitaan absoluuttisesti sijoitetuille lapsielementeille

- `.background` ja `.foreground`:
  - `position: absolute` – sijoittuvat päällekkäin
  - `transform: translateZ(...) scale(...)` – määrittävät, kuinka "syvällä" tai "lähellä" elementti on
    - `.background`: `translateZ(-70px) scale(4)`
    - `.foreground`: `translateZ(-20px) scale(3)`
  - `z-index: -1` – asettaa kuvat varsinaisen sisällön taakse
  - `object-fit: cover` – varmistaa, että kuvat täyttävät tilansa tyylikkäästi

- `.title`:
  - Suurikokoinen otsikko, joka näkyy kuvien päällä

- `section`:
  - Sisältää vieritettävää tekstiä
  - Tumma tausta ja vaalea fontti selkeää luettavuutta varten

## 💡 Parallax-tekniikka CSS:llä

Parallax-efekti perustuu seuraaviin tekniikoihin:

- **Perspective**: määrittää näkymän "syvyyden", joka vaikuttaa siihen, miten eri syvyyksiin sijoitetut elementit liikkuvat vierityksessä
- **TranslateZ**: siirtää elementtejä lähemmäs tai kauemmas katsojasta
- **Scale**: kompensoi perspektiivin aiheuttamaa pienennystä
- **Transform-style: preserve-3d**: mahdollistaa kolmiulotteisten siirtymien näkymisen oikein

## 🖼 Kuvitus

Kuvien polut (`imgs/header.png` ja `imgs/header2.png`) ovat esimerkinomaisia ja ne tulee lisätä projektin `imgs/`-kansioon.

## 📜 Lisenssi

Tämä projekti on vapaasti käytettävissä oppimistarkoituksiin.
