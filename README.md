# Visie op Nederland

Website van [visieopnederland.nl](https://visieopnederland.nl). Gebouwd met Jekyll; GitHub Pages bouwt en publiceert de site automatisch zodra er iets op `main` wordt gezet (meestal binnen 1–2 minuten online).

## Een nieuw artikel toevoegen

1. Maak in de map `_artikelen` een nieuw bestand, bijvoorbeeld `_artikelen/zorg-in-de-regio.md`.
   De bestandsnaam wordt het webadres: `visieopnederland.nl/artikelen/zorg-in-de-regio/`.
   Gebruik kleine letters en streepjes, geen spaties.
2. Zet bovenaan dit blok en vul het in:

```markdown
---
title: "Titel van het artikel"
date: 2026-11-01
thema: bestuur
samenvatting: "Eén of twee zinnen die op de kaart en in Google verschijnen."
icoon: document
bronnen:
  - titel: "CBS – Bevolkingsontwikkeling 2025"
    url: "https://www.cbs.nl/..."
  - titel: "Rapport zonder link"
    toelichting: "Ministerie van BZK, 2025, p. 12"
---

Hier begint de tekst. Gewone alinea's scheid je met een lege regel.

## Tussenkop

Een **vetgedrukt** woord, een *schuin* woord en een [link](https://voorbeeld.nl).
```

3. Zet het bestand op GitHub (uploaden via de website of laat Claude het pushen).

Daarna worden **automatisch** bijgewerkt: de homepage (3 nieuwste artikelen), de balk bovenaan ("Nieuw: …"), het archief op `/artikelen/`, de "Lees ook"-suggesties en `sitemap.xml`.

### Velden

| Veld | Verplicht | Uitleg |
|---|---|---|
| `title` | ja | Titel; ook de paginatitel in Google. |
| `date` | ja | Publicatiedatum (`JJJJ-MM-DD`). Bepaalt de volgorde: nieuwste eerst. Een datum in de toekomst verschijnt pas na de eerstvolgende publicatie op of na die datum. |
| `thema` | ja | Korte naam uit `_data/themas.yml`: `bestuur`, `media` of `toekomst`. |
| `samenvatting` | ja | Korte samenvatting voor kaarten en de meta-omschrijving. |
| `icoon` | nee | Een naam uit `_data/iconen.yml`: `grafiek`, `vergrootglas`, `huis`, `document`, `mensen`, `balans`. |
| `bronnen` | nee | Lijst met bronnen; elk met `titel` en optioneel `url` en/of `toelichting`. |
| `uitgelicht` | nee | `uitgelicht: true` zet dit artikel in de balk bovenaan, ook als het niet het nieuwste is. Zet het bij maar één artikel tegelijk. |
| `voorbeeld` | nee | `voorbeeld: true` toont de melding dat het een voorbeeldbeschouwing is. |

Leestijd wordt automatisch berekend (ca. 200 woorden per minuut).

## Een nieuw thema toevoegen

Zet in `_data/themas.yml` een nieuw paar regels erbij:

```yaml
- slug: zorg
  naam: "Zorg & Welzijn"
```

Het thema verschijnt dan automatisch als filterknop op `/artikelen/` en is te gebruiken als `thema: zorg`.

## Overzicht van de bestanden

| Bestand / map | Inhoud |
|---|---|
| `_artikelen/` | Eén Markdown-bestand per artikel |
| `_data/themas.yml` | Thema's |
| `_data/iconen.yml` | Iconen voor de artikelkaarten |
| `index.html` | Homepage |
| `artikelen/index.html` | Archief met filter |
| `_layouts/` | Paginasjablonen (algemeen en artikel) |
| `_includes/` | Gedeelde onderdelen: header, balk, footer, kaart |
| `assets/basis.css` | Opmaak van header, balk en footer |
| `assets/site.css` | Opmaak van homepage, archief en artikelen |
| `uitgangspunten-visie-op-nederland.html`, `disclaimer.html` | Losse pagina's |
| `dashboard.html` | Conceptdashboard; niet gelinkt en niet in Google |
| `robots.txt` | Zoekmachines mogen alles indexeren |
