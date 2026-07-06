# Onboarding-draaiboek: van eerste gesprek tot eerste weekly review

Het stappenplan dat de orchestrator afdwingt bij elke nieuwe klant. Elke
stap heeft een deliverable en een poort; de volgende stap start pas als
de poort dicht is. Voorbeelden komen uit dezelfde fictieve casus als de
ad-creative references: een merk in natuurlijke huidverzorging (95%
ingrediënten van natuurlijke oorsprong, 5% synthetische hulpstoffen).

## Overzicht

| Stap | Wat | Deliverable | Poort |
|---|---|---|---|
| 1 | Intake-gesprek | Antwoorden op INTAKE.md blok 1-7 | kernvragen beantwoord |
| 2 | Unit economics | Margetabel + margin-floor | floor bevestigd door beslisser |
| 3 | Website-scan | Bevindingen-document | claims op de site getoetst |
| 4 | VOC-research | Citaten per thema (4-bronnen-scan) | overlap-regel toegepast |
| 5 | Persona-set | 2-4 persona-briefs (10 velden) | wrong belief + taal-samples per brief |
| 6 | Angle-bank | Eerste angle-kandidaten met awareness-fase | 50-60% upper-funnel |
| 7 | Config | BRAND-CONFIG.md + ADS-STATUS.md | gevuld, gedateerd, in .gitignore |
| 8 | Tracking-audit | Audit-rapport (pixel, CAPI, consent, UTM) | Purchase-event gezond |
| 9 | Kickoff | Tien vragen + budget-tier | alle tien beantwoord |
| 10 | Offer-check | "Why today?"-antwoord | first-order winstgevend |
| 11 | Creatives | Smoke-test-set of eerste batch | ad-creative QC groen |
| 12 | Preflight | GO/NO-GO rapport | hard GO |
| 13 | Launch | Live campagne | expliciete "ja" per mutatie |
| 14 | Weekly ritme | Vast review-moment + ADS-STATUS bijgewerkt | 1-3 besluiten per week |

## Stap 1: Intake-gesprek

Loop `INTAKE.md` stapsgewijs door, blok voor blok, niet als formulier.
Begin met de vijf dingen zonder welke niets kan: klantnaam plus eigen
werkmap, ad account-ID plus pixel/dataset-ID, website-URL plus platform,
prijzen plus COGS, geo plus EU-status. Noteer per blok wat de klant niet
weet; dat zijn geen gaten om te verzinnen maar open punten voor de config.

Let op bij blok 1 (verboden claims): klanten zijn hier vrijwel altijd te
soepel voor zichzelf. Vraag door: "welke bewering zou een toezichthouder
of een kritische Reddit-thread onderuit halen?" De casus-lat: 95%
natuurlijke oorsprong betekent dat "100% natural" een verboden claim is,
hoe goed hij ook zou converteren.

## Stap 2: Unit economics

Reken samen met de klant (of uit de aangeleverde cijfers) per product:

1. Omzet ex btw uit de verkoopprijs
2. Marge vóór marketing: omzet ex btw min COGS min verzendkosten min
   betaalfee
3. Verwachte marge na retouren (eigen retourdata; anders conservatief
   schatten, fashion rond 20%)
4. Break-even CAC = verwachte marge; CAC-doel = ~70% daarvan
5. Margin-floor: blended CAC boven €X is geel, boven €Y is rood

Toon de hele berekening en laat de budgetverantwoordelijke de floor
expliciet bevestigen. Zonder bevestigde floor geen kickoff: elke
kill/scale-beslissing hangt aan dit getal.

## Stap 3: Website-scan

Haal de kernpagina's op (home, bestseller-PDP, over-ons, eventuele
landingspagina's) en destilleer:

- **Positionering**: welk segment claimt de site, klopt dat met de
  intake-antwoorden?
- **Claims boven de vouw**: letterlijk noteren en stuk voor stuk toetsen
  aan de verboden-claims-lijst. Site-copy die de eigen lijst breekt is
  bevinding nummer één van de onboarding en gaat als fix-voorstel naar
  de klant.
- **Painpoints**: welke problemen adresseert de site nu, en in wiens
  taal (merk-taal of klant-taal)?
- **Offer**: wat is het huidige aanbod, is er een "why today?", hoe
  wordt schaarste of urgentie gebruikt en is die feitelijk waar
  (EU Omnibus)?
- **Social proof**: reviews, aantallen, autoriteit; wat is er bruikbaar
  voor ads?
- **Conversie-basics**: prijsvergelijkingen, laadtijd mobiel, checkout.
  Bevindingen noteren als LP-input, geen redesign-project starten.

## Stap 4: VOC-research

Draai de 4-bronnen-scan uit
`../../ad-creative/references/angle-research.md`:

1. Reddit/fora van de niche: letterlijke probleem-zinnen, mislukte
   oplossingen, twijfels
2. Virale TikToks in de niche: welke framing en welke comments pakken
   organisch views
3. Competitor ad-comments via de Meta Ads Library: bezwaren onder
   concurrent-ads zijn objection-handling-goud
4. Eigen en concurrent-organics: wat resoneert zonder mediabudget en
   welk gevoel wordt daar geraakt

Orden de oogst per thema en pas de overlap-regel toe: een thema dat op
3+ bronnen terugkomt is signaal, één bron is anekdote. De deliverable is
een citaten-document in letterlijke klant-taal; parafrases zijn
waardeloos voor hooks.

## Stap 5: Persona-set

Giet intake plus VOC in 2-4 persona-briefs volgens het verplichte
10-velden-format in `../../ad-creative/references/persona-playbook.md`
(wie, wrong belief, pain points, dieper verlangen, taal-samples,
bezwaren, awareness-fase, hooks, bewijs-type). Elke brief krijgt een
code (P1, P2, ...) die later in campagne-namen en UTM's terugkomt.

Lat per brief: de taal-samples komen uit stap 4 (echte citaten), de
wrong belief is falsifieerbaar geformuleerd, en er staan 3-5
uitgeschreven hooks in. Een brief zonder echte klant-taal is een
aanname-document, geen persona-brief.

## Stap 6: Angle-bank

Bouw de eerste angle-kandidaten met het stappenplan in
`../../ad-creative/references/angle-bank.md`. Elke angle krijgt een
awareness-fase; bewaak dat 50-60% van de kandidaten op
unaware/problem-aware mikt (daar zit het volume en de minste
concurrentie). Koppel elke angle aan minstens één persona en aan de
VOC-thema's waaruit hij komt: een angle zonder bron-citaten is verzonnen,
niet gevonden.

## Stap 7: Config genereren

1. `BRAND-CONFIG-template.md` kopiëren naar
   `.claude/skills/BRAND-CONFIG.md`, vullen uit stap 1-6, datum erbij
2. Onbevestigde aannames (retourpercentage geschat, COGS indicatief) in
   de open-punten-lijst, niet als feiten presenteren
3. `ADS-STATUS-template.md` kopiëren naar `.claude/skills/ADS-STATUS.md`:
   fase, budget-tier, 90-dagen-doel, blokkades, eerste drie acties
4. Check `.gitignore`: beide bestanden bevatten privé-data en horen daar
   te staan. Eén werkmap per klant, zodat configs nooit verwisseld
   kunnen worden.

## Stap 8: Tracking-audit

Draai vóór de eerste euro spend de tracking-audit uit
`../../meta-ads-review/references/tracking-audit.md`: vuurt het
Purchase-event met correcte value en currency, dedupliceren pixel en
CAPI, staat de consent-setup goed, is er een UTM-conventie. Event Match
Quality van Purchase op 6 of hoger is de lat. Een kapotte meting eerst
fixen; adverteren op een blinde pixel is geld verbranden zonder learnings.

## Stap 9-13: het launch-spoor

Vanaf hier nemen de specialisten het over, in de vaste volgorde:

- **Stap 9, kickoff** (meta-media-buyer): de tien vragen uit
  `campagne-kickoff.md` plus budget-tier-keuze. Vraag 6 eist de
  persona-briefs uit stap 5; die poort staat er niet voor niets.
- **Stap 10, offer** (offer-architect): "why does someone need to buy
  this today?" beantwoord met iets echts, marge na offer nog first-order
  winstgevend, Omnibus-compliant.
- **Stap 11, creatives** (ad-creative): smoke-test-volgorde op lage
  tiers (3 statics, zelfde foto, 3 personas of angles), eigen
  QC-checklist afdraaien.
- **Stap 12, preflight** (ad-preflight): onafhankelijke GO/NO-GO op vijf
  lagen. NO-GO is een goede uitkomst; fixes terug naar de betreffende
  skill en dan de hele preflight opnieuw.
- **Stap 13, launch** (meta-ads-review): veiligheidsprotocol, expliciete
  "ja" van de budgetverantwoordelijke per mutatie, daarna bevestiging
  van wat er staat.

## Stap 14: Weekly ritme

Plan een vast wekelijks review-moment (meta-ads-review): wat draaide,
wat zegt de marge, signalen, voorraad-check, 1-3 besluiten. ADS-STATUS.md
wordt na elke review bijgewerkt met diff. Maandelijks (of bij
onverklaarbare verschuivingen): platform-check en tracking-spot-check.
Learnings die de skillset raken gaan via yt-learnings naar
skill-update-voorstellen.

## Rode vlaggen tijdens onboarding (eerlijk benoemen)

- Klant wil launchen zonder marge-cijfers: weigeren, stap 2 eerst
- Klant wil claims die de eigen verboden-lijst breken "omdat concurrenten
  het ook doen": blocker, geen stijlkwestie
- Budget onder tier 1 (zie het budget-tier playbook): adviseer
  e-mailcapture of sparen, geen purchase-campagne
- Geen enkele echte asset (alleen stockfoto's of AI-beelden): eerst
  echte productfoto's regelen; echte beelden zijn de hero-assets
- Tracking stuk en "dat fixen we later": later is nooit, stap 8 is een
  poort
