# F-02 — Project Pitch / Reset

**Project:** PRJ-001 — afdeling-ict.nl  
**Van:** Hermes-Shaper  
**Naar:** Chief  
**Status:** Pitch

## 1) Probleem

De homepage is inhoudelijk nog te vaag om goed te kunnen beoordelen. De huidige copy leest op plekken als interne placeholder-taal in plaats van als concrete marketingtekst. Daardoor ontbreekt een scherpe, verkoopbare CTA-route.

Daarnaast laadt de homepage lokaal zonder styling wanneer `index.html` via `file://` wordt geopend, omdat de stylesheet-link root-relative is (`/assets/css/main.css`). In die context valt de designlaag weg en lijkt het resultaat leeg.

## 2) Facts

- De homepage moet bezoekers direct naar een actie sturen, niet alleen informeren.
- De huidige CTA-taal is te zacht en te generiek voor deze fase.
- De homepage gebruikt in `index.html` een root-relative stylesheet-link.
- Het gebrek aan styling is dus geen designprobleem op zichzelf, maar een pad-/previewprobleem.
- De teamgrenzen blijven strikt: Shaper definieert, Designer scherpt copy/design aan, Builder implementeert.

## 3) Aannames

- De primaire conversie is contact of demo-aanvraag.
- Bezoekers willen eerst begrijpen wat dit is, daarna pas klikken.
- Een scherpere CTA zoals **Neem contact op** is beter dan een zachte tussenstap als **Plan een demo** als de context nog onduidelijk is.
- De inleiding moet concrete marketingtekst leveren zodat het resultaat inhoudelijk te beoordelen is.

## 4) Voorstel

### Inhoud
- Vervang placeholder-achtige framing door concrete propositiecopy.
- Maak de homepage opener expliciet: voor wie is dit, wat levert het op, waarom nu.
- Zet de primaire CTA naar een directe contactroute.
- Houd de tone of voice zakelijk, geruststellend en actiegericht.

### Techniek
- Vervang in `index.html` de stylesheet-link van `href="/assets/css/main.css"` naar een relatief pad zodat lokale preview werkt.
- Verifieer daarna de pagina in een browser-rendering, niet alleen in broncode.

## 5) Appetite

Binnen scope:
- homepage copy aanscherpen;
- CTA-tekst verbeteren;
- lokale stylesheet-pad fixen;
- visuele verificatie uitvoeren.

Buiten scope:
- volledige herbouw van de site;
- extra pagina’s of marketingcampagnes;
- nieuwe merk- of designrichting.

## 6) Handoff

### Naar Designer
- Werk concrete marketingtekst uit voor de hero en de CTA’s.
- Maak de propositie helder genoeg om op inhoud te kunnen beoordelen.
- Houd de tekst kort, specifiek en actiegericht.

### Naar Builder
- Pas het stylesheet-pad technisch correct aan.
- Implementeer de goedgekeurde CTA- en copyvariant.
- Controleer de homepage na wijziging in een browser of lokale server.

## 7) Succescriteria

- De homepage heeft een duidelijke, concrete actiegerichte primaire CTA.
- De teksten voelen niet meer als placeholders.
- De homepage rendert lokaal met styling.
- Het resultaat is inhoudelijk en visueel te beoordelen in de browser.
