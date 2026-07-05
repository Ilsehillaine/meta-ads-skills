# Meta Ads — stand van zaken juli 2026

**Bron:** eigen webresearch, uitgevoerd juli 2026 (2026-07-05). Doel: valideren welke adviezen uit 2024/2025 expert-video's nog kloppen. Per claim: bron + datum + betrouwbaarheidsoordeel.

Betrouwbaarheidslegenda:
- **[HARD]** = primaire bron (Meta engineering/business, Europese Commissie, gerenommeerde nieuwsmedia)
- **[PRACTITIONER]** = gerenommeerde onafhankelijke practitioner (Jon Loomer, Common Thread Co)
- **[VENDOR]** = agency/tool-blog; richting vaak juist, exacte cijfers onbetrouwbaar
- **[DUBIEUS]** = niet verifieerbaar of aantoonbaar opgeklopt

---

## 1. Andromeda / algoritme-updates

### Wat Andromeda werkelijk is
- **[HARD]** Andromeda is Meta's **retrieval engine**: de eerste fase van het ad-delivery systeem die tientallen miljoenen kandidaat-ads terugbrengt tot enkele duizenden, waarna de bekende value-based auction (bid × eAR × quality) rankt. Gebouwd met NVIDIA Grace Hopper + MTIA-chips. Resultaten volgens Meta zelf: +6% recall, +8% ads quality op geselecteerde segmenten, 10.000× model capacity. Bron: [Meta Engineering blog, 2 dec 2024](https://engineering.fb.com/2024/12/02/production-engineering/meta-andromeda-advantage-automation-next-gen-personalized-ads-retrieval-engine/).
- **[VENDOR]** Uitrol over vrijwel alle objectives/placements zou rond oktober 2025 voltooid zijn (o.a. [jetfuel.agency](https://jetfuel.agency/meta-algorithm-changes-2026-andromeda/), [confect.io](https://confect.io/tactics/meta-andromeda-2026), 2026). Geen officiële Meta-bevestiging van die datum gevonden.

### GEM: de tweede, minstens zo belangrijke update
- **[HARD]** **GEM (Generative Ads Recommendation Model)**: foundation model op LLM-schaal voor de ranking-kant, draait sinds ~Q2 2025 in de backend voor alle adverteerders (geen opt-in). Meta claimt +5% ad conversions op Instagram, 23× effectieve training FLOPS. Bron: [Meta Engineering blog, 10 nov 2025](https://engineering.fb.com/2025/11/10/ml-applications/metas-generative-ads-model-gem-the-central-brain-accelerating-ads-recommendation-ai-innovation/); duiding door [Foxwell Digital](https://www.foxwelldigital.com/blog/metas-generative-ads-model-gem-what-meta-advertisers-need-to-know) en Eric Seufert (Threads, nov 2025).
- Expert-video's uit 2024/medio 2025 die alleen "Andromeda" noemen missen GEM volledig; dat is de grotere ranking-verandering van eind 2025.

### Praktische gevolgen (consensus)
- **[PRACTITIONER]** Creative doet nu het targeting-werk. Jon Loomer: stop met tijd steken in interests, lookalikes, demografie; adviseert **15-25 werkelijk verschillende ads per campagne** (verschillende hooks, formats, copy-lengtes, psychologische invalshoeken). Bron: [jonloomer.com/meta-advertising-strategy](https://www.jonloomer.com/meta-advertising-strategy/), 2025-2026.
- **[VENDOR]** Vereenvoudigde accountstructuur wordt beloond: 1 campagne, 1 ad set, 10-20+ creatives; fragmentatie verdunt signaal. Consistent over meerdere bronnen ([uproas.io](https://www.uproas.io/blog/meta-andromeda-update-explained), [affectgroup](https://affectgroup.com/blog/andromeda-2026-how-meta-ads-algorithms-now-deliver-our-ads/), [segwise.ai](https://segwise.ai/blog/meta-andromeda-update-creative-strategy-2026)).

### Kritische noten
- **[DUBIEUS]** De veel geciteerde claim "Meta's data science team stelt dat creative 56% van campagneprestaties bepaalt" is een **hergebruikt Nielsen/NCSolutions-cijfer** (creative = 56% van sales lift bij digitale CPG-campagnes, ~450 campagnes, onderzoek van vóór Andromeda). Meta citeerde dit al jaren in Facebook IQ-materiaal. Het is geen nieuwe Andromeda-meting. Bronnen: [NCSolutions "Five Keys" rapport](https://f.hubspotusercontent20.net/hubfs/8042929/Pardot%20Files/How%20Advertising%20Works/NCS_How_Adv_Works_Five_Keys_Report.pdf), [Facebook IQ](https://www.facebook.com/business/news/insights/high-quality-creative-increases-ad-roi).
- **[DUBIEUS]** "Entity ID's op basis van visueel patroon", "computer vision + audio-analyse bepaalt je audience": mechanistische details uit agency-blogs die niet in Meta's eigen engineering-publicaties staan. Content-based retrieval is plausibel, de details zijn speculatie/marketing.

---

## 2. Advantage+ evolutie

- **[HARD/PRACTITIONER]** Begin 2025: **ASC hernoemd naar Advantage+ Sales campaigns**; scope verbreed (sales, leads, app installs). De aparte keuze "Manual vs Advantage+ Shopping" is verdwenen: er is nu **één unified campaign creation flow** waarin je "op" Advantage+ zit zolang je Meta's aanbevolen pad volgt; handmatige aanpassingen schuiven je er stilletjes vanaf. Bronnen: [Jon Loomer, Advantage+ Campaign Creation](https://www.jonloomer.com/advantage-plus-campaign/) (2025), [Pigeon Digital](https://www.pigeondigital.com/insight/advantage-plus-2025-changes-meta-campaign-overhaul) (2025).
- **[VENDOR]** Meerdere bronnen claimen dat Meta in **februari 2026** de grootste Ads Manager-overhaul in jaren afrondde: AI-optimalisaties (audience, placements, budget) staan default aan, per stuk uitschakelbaar ([1ClickReport](https://www.1clickreport.com/blog/meta-advantage-plus-campaign-setup-2026), [OptiFOX](https://optifox.in/blog/meta-ads-best-practices-2026/)). De merge startte feitelijk al in 2025; "feb 2026" als afrondingsdatum is niet primair bevestigd.
- **[HARD]** Legacy campaign APIs zijn gedeprecieerd ten gunste van de Advantage+ structuur ([ppc.land](https://ppc.land/meta-deprecates-legacy-campaign-apis-for-advantage-structure/), 2025).
- **[PRACTITIONER]** Maart 2026-updates volgens [Common Thread Co](https://commonthreadco.com/blogs/coachs-corner/meta-advantage-shopping-campaigns-in-2026): geconsolideerde budget controls (campagne-breed i.p.v. ad set-niveau), buy-now button in ads, creator commissions op Instagram, product set optimization, "Manus AI"-integratie. Let op: **het artikel citeert geen data**; CTC waarschuwt zelf: "Meta's AI optimaliseert voor Meta's omzet, niet jouw contributiemarge".
- **[VENDOR]** Verder genoemd voor 2026: multi-objective optimization (primair + secundair conversion event), verbeterde creative reporting binnen ASC (dichter bij ad-level inzicht).
- **Antwoord op de kernvraag**: ja, Advantage+ Sales is in 2026 nog steeds de facto de standaard-aanbeveling, sterker: het is nauwelijks nog een keuze, het is de default-toestand van de campagne-setup. Het onderscheid "ASC vs manual" uit 2024/2025-video's bestaat in de UI niet meer.

---

## 3. Creative-strategie consensus 2026

### Consensus (consistent over onafhankelijke bronnen)
1. **Creative is dé hendel.** Targeting-knoppen zijn grotendeels weg; differentiatie zit in creative-diversiteit. (Loomer, CTC, vrijwel elk bureau.)
2. **Diversiteit boven volume.** 15-25 échte verschillende ads (Loomer); 10-20 actieve creatives per ad set (vendorconsensus). Niet 50 varianten van dezelfde ad, maar verschillende hooks/formats/angles.
3. **Hybride AI-pipeline.** Winnende brands draaien niet all-AI of all-human: mensen maken hero-assets en vinden winnende angles, AI schaalt varianten. **[VENDOR]** Genoemde verdeling: 60-70% creative-budget naar AI-varianten/testing, 30-40% naar human hero creative ([aiadvantageagency](https://aiadvantageagency.com/ai-generated-creative-for-paid-ads/), 2026).
4. **Format-mix i.p.v. één winnend format.** Statics maken comeback in veel accounts; carrousels sterk voor fashion (meerdere productviews); video blijft dominant bij top-campagnes. Alle exacte percentages hieronder zijn vendor-cijfers zonder methodologie.

### Vendor-cijfers (richting oké, exacte waarde wantrouwen)
- **[DUBIEUS/VENDOR]** "Top-adverteerders draaien ~395 live ads vs 296 bij de onderste derde" ([adgpt.com](https://adgpt.com/blog/ecommerce-ads-dtc-brands-beat-creative-fatigue), 2026) — bron van dataset onduidelijk.
- **[VENDOR]** Brands >$5k/mnd spend: 5-15 nieuwe creatives per week tegen fatigue.
- **[VENDOR]** AI-creative presteert beter dan human creative onder ~$100 AOV, slechter erboven (één bron, niet gerepliceerd).
- **[VENDOR]** Carrousels 30-50% lagere cost per conversion dan single image ([dataslayer](https://www.dataslayer.ai/blog/meta-ad-formats-in-2025-guide)); video's 78% van top-performing ecommerce ads; fatigue-signalen: CTR -20% WoW, stijgende CPM zonder concurrentiestijging, frequency >3.0 op koud.
- **[VENDOR]** Voor fashion specifiek: lifestyle-beeld boven packshots, UGC-zwaar (genoemde mix: 40% UGC / 30% statics / 20% video / 10% carrousel — indicatief, geen data).

### Meta's eigen AI-creative richting
- **[HARD]** Zuckerberg (juni 2025, o.a. [Yahoo Finance/WSJ-rapportage](https://finance.yahoo.com/news/meta-looking-fully-automate-ad-113056107.html), [eWeek](https://www.eweek.com/news/meta-ads-ai-automation/)): doel is **volledig geautomatiseerde ad-creatie tegen eind 2026**: productfoto + doel + budget uploaden, Meta genereert creative, targeting en allocatie. Per juli 2026 is dit nog visie/gedeeltelijk uitgerold, geen realiteit voor alle adverteerders.
- **[HARD]** Marketing Brew (7 apr 2026) beschrijft hoe Meta's AI-push ad-creatie al verandert ([marketingbrew.com](https://www.marketingbrew.com/stories/2026/04/07/meta-ai-ad-creation)).

---

## 4. Klein-budget best practices (€20-50/dag)

- **[HARD-achtig]** Learning phase-drempel ongewijzigd: **~50 conversion events per week per ad set**. Tijdens learning liggen CPA's 20-40% hoger (vendorclaim, plausibel).
- **Consolidatie is regel #1**: bij €20-50/dag maximaal 1 campagne met 1 (max 2-3) ad sets, broad targeting, audience-tests sequentieel i.p.v. parallel. €50/dag over 10 ad sets = permanent in learning. Bronnen: [Stackmatix](https://www.stackmatix.com/blog/meta-ads-minimum-daily-budget-2026), [AdAdvisor](https://adadvisor.ai/blog/how-to-run-facebook-ads-on-a-tight-budget-in-2026), [cropink](https://cropink.com/minimum-budget-for-facebook-ads) (2026).
- **Realistische verwachting bij fashion**: met CAC-benchmark ~$28 (zie §5) levert €35/dag ± 1 purchase/dag = ~7-10/week. Dat is **ver onder de 50 events/week**: purchase-optimalisatie blijft dan structureel in learning. Opties: accepteren (werkt vaak alsnog), of initieel op add-to-cart/checkout optimaliseren. [Eigen inferentie op basis van benchmarks, geen directe bron.]
- **Overige consensus**: CBO gebruiken onder ~$5k/mnd; schalen met max 20-30% per 3-4 dagen; minimaal 14 dagen niet aan campagnes zitten; retargeting-laag naast koud (converteert 3-5× beter); Pixel + CAPI beide actief.
- **[PRACTITIONER]** Loomer: volautomatische campagnes (Meta's eindvisie) zijn juist voor de kleinste adverteerders de "easy button"; kleine accounts profiteren relatief het meest van automation ([jonloomer.com/future-of-meta-advertiser](https://www.jonloomer.com/future-of-meta-advertiser/)).
- **[VENDOR]** AppsFlyer-onderzoek wordt geciteerd: 70-80% van performance is creative-kwaliteit, niet budget. (Cijfer niet primair geverifieerd, richting consistent met Nielsen.)

---

## 5. Benchmarks fashion/apparel EU 2026

Alle beschikbare cijfers zijn vendor-data zonder gepubliceerde methodologie. Gebruiken als orde-van-grootte, niet als doelstelling.

| Metric | Waarde | Bron |
|---|---|---|
| Fashion CTR | 2,84% | [Lebesgue 2026](https://lebesgue.io/facebook-ads/facebook-benchmarks-by-industry-ctr-cpm-cr-and-cac) |
| Fashion CPM | $8,15 (Lebesgue) / $9,23 (digitalapplied) | idem + [digitalapplied](https://www.digitalapplied.com/blog/facebook-ads-benchmarks-2026-cpc-cpm-ctr-industry) |
| Fashion conversion rate | 0,90% | Lebesgue 2026 |
| Fashion CAC | $28,08 | Lebesgue 2026 |
| Fashion CPC | ~$0,45 (laagste van alle industrieën) | digitalapplied 2026 |
| **Nederland** CPM | **$9,20 gem.** (range $7,50-11,00) | [AdAmigo, 2 jul 2026](https://www.adamigo.ai/blog/meta-ads-cpm-cpc-benchmarks-by-country-2026) — expliciet "projecties o.b.v. eind-2025 data" |
| Nederland CPC | $1,35 | idem |
| Duitsland CPM / België CPM | $10,05 / $8,40 | idem |
| Mediaan CVR alle industrieën | 1,57% | digitalapplied 2026 |

Kanttekeningen:
- Geen enkele bron levert NL-specifieke **fashion**-CPA. NL-CPM × fashion-CTR/CVR combineren is zelf rekenen met gestapelde onzekerheid.
- Lebesgue geeft geen regio/steekproef; waarschijnlijk US-zwaar. EU-CPM's liggen doorgaans lager dan US.
- Q4 (BFCM) CPM-spikes gelden nog steeds; juni-lancering zit in relatief goedkoop seizoen.
- **Nieuw voor 2026**: het EU "less personalized ads"-cohort (zie §6) maakt EU-benchmarks van vóór jan 2026 structureel onvergelijkbaar met erna. Vergelijk eigen Q1-Q2 2026 baseline, niet 2025-cijfers.

---

## 6. Aantoonbaar veranderd sinds medio 2025 (changelog)

### Targeting
- **23 jun 2025**: consolidatie detailed targeting interests in bredere groepen ([Meta Business Help](https://www.facebook.com/business/help/458835214668072), [MediaPost 19 aug 2025](https://www.mediapost.com/publications/article/408262/meta-further-consolidates-ad-targeting-options.html)).
- **15 dec 2025**: gedeprecieerde interests niet meer bruikbaar in nieuwe ad sets.
- **15 jan 2026**: ad sets met gedeprecieerde interests **gestopt met leveren** ([Brandwatch help](https://social-media-management-help.brandwatch.com/en/articles/13215856-meta-changes-to-detailed-targeting-interests-in-advertise)).
- Detailed targeting **exclusions** verwijderd: Ads Manager mrt 2025, boosted posts jun 2025 (Meta citeerde intern 22,6% lagere mediane cost per conversion zonder exclusions).

### Algoritme & platform
- **~Q2 2025**: GEM in productie (backend, alle adverteerders); publiek gemaakt **10 nov 2025** (Meta Engineering).
- **2025**: unified campaign creation flow; "6 ads per ad set"-richtlijn stilletjes verdwenen uit documentatie; Value Rules gelanceerd; Opportunity Score (0-100) toegevoegd; engaged-view attribution 10s → 5s; Incremental Attribution beschikbaar ([dataslayer changelog](https://www.dataslayer.ai/blog/meta-ads-changes-2025-83-updates-that-changed-facebook-advertising-forever)).
- **Mrt 2026**: ASC-updates (budget controls, buy-now button, creator commissions, product set optimization) per Common Thread Co.

### Nieuwe inventory
- **Threads ads**: wereldwijd voor adverteerders sinds apr 2025; volledige uitrol naar alle users aangekondigd **21 jan 2026**, gestart 27 jan 2026; carrousel + Advantage+ catalog support ([TechCrunch 21 jan 2026](https://techcrunch.com/2026/01/21/threads-rolls-out-ads-to-all-users-worldwide/)).
- **WhatsApp Status ads**: globale uitrol gestart jun 2025, **EU uitgezonderd tot minstens 2026** na interventie Ierse DPC/GDPR-zorgen ([heise](https://www.heise.de/en/news/Advertising-in-WhatsApp-not-before-2026-in-the-EU-10453818.html), [dig.watch](https://dig.watch/updates/whatsapp-ads-delayed-in-eu-until-2026)).

### EU/DMA — de grootste verandering voor NL-adverteerders
- **Apr 2025**: Europese Commissie oordeelt pay-or-consent-model non-compliant onder DMA; **€200M boete** ([EC](https://digital-markets-act.ec.europa.eu/meta-commits-give-eu-users-choice-personalised-ads-under-dma-2025-12-08_en)).
- **8 dec 2025**: Meta committeert zich aan derde keuze-optie.
- **Jan 2026**: uitrol **"Less Personalized Ads" (LPA)** in de EU: users kiezen tussen (1) volledige personalisatie, (2) betaald ad-vrij abonnement, (3) LPA met aanzienlijk minder datadeling ([EC, 8 dec 2025](https://digital-markets-act.ec.europa.eu/meta-commits-give-eu-users-choice-personalised-ads-under-dma-2025-12-08_en); [emarketer](https://www.emarketer.com/content/meta-rewrites-its-eu-ad-model-regulators-tighten-screws)).
- **Impact voor adverteerders** ([seresa.io](https://seresa.io/blog/meta-dma-less-personalized-ads/metas-lpa-rollout-just-split-your-eu-audience-into-two-tiers), enkele bron, kwantificering onzeker): LPA-users delen tot ~90% minder data; krimpende retargeting-pools en lookalike-kwaliteit in de EU; Ads Manager toont níet welk deel van je audience LPA koos; **server-side CAPI-events worden relatief het belangrijkste EU-signaal**; advies: EU-performance Q1-Q2 2026 als nieuwe baseline nemen en EU/US-audiences niet aggregeren.
- Meta's 2026 DMA-nalevingsrapport bevestigt boete + defiante houding ([ppc.land](https://ppc.land/metas-2026-dma-report-reveals-whatsapp-ads-a-eu200m-fine-and-a-defiant-stance-on-personalized-advertising/)).

---

## 7. Verdict: welke 2024/2025-video-adviezen kloppen nog?

| Advies uit 2024/2025-video's | Status juli 2026 |
|---|---|
| "Gebruik interest-targeting / stacked interests" | **Achterhaald.** Interests geconsolideerd, exclusions weg, deprecated interests gestopt jan 2026. Broad is de norm. |
| "ASC naast een manual campagne draaien" | **Achterhaald qua UI.** ASC heet nu Advantage+ Sales en de manual/ASC-splitsing bestaat niet meer; het is één flow met AI-defaults. |
| "CBO, consolideren, learning phase 50 events/week" | **Klopt nog.** Onveranderd. |
| "Test 3-5 creatives" | **Te weinig volgens 2026-consensus.** 10-25 gedifferentieerde creatives is de nieuwe norm (Loomer: 15-25). |
| "Creative is de belangrijkste hendel" | **Klopt, sterker dan ooit** (Andromeda-retrieval + GEM-ranking zijn creative/content-gedreven). |
| "Lookalikes bouwen" | **Grotendeels achterhaald**, en in de EU extra verzwakt door LPA-datareductie sinds jan 2026. |
| "Schaal +20% per paar dagen, niet vaker" | **Klopt nog.** |
| "Video verslaat statics altijd" | **Genuanceerd.** Statics-comeback breed gerapporteerd; consensus = format-mix. |
| Alles over EU-tracking van vóór 2026 | **Herzien nodig.** LPA-optie (jan 2026) splitst het EU-publiek in twee datatiers; CAPI belangrijker dan ooit. |

## Belangrijkste bias-waarschuwing
Vrijwel alle "Andromeda verandert alles"-content komt van bureaus/tools die creative-volume-diensten of AI-creative-software verkopen. Hun richting (meer diverse creative, simpelere structuur) wordt onafhankelijk bevestigd door Loomer en Meta's eigen engineering-publicaties, maar hun **cijfers** (56%, 395 ads, 30-50% goedkopere carrousels, Entity ID-mechanica) zijn niet verifieerbaar of aantoonbaar hergebruikt ouder onderzoek.
