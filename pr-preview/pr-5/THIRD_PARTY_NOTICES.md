# Tredjepartslisenser

Dette repoet er lisensiert under CC BY-SA 3.0 IGO (se [LICENSE](LICENSE)),
med unntak av følgende vendret innhold:

## designsystemet.no

- **Filer:** `assets/css/vendor/designsystemet.css`, `assets/css/vendor/designsystemet-theme.css`
- **Kilde:** [`@digdir/designsystemet-css`](https://www.npmjs.com/package/@digdir/designsystemet-css) v1.21.0
- **Opphav:** Digitaliseringsdirektoratet (Digdir) — <https://designsystemet.no/>, <https://github.com/digdir/designsystemet>
- **Lisens:** MIT

Filene er kopiert uendret inn i repoet for at nettstedet ikke skal ha en
kjøretidsavhengighet til en ekstern CDN. Oppdater ved å hente en nyere
versjon fra npm og erstatte filene.

## Inter (font)

- **Fil:** `assets/fonts/Inter-variable-latin.woff2`
- **Opphav:** Rasmus Andersson m.fl. — <https://rsms.me/inter/>
- **Lisens:** SIL Open Font License 1.1

## Source Serif 4 (font)

- **Fil:** `assets/fonts/SourceSerif4-variable-latin.woff2`
- **Opphav:** Adobe — <https://github.com/adobe-fonts/source-serif>
- **Lisens:** SIL Open Font License 1.1

Begge fontfilene er hentet i variabel-font-format (latin-subsett) via Google
Fonts og selv-hostet i dette repoet, se `assets/css/fonts.css`.

## Kildemateriale (ikke kode, men grunnlaget for innholdet)

- **OECD OPSI — Service Design-guiden**: <https://oecd-opsi.org/guide/service-design/> — lisensiert CC BY-SA 3.0 IGO av OECD.
- **Toolbox for Designing Digital Public Services**: <https://oecd-opsi.org/toolkits/toolbox-for-designing-digital-public-services/>, opprinnelig utviklet av Estlands Kommunikasjons- og økonomidepartement (<https://digiriik.eesti.ee/>), merket «CC Public domain» i OECD OPSI sin katalog.

Tekstene i `guide/`, `verktoykasser/` og på forsiden er skrevet på nytt på
norsk med utgangspunkt i strukturen til disse kildene, ikke oversatt
maskinelt eller kopiert ord for ord.
