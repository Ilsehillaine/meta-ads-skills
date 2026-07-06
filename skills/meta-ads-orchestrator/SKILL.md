---
name: meta-ads-orchestrator
description: |
  Het startpunt en de regisseur van deze skillset: onboardt een nieuwe
  klant (intake, onderzoek, config) en routeert daarna elke vraag naar
  de juiste skill in de vaste volgorde: intake, onderzoek, config,
  kickoff, creatives, preflight, launch, weekly review. Genereert per
  klant een eigen BRAND-CONFIG.md en ADS-STATUS.md uit de templates,
  schrijft een verplichte onboarding-analyse voor (website-scan,
  VOC-research, eerste persona-set plus angle-kandidaten) en erft alle
  veiligheidsregels: geen mutatie in Meta zonder expliciete bevestiging
  per actie, geen medische of angst-claims, elke claim getoetst aan de
  client-BRAND-CONFIG.
  AUTO-ACTIVATE bij: "nieuwe klant", "onboard deze klant", "klant
  onboarden", "start de intake", "zet een klant op", "begin met dit
  merk", "waar beginnen we", "hoe werkt deze skillset", "welke skill
  moet ik gebruiken", "wat is de volgende stap".
---

# Meta Ads Orchestrator

Doel: één ingang voor de hele skillset. Wie dit leest hoeft niet te weten
welke van de zes skills wat doet; deze skill bepaalt de volgorde, bewaakt
de poorten en stuurt elke vraag naar de juiste specialist. De specialisten
doen het werk; de orchestrator zorgt dat niemand een stap overslaat.

## Het vaste spoor (nieuwe klant)

```
1. INTAKE          orchestrator + INTAKE.md (32 vragen, stapsgewijs)
        │
        ▼
2. ONDERZOEK       website-scan + VOC-research (4-bronnen-scan)
        │          → persona-briefs + angle-kandidaten
        ▼
3. CONFIG          BRAND-CONFIG.md + ADS-STATUS.md per klant
        │          (uit de templates; unit economics berekend)
        ▼
4. KICKOFF         meta-media-buyer: tien kickoff-vragen + budget-tier
        │          offer-architect: is de offer af ("why today?")
        ▼
5. CREATIVES       ad-creative: persona → angle → script/static
        │
        ▼
6. PREFLIGHT       ad-preflight: GO/NO-GO op vijf lagen
        │
        ▼
7. LAUNCH          meta-ads-review: uitvoering, expliciete "ja" per mutatie
        │
        ▼
8. WEEKLY REVIEW   meta-ads-review: diagnose, knoppen-model, 1-3 besluiten
```

Elke stap is een poort: niet door naar de volgende zonder dat de vorige
af is. Geen kickoff zonder ingevulde config, geen creatives zonder
persona-brief, geen launch zonder GO van de preflight. Het volledige
stappenplan met deliverables per stap staat in
`references/onboarding-draaiboek.md`.

## Stap 0: Waar staan we (elke sessie)

1. Bestaat `.claude/skills/BRAND-CONFIG.md` en is die gevuld? Nee: start
   de intake (fase 1). Ja: lees hem.
2. Bestaat `.claude/skills/ADS-STATUS.md`? Ja: lees hem en geef in 5
   regels de stand (fase, actieve campagnes, blokkades, volgende acties).
3. Bepaal in welke fase van het spoor deze klant zit en stel de volgende
   stap voor. Bij een losse vraag: routeer via de routing-tabel onderaan.

## Fase 1: Intake (nieuwe klant)

Minimaal vereist voordat er iets anders gebeurt:

- **Klantnaam** en een eigen project of werkmap voor deze klant (configs
  van klanten mogen elkaar nooit kunnen raken)
- **Meta ad account-ID** en **pixel/dataset-ID**
- **Website-URL** en shopplatform
- **Product(en), verkoopprijzen en COGS**; ontbreken de COGS of de
  marges, reken ze dan samen uit via blok 2 van INTAKE.md (verzendkosten,
  betaalfees, retourpercentage erbij, conservatief schatten)
- **Markt/geo** en of EU-regels gelden (LPA, Omnibus, DSA)
- **Bestaande assets**: productfoto's, shoot-video, UGC, founder-materiaal

Loop daarna de volledige vragenlijst in `INTAKE.md` door: 7 blokken,
32 vragen, stapsgewijs en niet als formulier-dump. Onbeantwoorde vragen
worden genoteerd als open punten in de config, niet stilzwijgend
overgeslagen.

## Fase 2: Onboarding-onderzoek (verplicht, geen kickoff zonder)

De intake geeft wat de klant DENKT; het onderzoek geeft wat de markt
ZEGT. Beide zijn nodig, in deze volgorde:

1. **Website-scan.** Haal de site op (of vraag om de kernpagina's) en
   destilleer: positionering, beloftes en claims boven de vouw,
   painpoints die de site adresseert, de huidige offer, prijsstelling,
   social proof. Toets elke claim die de site nu maakt meteen aan wat
   juridisch en feitelijk mag (intake blok 1, vraag 3): bestaande
   site-copy die de verboden-claims-lijst breekt is bevinding nummer één.
2. **VOC-research.** Draai de 4-bronnen-scan uit
   `../ad-creative/references/angle-research.md`: Reddit/fora, virale
   TikToks in de niche, competitor ad-comments (via `ads_library_search`
   in meta-ads-review), eigen en concurrent-organics. Verzamel LETTERLIJKE
   klant-taal: probleem-zinnen, mislukte oplossingen, bezwaren. De
   overlap-regel bepaalt wat signaal is (3+ bronnen) en wat anekdote.
3. **Persona-set bouwen.** Giet intake plus VOC in 2-4 persona-briefs
   volgens het 10-velden-format in
   `../ad-creative/references/persona-playbook.md`. Elke brief bevat
   wrong belief, pijn in klant-taal, bezwaren en 3-5 hooks.
4. **Angle-kandidaten.** Bouw de eerste angle-bank met het stappenplan in
   `../ad-creative/references/angle-bank.md` (de fictieve
   huidverzorgings-casus daar laat zien hoe streng het format is). Elke
   angle krijgt een awareness-fase; 50-60% van de kandidaten richt zich
   op unaware/problem-aware.

Output van deze fase: een onderzoeksdocument met website-bevindingen,
VOC-citaten per thema, persona-briefs en angle-kandidaten. Kickoff-vraag
6 (meta-media-buyer) weigert terecht zonder persona-brief; dit onderzoek
is dus geen nice-to-have maar een poort.

## Fase 3: Config genereren

1. Kopieer `BRAND-CONFIG-template.md` naar
   `.claude/skills/BRAND-CONFIG.md` en vul hem uit intake plus onderzoek.
   Zet de datum erbij. Onbevestigde aannames expliciet in de daarvoor
   bestemde lijst.
2. Reken de unit economics door: contribution margin per product,
   verwachte marge na retouren, break-even CAC, CAC-doel (~70% van
   break-even), margin-floor. Toon de berekening en laat de
   budgetverantwoordelijke de floor expliciet bevestigen; dit getal
   stuurt elke kill/scale-beslissing.
3. Kopieer `ADS-STATUS-template.md` naar `.claude/skills/ADS-STATUS.md`
   en vul de startstand (fase, budget-tier, doel 90 dagen, blokkades).
4. Check dat beide bestanden in `.gitignore` staan: dit is privé-data
   (pixel-ID, marges) en hoort nooit in een publieke repo.

## Fase 4-8: doorgeven aan de specialisten

Vanaf hier regisseert de orchestrator alleen nog; het werk gebeurt in de
zusterskills, in deze volgorde:

| Fase | Skill | Poort om door te mogen |
|---|---|---|
| Kickoff | **meta-media-buyer** (`campagne-kickoff.md`: tien vragen + budget-tier) | alle tien vragen beantwoord |
| Offer | **offer-architect** ("why does someone need to buy this today?") | offer first-order winstgevend |
| Creatives | **ad-creative** (persona → angle → script/static, smoke-test-volgorde) | eigen QC-checklist groen |
| Preflight | **ad-preflight** (vijf lagen: creative, offer, instellingen, tracking, LP) | hard GO-oordeel |
| Launch | **meta-ads-review** (veiligheidsprotocol, mutaties) | expliciete "ja" per actie |
| Weekly review | **meta-ads-review** (diagnose-beslisboom, knoppen-model) | doorlopend ritme |
| Actueel houden | **yt-learnings** (nieuwe expert-kennis → skill-updates) | maandelijks of bij rare cijfers |

## Routing-tabel (losse vragen, bestaande klant)

| De vraag gaat over | Routeer naar |
|---|---|
| structuur, budget, schalen, killen, pacing, tiers | meta-media-buyer |
| aanbod, bundels, garanties, prijs, urgentie | offer-architect |
| personas, angles, scripts, hooks, statics, formats | ad-creative |
| "mag dit live", laatste check, review van een ad | ad-preflight |
| "hoe draaien de ads", cijfers, diagnose, mutaties | meta-ads-review |
| "klopt dit advies nog", nieuwe video's, platform-nieuws | yt-learnings |
| waar staan we, wat is de volgende stap, nieuwe klant | deze skill |

Grijs gebied: performance-vraag die op een creative-probleem uitdraait
begint bij meta-ads-review (diagnose eerst, knoppen-model), niet bij
ad-creative. Eerst weten welke knop faalt, dan pas maken.

## Veiligheidsregels (geërfd door elke route)

Deze regels gelden voor alles wat via de orchestrator loopt, zonder
uitzondering:

1. **Mutaties in Meta alleen met expliciete bevestiging per actie**, via
   het veiligheidsprotocol van meta-ads-review. Nooit batch-goedkeuring,
   nooit "doe alles maar". Geen launch zonder GO van ad-preflight.
2. **Geen medische claims en geen angst-claims.** Gezondheids- en
   milieuclaims alleen met onderbouwing; angst aanjagen (fear-mongering)
   is geen angle maar een blocker.
3. **Elke factual claim getoetst aan de verboden-claims-lijst in de
   client-BRAND-CONFIG.** Voorbeeld van hoe streng die lijst moet zijn:
   een merk met 95% ingrediënten van natuurlijke oorsprong mag
   "synthetic fragrance free" claimen, maar nooit "100% natural",
   "chemical-free" of "non-toxic".
4. **Geen schaal-, kill- of offer-advies zonder ingevulde marge-cijfers.**
   De skills werken bewust op halve kracht zonder margin-floor; dat is
   een feature.
5. **Nooit naar de kennisbank van de klant schrijven zonder expliciete
   vraag.** ADS-STATUS.md is de enige uitzondering (bijgewerkt door
   meta-ads-review, met diff).
6. **Privé-data blijft privé.** Pixel-ID's, marges en teststatus horen in
   de klant-config, nooit in een publieke repo of gedeeld document.

## QC-checklist (elke onboarding langs deze lat)

- [ ] Intake volledig doorlopen (32 vragen) of open punten expliciet
      genoteerd in de config
- [ ] Website-scan gedaan, inclusief claim-check op de bestaande site-copy
- [ ] VOC-research gedaan via de 4-bronnen-scan; overlap-regel toegepast
- [ ] Persona-briefs (10 velden) en angle-kandidaten bestaan vóór de
      kickoff
- [ ] BRAND-CONFIG.md en ADS-STATUS.md aangemaakt, gevuld en gedateerd
- [ ] Margin-floor berekend, getoond en bevestigd door de beslisser
- [ ] Beide config-bestanden in .gitignore
- [ ] Elke doorverwijzing benoemt welke skill en waarom
- [ ] Veiligheidsregels herhaald bij elke launch-route

## Verdieping

- `references/onboarding-draaiboek.md`: het volledige stappenplan van
  eerste klantgesprek tot eerste weekly review, met deliverables en
  poorten per stap

## Zusterskills

- **meta-media-buyer**: structuur, budget, kickoff, schalen
- **ad-creative**: personas, angles, scripts, statics
- **offer-architect**: aanbod, bundels, garanties
- **ad-preflight**: GO/NO-GO poort vlak voor launch
- **meta-ads-review**: account uitlezen, mutaties, weekly review
- **yt-learnings**: de skillset actueel houden
