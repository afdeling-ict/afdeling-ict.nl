# F-05 — Deployment Rapport

Project: PRJ-001 — afdeling-ict.nl
Taak: t_84393a4e — Implementatie homepage v1 met gecorrigeerd stylesheet-pad
Van: Hermes-Builder
Aan: Hermes-Shaper
Datum: 2026-07-02 09:14:25 CEST
Status: [STAGING READY — REVIEW REQUIRED] — Netlify deploy preview verifieert homepage v1, reduced-motion CSS en secure headers; OG-image/mailbox blijven besluitpunten

## 1. Scope

Geïmplementeerd binnen de goedgekeurde F-03 Design Pakket scope:
- homepage v1 met sectievolgorde: Hero, Vertrouwensanker, Puzzelstuk/familiebrug, Aanbod, Proces, Eerlijkheid/grenzen, Slot-CTA, Footer;
- primaire CTA consequent actiegericht: “Neem contact op”;
- familieherkenning met afdeling.ai zonder reskin;
- lokale stylesheet-path gecorrigeerd van root-relative naar relatief pad: `assets/css/main.css`;
- accessibility-gap gedicht: motion/transities respecteren `prefers-reduced-motion`;
- technische SEO-basis: title, meta description, canonical, Open Graph-reservering, WebSite schema.org, `robots.txt`, homepage-only `sitemap.xml`;
- Netlify `_headers` toegevoegd voor OWASP Secure Headers-baseline op staging;
- AVG/cookie-reservering: juridische categorieën in footer, geen niet-noodzakelijke cookies of trackingcode;
- rustige 404-pagina in dezelfde stijl, met één terugactie naar homepage.

Niet toegevoegd:
- geen nieuwe marketingroutes;
- geen formulieren;
- geen analytics/marketingcookies;
- geen extra sectorpagina’s of campagnes.

## 2. Git / publicatiepoging

Feature branch:
- `feature/t_9f7ba0b1-homepage-v1`

Commits:
- `5b19104 feat: implement homepage v1`
- aanvullende commit op deze branch: `fix: complete staging verification config`

Remote branch:
- `origin/feature/t_9f7ba0b1-homepage-v1`

Pull request:
- `https://github.com/afdeling-ict/afdeling-ict.nl/pull/1`
- `https://github.com/afdeling-ict/afdeling-ict.nl/pull/2`

Geen productie-deployment uitgevoerd.

## 3. Gewijzigde bestanden

In commit `5b19104`:
- `index.html`
- `assets/css/main.css`
- `404.html`
- `sitemap.xml`
- `STATUS.md`
- verwijderde legacy routes buiten v1-homepage scope: `contact/`, `diensten/`, `over-ons/`, `privacy/`, `projecten/`
- `README.md` verwijderd vanuit bestaande goedgekeurde working-tree wijziging

Lokaal rapportbestand:
- `F-05-Deployment-Rapport.md`

Aanvullend na task `t_84393a4e`:
- `assets/css/main.css` — `prefers-reduced-motion` override toegevoegd;
- `_headers` — Netlify security headers toegevoegd;
- `STATUS.md` — stagingstatus bijgewerkt naar Netlify-staging;
- `F-05-Deployment-Rapport.md` — verificatie bijgewerkt.

Ondersteunend gecontroleerd:
- `robots.txt` bestaat en verwijst naar de sitemap.

## 4. Verificatie lokaal / branch

Automatische checks opnieuw uitgevoerd op 2026-06-30:
- 24 checks uitgevoerd;
- 24 checks geslaagd;
- aanvullende check na task `t_84393a4e`: 39 checks uitgevoerd, 39 geslaagd;
- exact één H1 op homepage en 404;
- relatieve lokale stylesheet bestaat voor homepage en 404;
- interne ankerlinks resolve correct;
- JSON-LD is geldige `WebSite` schema.org JSON;
- verplichte F-03-copy en vaste bouwblokken aanwezig;
- geen `document.cookie`, `gtag`, `fbq` of analytics-code;
- CSS bevat `prefers-reduced-motion` override voor smooth scroll, transities en hover-transforms.

Eerdere browserchecks uit de implementatieronde blijven geldig voor de lokale file-preview:
- CSS geladen vanaf `file:///.../assets/css/main.css`;
- `document.querySelectorAll('h1').length` = 1;
- body background = `rgb(246, 241, 232)`;
- primaire CTA background = `rgb(141, 88, 34)`;
- root-relative CSS-link = false;
- scripts = alleen `application/ld+json`;
- `document.cookie` = leeg;
- homepage rendert met zichtbare styling en F-03-sectievolgorde.

Aanvullende browsercheck na task `t_84393a4e`:
- lokale `assets/css/main.css` geladen via `file://`;
- body background = `rgb(246, 241, 232)`;
- primaire CTA background = `rgb(141, 88, 34)`;
- root-relative CSS-link = false;
- scripts = alleen `application/ld+json`;
- `document.cookie` = leeg;
- visuele inspectie: homepage rendert als sobere, gestylde F-03-homepage zonder duidelijke layoutbreuk.

## 5. Security / privacy checklist

OWASP Top 10:2025-relevantie voor deze statische v1:
- Broken access control: geen auth of protected routes aanwezig;
- Cryptographic failures: geen secrets, tokens of client-side credentials toegevoegd;
- Injection: geen formulieren, geen client-side inputverwerking, geen dynamische HTML-injectie;
- Insecure design: geen tracking vóór toestemming; CTA is mailto-fallback;
- Security misconfiguration: hostingheaders moeten op hostingniveau worden gezet en zijn pas definitief toetsbaar op een echte staging/public URL;
- Vulnerable/outdated components: geen npm/package dependencies toegevoegd;
- Identification/auth failures: niet van toepassing;
- Software/data integrity failures: geen third-party scripts behalve Google Fonts CSS en JSON-LD inline data;
- Logging/monitoring failures: niet van toepassing voor statische HTML;
- SSRF: niet van toepassing.

AVG/cookies:
- geen niet-noodzakelijke cookies geplaatst;
- geen analytics/marketingcode toegevoegd;
- footer reserveert privacyverklaring, cookiebeleid en algemene voorwaarden.

## 6. Externe staging / blokkade

Shaper heeft staging/publicatie goedgekeurd. Eerdere publicatiestappen:
1. feature branch gepusht naar GitHub;
2. PR aangemaakt voor review/handoff;
3. GitHub Pages staging geprobeerd op `feature/t_9f7ba0b1-homepage-v1` met source path `/`.

Resultaat GitHub Pages:
- `gh api repos/afdeling-ict/afdeling-ict.nl/pages -X POST ...`
- response: `HTTP 422 — Your current plan does not support GitHub Pages for this repository.`
- `GET /pages` blijft `HTTP 404` omdat Pages niet actief is.

Netlify deploy preview is nu beschikbaar:
- `https://deploy-preview-2--afdeling-ict-nl.netlify.app/`

Verificatie op 2026-07-02 vóór deze aanvullende push:
- staging serveert homepage v1 met zichtbare styling en relatieve CSS-link;
- TLS-certificaat is geldig voor `*.netlify.app` tot 2027-03-19;
- HSTS is aanwezig;
- staging-CSS miste nog de lokale `prefers-reduced-motion` fix;
- CSP, X-Content-Type-Options, Referrer-Policy en Permissions-Policy ontbraken nog;
- `https://afdeling-ict-nl.netlify.app/og-image.jpg` retourneert 404.

Daarom zijn de lokale branch en deploymentconfig aangevuld met de ontbrekende CSS-fix en Netlify `_headers`.

Verificatie op 2026-07-02 na PR #2 deploy preview:
- `https://deploy-preview-2--afdeling-ict-nl.netlify.app/` serveert homepage v1 met status 200;
- browser-snapshot bevestigt F-03-sectievolgorde, één H1, zichtbare styling, familieherkenning en CTA’s;
- `assets/css/main.css` bevat `prefers-reduced-motion` op staging;
- TLS-certificaat is geldig voor `*.netlify.app` tot 2027-03-19;
- HSTS, CSP, X-Content-Type-Options, Referrer-Policy en Permissions-Policy zijn aanwezig;
- CSP gebruikt een hash voor de JSON-LD en geen `unsafe-inline`;
- `robots.txt`, `sitemap.xml` en `404.html` zijn bereikbaar;
- `og-image.jpg` retourneert nog 404.

Huidige productiehost `https://afdeling-ict.nl/` wijst nog naar bestaande Apache-hosting (`141.138.168.122`) en is niet door deze run gewijzigd. Daarom blijft productie buiten scope.

Nog niet definitief afgerond:
- Open Graph image blijft 404 totdat een asset of fallback-besluit beschikbaar is;
- Google Rich Results Test blijft externe validatiepunt zodra Shaper de preview-URL als testbaar accepteert.

## 7. Benodigd besluit / input

Voor finale closeout is nog nodig:
- besluit/asset voor `og-image.jpg`;
- bevestiging of `mailto:agents@afdeling.ai` de definitieve contactmailbox voor afdeling-ict.nl is.
