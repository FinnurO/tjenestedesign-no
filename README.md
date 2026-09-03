# Tjenestedesign i offentlig sektor

En norsk, redaksjonelt bearbeidet utgave av [OECD OPSI sin veileder om
tjenestedesign](https://oecd-opsi.org/guide/service-design/) og
verktøykassen [Toolbox for Designing Digital Public
Services](https://oecd-opsi.org/toolkits/toolbox-for-designing-digital-public-services/)
(opprinnelig fra Estland), tilpasset norske lover, aktører og ressurser.
Bygget med [designsystemet.no](https://designsystemet.no/).

**Live:** https://finnuro.github.io/tjenestedesign-no/

> Dette er en **uoffisiell** bearbeiding — ikke en offisiell nettside for
> Digitaliseringsdirektoratet (Digdir), DOGA eller OECD.

> **Laget utelukkende med KI-agenter** (Claude/Claude Code): research,
> oversettelse, tekst, design og kode. Ikke fasitsjekket av et menneske
> utover det som står i denne READMEen — se [Dekning](#dekning) under.

## Innhold

| Side | Sti | Beskrivelse |
|---|---|---|
| Forside | `/` | Hvorfor en norsk utgave, og hva du finner her |
| Guide | `/guide/` | Grunnprinsipper, norsk praksis, hensyn i offentlig sektor, metoder |
| Verktøykasser | `/verktoykasser/` | Katalog over verktøykasser (OECD OPSIs «Toolkit Navigator») |
| Digital verktøykasse | `/verktoykasser/digitale-offentlige-tjenester/` | Sju faser — norsk introduksjon basert på strukturen i Estlands digiriik.eesti.ee |

## Dekning

«Digital verktøykasse» er en introduksjon til **strukturen** i
[digiriik.eesti.ee](https://digiriik.eesti.ee/), ikke en full oversettelse
av innholdet:

- ✅ Alle 7 fasene, riktig rekkefølge og navn
- ✅ Ett nøkkelspørsmål og 2–4 stikkords-verktøy per fase (skrevet av oss)
- ✅ 7 av originalens ~25 navngitte verktøy, forklart i ett avsnitt hver
- ✅ Norske ressurskoblinger per fase (finnes ikke i originalen)
- ❌ De ~25–35 fyldige underartiklene originalen har (én per fase-steg)
- ❌ De resterende ~18 verktøyene i originalens eget verktøybibliotek
- ❌ Seksjonene *Riiklikud juhised*, *Artiklid*, *Teatmik*, *Koostoimeraamistik* og *Riigi IT-majad* fra originalen

Se [issue #1](https://github.com/FinnurO/tjenestedesign-no/issues/1) for
full sjekkliste og fremdrift.

## Teknisk

Rent statisk HTML/CSS/JS — ingen bygg-steg, ingen avhengigheter, ingen
server. Alt som trengs (designsystemet.no sitt CSS, og fontene Inter og
Source Serif 4) er selv-hostet i `assets/`, slik at siden ikke har noen
kjøretidsavhengighet til eksterne CDN-er.

```
├─ index.html                                          Forside
├─ guide/index.html
├─ verktoykasser/index.html
├─ verktoykasser/digitale-offentlige-tjenester/index.html
└─ assets/
   ├─ css/
   │  ├─ vendor/designsystemet.css         (fra @digdir/designsystemet-css, MIT)
   │  ├─ vendor/designsystemet-theme.css   (samme pakke, tema/tokens)
   │  ├─ fonts.css                         (@font-face for selv-hostede fonter)
   │  └─ site.css                          (redaksjonelt CSS-lag, bygger på ds-tokens)
   ├─ fonts/                               (Inter + Source Serif 4, variable, OFL 1.1)
   └─ favicon.svg
```

### Kjøre lokalt

Ingen byggeverktøy nødvendig — server mappa med hva som helst statisk:

```bash
python3 -m http.server 8000
# eller
npx serve .
```

### Oppdatere designsystemet-versjonen

Filene i `assets/css/vendor/` er kopiert fra npm-pakken
[`@digdir/designsystemet-css`](https://www.npmjs.com/package/@digdir/designsystemet-css).
For å oppdatere:

```bash
npm view @digdir/designsystemet-css version   # sjekk nyeste versjon
curl -L "https://cdn.jsdelivr.net/npm/@digdir/designsystemet-css@<versjon>/dist/src/v2/index.min.css" -o assets/css/vendor/designsystemet.css
curl -L "https://cdn.jsdelivr.net/npm/@digdir/designsystemet-css@<versjon>/dist/theme/designsystemet.css" -o assets/css/vendor/designsystemet-theme.css
```

(behold kildehenvisningen øverst i hver fil, og oppdater versjonsnummeret).

### Legge til en ny verktøykasse

Katalogsiden (`verktoykasser/index.html`) har flere kort merket «Kommer».
For å legge til en ny, oversatt verktøykasse: kopier strukturen i
`verktoykasser/digitale-offentlige-tjenester/index.html` (fase-liste med
`<details class="phase">`), lag en ny mappe under `verktoykasser/`, og
oppdater kortet i katalogen samt `sitemap.xml`.

## Lisens

Innholdet er lisensiert under **CC BY-SA 3.0 IGO** — samme lisens som OECD
OPSI selv bruker, se [LICENSE](LICENSE). Vendret kode og fonter har egne
lisenser, se [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).
