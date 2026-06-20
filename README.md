# afdeling-ict.nl prototype

Statisch HTML/CSS-prototype voor de nieuwe website van afdeling-ict.nl.

## Structuur

```text
.
├─ index.html
├─ over-ons/index.html
├─ diensten/index.html
├─ projecten/index.html
├─ contact/index.html
├─ privacy/index.html
├─ assets/
│  └─ css/main.css
├─ robots.txt
├─ sitemap.xml
├─ 404.html
└─ STATUS.md
```

## Lokale preview

Open de site lokaal het liefst via een simpele static server, zodat de paden tussen de pagina’s correct werken:

```bash
cd /Users/afdelingai/.hermes/workspace/afdeling-ai/07_Projects/PRJ-001_afdeling-ict_website
python3 -m http.server 8080
```

Open daarna:
- http://localhost:8080/

Je kunt ook rechtstreeks `index.html` openen, maar een lokale server is betrouwbaarder voor de subpagina’s.

## Later deployen

Het is een gewone statische website. Later kan Farid dit handmatig of via een simpele static hosting-oplossing deployen, bijvoorbeeld door:
- de mapinhoud te uploaden naar een statische host;
- of de repository te koppelen aan een static hosting service.

Er is geen CMS, geen framework en geen externe tracking opgenomen.

## Openstaande reviewpunten

Bronveilig houden totdat deze punten zijn bevestigd:
- exacte dienstenscope buiten e-mailhosting;
- echte projectcases of referenties;
- definitieve contactroute en contactgegevens;
- juridische gegevens voor de privacy-pagina;
- definitieve keuze voor eventuele pricing- of supportinformatie;
- eventuele koppeling met externe analytics of formulieren: nu bewust niet aanwezig.
