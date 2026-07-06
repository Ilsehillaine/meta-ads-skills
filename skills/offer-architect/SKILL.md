---
name: offer-architect
description: |
  Offers, bundels en aanbod-ontwerp die aan een koud publiek verkopen
  zonder je merk tot discount-merk te maken. Gebouwd op Carl Weische's
  cold-friendly-offer framework (2024) en Taylor Holiday's peak-
  arbitragetheorie (2026), gefilterd door een premium anti-discount
  guardrail en EU Omnibus-compliance. Verhoogt perceived value in plaats
  van prijs te verlagen. Leest unit economics en merkregels uit
  BRAND-CONFIG.md.
  AUTO-ACTIVATE bij: "offer", "aanbod", "bundel", "bundle", "pricing",
  "garantie", "drop aanbod", "wat bieden we aan", "early access aanbod",
  "hoe maak ik dit aantrekkelijker", "prijs psychologie".
---

# Offer Architect

Doel: een aanbod dat een onbewust publiek over de streep trekt op waarde,
niet op korting. Weische's eigen principe is de toets: "compete on unique
value, not price." Zijn framework nemen we, zijn 40%-off-uitvoering niet.

## Stap 1: Context laden (verplicht, elke run)

1. `.claude/skills/BRAND-CONFIG.md` (ingevuld via INTAKE.md): merk,
   positionering, unit economics per product, margin-floor, verboden
   claims, taal- en schrijfregels. Zonder ingevulde marge-cijfers: geen
   offer-advies, eerst de intake.
2. Actuele aanbod-status: bij drop-based merken welke drop loopt of komt
   eraan (voorraad, prijzen); bij continu-merken welke campagne of piek
   eraan komt en wat de voorraadstand is.
3. Marge-data: een offer die de first-order winstgevendheid sloopt is geen
   offer maar een lek (check tegen de margin-floor in BRAND-CONFIG).

## Kernframework: de cold-friendly offer

Schalen komt niet van targeting of creatives maar van een aanbod dat
verkoopbaar is aan mensen die het probleem nog niet kennen (Schwartz'
awareness stages). Het unaware-segment is het grootst en het minst
concurrerend: een "artificial blue ocean". De invisible villain uit
BRAND-CONFIG (blok 4 van de intake) wijst de weg: het grootste publiek
kent de verborgen oorzaak van het probleem in jouw categorie nog niet.

Bouwvolgorde per offer:

1. **Desire kiezen.** Vier mass market desires; desire kun je niet creëren,
   alleen kanaliseren. Kies er per offer één, op basis van het diepere
   verlangen in BRAND-CONFIG:
   - *Attractiveness*: er beter uitzien, je aantrekkelijker voelen
   - *Status*: hoe anderen je zien; bewust of premium kopen als statement
   - *Belonging*: onderdeel van een community of kleine groep insiders
   - *Safety*: pijn, risico of twijfel vermijden (formuleren binnen de
     toegestane claims, zie guardrails)
2. **Perceived value verhogen, prijs laten staan.** "Making more money per
   customer, not less." Waarde stapelen: bundel-samenstelling, gids of
   info-product, garantie, early access. Geen korting als eerste reflex.
3. **Bundelen met een nieuw narratief.** Bundeltypen uit de bron: passende
   producten samen, more-of-the-same, info-product erbij, community-toegang.
   Sterkste vorm: de holistische bundel ("everything you need to X") als
   complete oplossing. Het anker-effect is de echte winst: de bundelprijs
   ankert de hele shop omhoog, ook als niemand de bundel koopt.
4. **Persuasion-laag.** Social proof, autoriteit, garantie, eerlijke
   schaarste. Zie hieronder.

## Garanties (meest kopieerbare techniek voor premium)

- **Time-based kwaliteitsgarantie** past het best bij premium: bijvoorbeeld
  een gebruiks- of maandengarantie op vorm en kwaliteit. Premium merken
  bewijzen kwaliteit, discount-merken bewijzen prijs.
- Try-before-you-buy is het overwegen waard bij twijfel over pasvorm of
  werking, maar check eerst de retourkosten-impact op de marge.
- Elke garantie moet operationeel waargemaakt kunnen worden door jouw
  teamgrootte. Geen beloftes die supportlast worden.

## Piek-offers: peak arbitrage

Je bent market taker op CPM. Een zelfgemaakte vraagpiek buiten BFCM
betekent: hogere conversie bij gelijkblijvende advertentieprijzen. Streef
naar zo'n 4 zelfgemaakte pieken per jaar via een cultural calendar.

**Voor drop-based merken:** het drop-model ís al een offer-machine, echte
schaarste zonder theater.

- Per drop expliciet beantwoorden: **"why does someone need to buy this
  today?"** Als het antwoord alleen "omdat het nieuw is" is, is de offer
  niet af.
- Een early-access-window voor je nieuwsbrief of community is het
  exclusivity-mechaniek: voorrang is de beloning, geen korting.
- Sell-out communiceren mag alleen als het waar is. Benoem echte
  oplage-aantallen; dat is geloofwaardiger dan "almost gone".

**Voor continu-merken:** bouw je pieken zelf: seizoenslanceringen, limited
colorways, restocks van uitverkochte varianten, een jaarlijks
merk-moment. Zelfde regels: urgentie alleen waar die feitelijk bestaat
(echte voorraad, echte einddatum), en het early-access-mechaniek werkt
ook hier via je owned media.

## Prijs-eerst-diagnose

CPC en CPM in lijn met verwachting, verkeer komt binnen, maar massale cart
abandonment: dan is het een prijs- of offer-probleem, geen creative-probleem.
Eerst de offer fixen, dan pas nieuwe creatives vragen. Andersom geldt ook:
geen offer-paniek als het probleem gewoon te weinig verkeer is.

## Harde guardrails

- **Anti-discount (bij premium positionering):** geen 40-50% off, geen
  opgeblazen van-prijzen, geen subscription-trucs, geen
  transformatiebeloftes. Korting-erosie is bij premium onomkeerbaar.
  Check je positionering en discount-beleid in BRAND-CONFIG.
- **EU Omnibus/ACM (als EU-regels gelden volgens BRAND-CONFIG):** elke
  van-prijs moet de laagste prijs van de afgelopen 30 dagen zijn.
  Nep-countdowns en fake voorraadmeldingen zijn een juridisch risico in
  de EU, niet alleen een stijlfout.
- **Claim-check:** toets elke bewering aan de verboden-claims-lijst in
  BRAND-CONFIG. (VOORBEELD van hoe streng die lijst moet zijn: een merk
  met 95% ingrediënten van natuurlijke oorsprong mag "synthetic
  fragrance free" claimen, maar nooit "100% natural", "chemical-free"
  of "non-toxic", want de overige 5% is synthetisch.)
- Klantgerichte copy: volg de taal- en schrijfregels uit BRAND-CONFIG.
- Nooit naar je kennisbank of vault schrijven zonder expliciete vraag.

## QC-checklist (elke offer langs deze lat)

- [ ] Omnibus-check: klopt elke prijsvergelijking juridisch (30-dagenregel,
      indien EU)
- [ ] Claim-check op alle copy tegen de verboden-claims-lijst in BRAND-CONFIG
- [ ] Discount-erosie check: schaadt dit de positionering over 6 maanden,
      niet alleen deze week
- [ ] Unit economics: is de order na deze offer nog first-order winstgevend
      (marge-check tegen de margin-floor in BRAND-CONFIG)
- [ ] Schaarste eerlijk: elk urgentie-element is feitelijk waar
- [ ] "Why today?" beantwoord met iets echts
- [ ] Operationeel haalbaar voor jouw teamgrootte

## Verdieping

- `references/bron-weische-offers-2024.md`: volledig framework, 4 desires,
  bundeltypen, garantietypen, 6 cases met cijfers, plus de kanttekeningen
  bij zijn discount-uitvoering

## Zusterskills

- **ad-creative**: de offer in de creative verwerken (zie de offer- en
  objection-angles in de angle-bank)
- **meta-media-buyer**: marge-impact en piek-pacing
- **meta-ads-review**: meten of de offer het cart-abandonment-probleem oplost
