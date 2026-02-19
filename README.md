# 🎮 Sanastopeli

Selainpohjainen sanastopeli, jolla voi harjoitella vieraan kielen sanoja ja artikkeleita. Toimii sekä puhelimella että tietokoneella.

---

## Pelaaminen

Pelissä on kaksi pelimuotoa, jotka valitaan ruudun alalaidasta:

**✏️ Kirjoitus**
Näytöllä näkyy sana lähdekielellä. Kirjoita käännös vastauskenttään ja paina *Tarkista* tai Enter. Saat täydet pisteet oikeasta vastauksesta. Jos sana on oikein mutta artikkeli puuttuu tai on väärin, saat silti pisteen – mutta peli muistuttaa oikeasta muodosta.

**🎯 Monivalinta**
Näytöllä näkyy sana lähdekielellä. Valitse oikea käännös neljästä vaihtoehdosta.

### Asetukset (⚙️ vasemmassa yläkulmassa)
- Vaihda taustaväri viidestä eri teemasta
- Vaihda käännössuunta: esim. suomi → saksa tai saksa → suomi

### Pelin jälkeen
Kun kaikki sanat on käyty läpi, näet tuloksen. Jos vastasit johonkin väärin, voit harjoitella pelkät väärät sanat uudelleen.

---

## Sanojen muokkaaminen

Avaa tiedosto `index.html` tekstieditorilla (esim. Notepad, VS Code). Etsi kohta jossa lukee:

```
const VOCAB = [
```

Jokainen sana on oma rivinsä, muodossa:

```js
{ source:"suomenkielinen sana", target:"der Beispiel", article:"der", word:"Beispiel" },
```

| Kenttä | Selitys |
|--------|---------|
| `source` | Lähdekielen sana tai lause, esim. `pöytä` |
| `target` | Kohdekielen sana artikkelin kanssa, esim. `der Tisch` |
| `article` | Pelkkä artikkeli (`der`, `die`, `das`) tai `null` jos ei ole |
| `word` | Kohdekielen sana ilman artikkelia, esim. `Tisch` |

**Esimerkki uuden sanan lisäämisestä:**
```js
{ source:"pöytä", target:"der Tisch", article:"der", word:"Tisch" },
```

Jos sanalla ei ole artikkelia (esim. verbi tai lause):
```js
{ source:"nukkua", target:"schlafen", article:null, word:"schlafen" },
```

### Kielen vaihtaminen

Etsi tiedoston alusta kohta:

```js
const LANG = {
  sourceLanguage:   'Suomi',
  targetLanguage:   'Saksa',
  sourceFlagEmoji:  '🇫🇮',
  targetFlagEmoji:  '🇩🇪',
};
```

Vaihda kielten nimet ja liput haluamaksesi, esim. ranskaa varten:

```js
const LANG = {
  sourceLanguage:   'Suomi',
  targetLanguage:   'Ranska',
  sourceFlagEmoji:  '🇫🇮',
  targetFlagEmoji:  '🇫🇷',
};
```
