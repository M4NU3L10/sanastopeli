# 🌍 Sanastopeli

Selainpohjainen sanastopeli, jolla voi harjoitella vieraan kielen sanoja ja artikkeleita. Toimii sekä puhelimella että tietokoneella, ja voidaan asentaa kotinäytölle verkkosovelluksena.

---

## Pelaaminen

Pelissä on neljä pelimuotoa, jotka valitaan ruudun alalaidasta:

### 🪧 Kääntökortit
Näytöllä näkyy sana lähdekielellä. Napauta tai klikkaa korttia kääntääksesi sen ja nähdäksesi käännöksen. Merkitse sitten itse, menikö oikein vai väärin.

**Näppäinoikotiet tietokoneella:**
| Näppäin | Toiminto |
|---------|----------|
| `↑` tai `↓` | Käännä kortti |
| `→` | Merkitse oikein |
| `←` | Merkitse väärin |

### 🏗️ Rakenna
Näytöllä näkyy sana lähdekielellä. Koosta käännös klikkaamalla kirjaimia oikeaan järjestykseen. Artikkeli näytetään valmiina. Vain yksittäiset sanat (3–18 kirjainta) kelpaavat tähän muotoon.

### 🔡 Monivalinta
Näytöllä näkyy sana lähdekielellä. Valitse oikea käännös neljästä vaihtoehdosta.

### ✏️ Kirjoitus
Näytöllä näkyy sana lähdekielellä. Kirjoita käännös vastauskenttään ja paina *Tarkista* tai Enter.

- Täysin oikein (oikea artikkeli + sana) → täydet pisteet
- Sana oikein mutta artikkeli puuttuu tai on väärä → piste, mutta muistutus oikeasta muodosta
- Sana väärin → ei pistettä

Kirjoitusmuodossa on pikanapit saksalaisille erikoismerkeille: **ä ö ü ß / Ä Ö Ü ẞ**

---

## Asetukset (⚙️ vasemmassa yläkulmassa)

- Vaihda taustaväri viidestä eri teemasta (Kosminen, Merivirta, Auringonlasku, Metsä, Kristalli)
- Vaihda käännössuunta: esim. suomi → saksa tai saksa → suomi
- Kesken pelin: lopeta peli *Lopeta peli* -napilla

---

## Pelin jälkeen

Kun kaikki sanat on käyty läpi, näet tuloksen ja prosenttiosuuden. Jos vastasit johonkin väärin, voit harjoitella pelkät väärät sanat uudelleen samalla pelimuodolla.

---

## Asentaminen kotinäytölle

### iPhone / iPad (Safari)
Automaattinen asennuskehotus ei ole mahdollinen Applen rajoitusten vuoksi. Lisää manuaalisesti:
1. Avaa sivu Safarissa
2. Paina **⎋ Jaa** → **Lisää Koti-valikkoon**

### Android (Chrome)
Chrome näyttää asennuskehotteen automaattisesti, tai se löytyy selaimen valikosta.

---

## Sanojen muokkaaminen

Avaa tiedosto `index.html` tekstieditorilla (esim. Notepad, VS Code). Etsi kohta:

```js
const VOCAB = [
```

Jokainen sana on oma rivinsä:

```js
{ source:"suomenkielinen sana", target:"der Beispiel", article:"der", word:"Beispiel" },
```

| Kenttä | Selitys |
|--------|---------|
| `source` | Lähdekielen sana tai lause, esim. `pöytä` |
| `target` | Kohdekielen sana artikkelin kanssa, esim. `der Tisch` |
| `article` | Pelkkä artikkeli (`der`, `die`, `das`) tai `null` jos ei ole |
| `word` | Kohdekielen sana ilman artikkelia, esim. `Tisch` |

**Sana artikkelilla:**
```js
{ source:"pöytä", target:"der Tisch", article:"der", word:"Tisch" },
```

**Sana ilman artikkelia (verbi, lause tms.):**
```js
{ source:"nukkua", target:"schlafen", article:null, word:"schlafen" },
```

> **Huom.** Rakenna-pelimuoto valitsee automaattisesti vain sanat, joissa `word`-kenttä sisältää pelkkiä kirjaimia (3–18 kpl) – ei välejä tai välimerkkejä.

---

## Kielen vaihtaminen

Etsi tiedoston alusta:

```js
const LANG = {
  sourceLanguage:  'Suomi',
  targetLanguage:  'Saksa',
  sourceFlagEmoji: '🇫🇮',
  targetFlagEmoji: '🇩🇪',
};
```

Vaihda kielten nimet ja liput. Esimerkiksi ranskaa varten:

```js
const LANG = {
  sourceLanguage:  'Suomi',
  targetLanguage:  'Ranska',
  sourceFlagEmoji: '🇫🇮',
  targetFlagEmoji: '🇫🇷',
};
```
