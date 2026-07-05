---
name: meta-ads-review
description: |
  Je Meta-account uitlezen, diagnosticeren en de weekly review draaien
  via de Meta Ads MCP-tools. Dit is de ENIGE skill die met het echte
  account praat. Default read-only; elke mutatie (aanmaken, budget,
  activeren) vereist expliciete bevestiging per actie. Diagnose op
  contribution margin en shop-waarheid, niet op Ads Manager-ROAS.
  AUTO-ACTIVATE bij: "hoe draaien mijn ads", "analyseer mijn account",
  "weekly review", "ad performance", "waarom performt", "check mijn
  campagnes", "meta review", "ads rapport", "campagne live zetten",
  "ad aanmaken in meta", "waar staan we met de ads", "ads status".
---

# Meta Ads Review

Doel: elke week weten wat er echt gebeurt (niet wat Ads Manager zegt dat er
gebeurt) en daar maximaal 1-3 beslissingen uit halen. Dit is echt geld van
een klein merk: bij twijfel niet doen.

## Stap 0: Waar zijn we (sessie-start, altijd eerst)

Bij elke nieuwe sessie of de vraag "waar staan we": lees
`.claude/skills/ADS-STATUS.md` (fase, actieve campagnes, lopende tests
met leerdoel, blokkades, volgende acties; aangemaakt uit
`ADS-STATUS-template.md` in deze repo) en geef in 5 regels de stand.
Pas daarna analyseren. Na elke review, launch of kill: ADS-STATUS
bijwerken en de diff tonen. Status is kort; learnings horen in je eigen
testlog, archief in je eigen kennisbank of logbestanden.

**Up-to-date blijven:** maandelijks (of als resultaten onverklaarbaar
verschuiven) een korte platform-check: wat is er aan Meta veranderd
(features, EU-regels, algoritme)? Bevindingen die de skills raken →
voorstel om de betreffende skill bij te werken.

## Stap 1: Context en tools laden (verplicht, elke run)

1. `.claude/skills/BRAND-CONFIG.md` lezen (merk, margin-floor,
   pixel/dataset-ID; ingevuld via INTAKE.md), plus je eigen
   merkdocumentatie of kennisbank indien aanwezig
2. MCP-tools laden via ToolSearch, in ÉÉN call (de tools zijn deferred):
   `select:mcp__meta-ads__ads_get_ad_accounts,mcp__meta-ads__ads_insights_advertiser_context,mcp__meta-ads__ads_insights_performance_trend,mcp__meta-ads__ads_insights_anomaly_signal,mcp__meta-ads__ads_get_ad_entities,mcp__meta-ads__ads_get_errors,mcp__meta-ads__ads_get_dataset_quality`
   Voeg alleen toe wat de taak nodig heeft (benchmarks, library, mutaties).
3. Vraag naar de actuele contribution-margin-floor (uit BRAND-CONFIG of je
   financiële waarheidslaag: boekhouding of dashboard) als die niet in het
   gesprek zit. Zonder floor geen kill/scale-oordeel.

## Tool-contract

**Read-only analyse (default):**

| Tool | Waarvoor |
|---|---|
| `mcp__meta-ads__ads_get_ad_accounts` | account identificeren |
| `mcp__meta-ads__ads_insights_advertiser_context` | totaaloverzicht |
| `mcp__meta-ads__ads_insights_performance_trend` | trends over tijd |
| `mcp__meta-ads__ads_insights_anomaly_signal` | afwijkingen spotten |
| `mcp__meta-ads__ads_get_ad_entities` | campagnes/ad sets/ads ophalen |
| `mcp__meta-ads__ads_get_errors` | delivery-problemen |
| `mcp__meta-ads__ads_get_dataset_quality` + `ads_get_dataset_stats` | CAPI/pixel-gezondheid (pixel/dataset-ID uit BRAND-CONFIG) |
| `mcp__meta-ads__ads_library_search` | competitor-ads onderzoeken |
| `mcp__meta-ads__ads_insights_industry_benchmark` + `ads_insights_auction_ranking_benchmarks` | benchmarks, altijd met disclaimer (post-LPA nauwelijks vergelijkbaar) |
| `mcp__meta-ads__ads_get_opportunity_score` | Meta's eigen aanbevelingen. Kritisch lezen: Meta adviseert in Meta's belang (meer spend), niet in dat van jou |

**Mutaties (alleen na het veiligheidsprotocol hieronder):**
`ads_create_campaign`, `ads_create_ad_set`, `ads_create_ad`,
`ads_create_creative`, `ads_update_entity`, `ads_activate_entity`

## Veiligheidsprotocol (hardste regel van deze skill)

Default is READ-ONLY. Voor elke mutatie, zonder uitzondering:

1. Toon exact wat er gaat gebeuren, met alle parameters (naam, budget,
   targeting, creative, status)
2. Toon de verwachte kosten-impact in euro's per dag en per week
3. Wacht op een expliciete "ja" van de budgetverantwoordelijke voor DEZE
   ene actie. Nooit batch-goedkeuring ("doe alles maar")
4. Geen campagne live zonder een GO van de ad-preflight skill (creative,
   offer, instellingen, tracking en LP-congruentie in één poort)
5. Na uitvoering: bevestig wat er is gewijzigd en wat de status is

## Diagnose-principes

1. **Je shop-backend is de waarheid, Ads Manager het gerucht.** Stuur op
   blended CAC en dagelijkse contribution margin uit je financiële
   waarheidslaag (boekhouding of dashboard). Platform-ROAS is een
   channel-metric onderaan de hiërarchie.
2. **Attributie:** 7-day click als venster. Check periodiek de correlatie
   tussen platform-revenue en echte new-customer revenue (CORREL, streef
   0,7-0,9). Zakt die weg, dan liegt het dashboard harder dan normaal.
3. **LPA-realisme (EU, sinds jan 2026):** een deel van de EU-gebruikers
   deelt nauwelijks data; Ads Manager onderschat de werkelijkheid en je
   ziet niet wie LPA koos. Eigen baseline vanaf Q1-Q2 2026, geen oude
   benchmarks.
4. **Learning-realisme:** bij bijvoorbeeld €35/dag en een fashion-CAC rond
   €28 zijn 7-10 purchases per week normaal; structureel in learning is
   geen fout. Beoordeel trends over 7-14 dagen, nooit één dag.
5. **Prijs-eerst-diagnose:** CPC/CPM in lijn + genoeg verkeer + massale
   cart abandonment = offer/prijs-probleem (naar offer-architect), geen
   creative-probleem.
6. **Data raar? Eerst loodgieterswerk.** Bij vreemde cijfers eerst
   `ads_get_errors` en dataset quality draaien voordat je conclusies trekt.

Verdieping in references/:
- `diagnose-beslisboom.md`: volledige beslisboom + weekly-review-protocol
- `knoppen-model.md`: de funnel-keten metric voor metric (hook, hold,
  click, land, cart, checkout, marge) met per lek de juiste knop en skill
- `tracking-audit.md`: volledige pixel/CAPI/consent/UTM-audit (maandelijks
  en na elke site-wijziging)

## Weekly review output-format

Kort en beslissingsgericht, in de chat:

1. **Wat draaide:** spend, blended CAC, e-mailcaptures, per angle indien
   uitleesbaar
2. **Wat zegt de marge:** contribution margin deze week vs floor (uit je
   financiële waarheidslaag)
3. **Signalen:** anomalieën, fatigue-kandidaten, delivery-errors,
   pixel/CAPI-gezondheid
4. **Voorraad-check:** kernmaten/kernvarianten die richting sell-out gaan
   (uitverkopende varianten slopen Meta-learning; zie meta-media-buyer)
5. **1-3 beslissingen:** concreet, elk met verwachte impact en of er een
   mutatie voor nodig is (die dan het veiligheidsprotocol volgt)

Eigen logbestanden (AB-testlog, campagne-overzicht, spend-log in je
kennisbank) alleen bijwerken als je er expliciet om vraagt; ADS-STATUS.md
is de enige uitzondering (zie Stap 0).

## Fallbacks

- MCP niet beschikbaar of geen account-toegang: vraag om een CSV-export uit
  Ads Manager of screenshots. Niet gissen.
- Marge-cijfers niet beschikbaar: vraag erom. Zonder marge alleen
  beschrijvende analyse, geen beslissingen.

## QC-checklist

- [ ] Elke conclusie getoetst aan de shop/boekhoudings-waarheid, niet
      alleen Ads Manager
- [ ] Geen kill/scale-advies zonder margin-floor
- [ ] Benchmarks alleen met post-LPA-disclaimer gebruikt
- [ ] Mutaties: veiligheidsprotocol volledig doorlopen, per actie
- [ ] Voorraadstand meegewogen in elk schaal-advies

## Zusterskills

- **meta-media-buyer**: de beslisregels (70/30, +20-30%, 14 dagen, kill-regels)
- **ad-creative**: nieuwe creatives als de diagnose "verhaal versleten" is
- **offer-architect**: als de diagnose "prijs/offer" is
