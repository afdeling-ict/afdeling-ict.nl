# F-04 — Design Tokens / Homepage v1

Project: PRJ-001 — afdeling-ict.nl
Van: Hermes-Designer
Naar: Hermes-Builder
Status: Build

## 1. Gebruik
Deze tokens vertalen de gekozen homepage-richting naar bouwbare frontend-keuzes. Ze zijn expres compact: genoeg om consistent te bouwen, zonder nieuw merkwerk te introduceren.

## 2. Typografie
font.family.display = "Fraunces, serif"
font.family.body = "Plus Jakarta Sans, sans-serif"
font.family.meta = "DM Mono, monospace"

font.size.hero = clamp(2.75rem, 5vw, 4.75rem)
font.size.h2 = clamp(1.75rem, 3vw, 2.5rem)
font.size.h3 = 1.125rem
font.size.body = 1rem
font.size.small = 0.9375rem
font.size.meta = 0.8125rem

font.weight.display = 600-700
font.weight.body = 400-500
font.weight.strong = 600-700

line.height.tight = 1.05-1.15
line.height.heading = 1.15-1.2
line.height.body = 1.55-1.7
line.height.meta = 1.4

letter.spacing.meta = 0.04em

## 3. Kleurrollen
color.bg.canvas = #f6f1e8
color.bg.surface = #fffdf8
color.bg.surface-strong = #f0e7d8
color.bg.footer = #121212

color.text.primary = #161616
color.text.secondary = #4f4b45
color.text.inverse = #f8f4ec

color.border.soft = #d8cdbd
color.border.strong = #bca98a

color.accent.brass = #a56a2a
color.accent.brass-hover = #8d5822
color.accent.brass-soft = #ead8c2

color.family.highlight = #f2d15b

color.focus.ring = #1f5eff
color.state.error = #a33131
color.state.success = #2f6b45

Regels:
- brass/koper is het enige eigen accent voor CTA’s, links in hover/focus-omgeving en kleine nadrukken;
- family.highlight alleen spaarzaam in of rond puzzel/familiecomponent;
- geen extra accentkleuren toevoegen.

## 4. Spacing
space.2xs = 0.25rem
space.xs = 0.5rem
space.sm = 0.75rem
space.md = 1rem
space.lg = 1.5rem
space.xl = 2rem
space.2xl = 3rem
space.3xl = 4.5rem
space.4xl = 6rem

Section rhythm:
- desktop sectie-padding: 4.5rem tot 6rem;
- mobiel sectie-padding: 3rem tot 4rem.

## 5. Radius en border
radius.sm = 0.5rem
radius.md = 0.875rem
radius.lg = 1.25rem
radius.pill = 999px

border.width.default = 1px
border.width.strong = 1.5px

## 6. Schaduw
shadow.none = none
shadow.card = 0 8px 24px rgba(22, 22, 22, 0.05)
shadow.interactive = 0 10px 28px rgba(22, 22, 22, 0.08)

Regel:
- standaardkaarten krijgen liever border + contrast dan zware schaduw;
- shadow.interactive alleen op hover/focus waar functioneel relevant.

## 7. Layout
layout.maxWidth = 1200px
layout.textMeasure = 68ch
layout.heroColumns = minmax(0, 1.2fr) minmax(18rem, 0.8fr)
layout.grid4 = repeat(4, minmax(0, 1fr))
layout.grid2 = repeat(2, minmax(0, 1fr))

Breakpoints:
- mobile: 0-767px
- tablet: 768-1023px
- desktop: 1024px+

## 8. Componenttokens
### Buttons
button.height = 48-52px
button.paddingInline = 1.1rem-1.4rem
button.radius = radius.pill
button.fontWeight = 600

button.primary.bg = color.accent.brass
button.primary.text = #fffaf3
button.primary.border = color.accent.brass
button.primary.hover.bg = color.accent.brass-hover

button.secondary.bg = transparent
button.secondary.text = color.text.primary
button.secondary.border = color.border.strong
button.secondary.hover.bg = color.bg.surface-strong

### Chips
chip.height = auto
chip.padding = 0.45rem 0.8rem
chip.radius = radius.pill
chip.bg = color.bg.surface
chip.border = color.border.soft
chip.text = color.text.secondary

### Cards
card.bg = color.bg.surface
card.border = color.border.soft
card.radius = radius.lg
card.padding = 1.25rem-1.5rem
card.shadow = shadow.none

### Spec-card
specCard.bg = color.bg.surface
specCard.border = color.border.strong
specCard.radius = radius.lg
specCard.padding = 1.5rem
specCard.metaFont = font.family.meta

### Puzzle panels
puzzle.panel.bg = color.bg.surface
puzzle.panel.border = color.border.soft
puzzle.panel.radius = radius.lg
puzzle.bridge.accent = color.family.highlight
puzzle.ictAccent = color.accent.brass-soft

### Note-card
note.bg = color.bg.surface-strong
note.border = color.border.soft
note.radius = radius.lg

### Footer
footer.bg = color.bg.footer
footer.text = color.text.inverse
footer.link = color.text.inverse
footer.border = rgba(255,255,255,0.12)

## 9. Interactie en focus
- Alle interactieve elementen krijgen zichtbare focus-ring met color.focus.ring.
- Hover mag subtiel zijn; geen springerige animaties.
- Transitionduur maximaal 150-180ms.
- prefers-reduced-motion respecteren door transities te minimaliseren.

## 10. Responsive regels
- Hero gaat onder 1024px naar 1 kolom zodra copy en spec-card anders te krap worden.
- Vier aanbodskaarten gaan op tablet naar 2 kolommen en op mobiel naar 1 kolom.
- Puzzle panels stapelen op mobiel; bruglabel blijft tekstueel aanwezig.
- CTA’s mogen op mobiel volle breedte gebruiken.
- Navigation links mogen compact worden, maar contentprioriteit blijft boven decoratie.

## 11. Toegankelijkheidsgrenzen voor tokens
- Koperaccent mag alleen gebruikt worden waar contrast AA gehaald wordt.
- Meta-tekst in DM Mono nooit kleiner dan leesbaar body-small niveau toepassen.
- Button- en linkstates niet alleen via kleurverschil onderscheiden.
- Decorative kleurvlakken mogen semantiek niet vervangen.

## 12. Builder-checklist
Voor implementatie controleren:
- gebruikt de pagina alleen Fraunces / Plus Jakarta Sans / DM Mono?
- is brass/koper het enige echte accent?
- blijft de pagina rustig en documentair, zonder generieke AI-glans?
- zijn desktop, tablet en mobiel consistent met de vaste layoutregels?
- halen primaire en secundaire CTA-states contrast en focus-eisen?
