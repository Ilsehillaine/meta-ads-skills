# Diagnose-beslisboom en weekly review protocol

Bron: Taylor Holiday/CTC metrics-hiërarchie (2026), Shackelford
KPI-hiërarchie voor starters (2025), Steede/Adflue declining-boom en
review-lat (2026, zie meta-media-buyer/references/bron-levi-steede-2026.md),
Meta-landschap juli 2026 (zie bron-meta-landschap-juli-2026.md).

## Metrics-hiërarchie (in deze volgorde kijken, nooit andersom)

1. **Cash flow** (13 weken vooruit; leeft in je financiële waarheidslaag,
   boekhouding of dashboard, niet in Meta)
2. **Dagelijkse contribution margin**: net sales min COGS min variabele
   kosten min ad spend
3. **Business metrics**: blended CAC, e-mailcaptures, repeat rate
4. **Customer metrics**: AOV, first-order marge
5. **Channel metrics**: platform-ROAS, CPM, CTR (onderaan, sturingswaarde
   is beperkt)

Fout die de hele industrie maakt: onderaan beginnen en daar blijven.

## Beslisboom bij "de ads doen het niet"

Loop in deze volgorde, stop bij de eerste tak die raak is:

**Tak 0: Klopt de data?**
- `ads_get_errors` draaien: delivery-problemen, afgekeurde ads?
- Dataset quality checken: pixel/CAPI-events binnen, dedup ok?
- Shop-omzet vs platform-revenue: correleert het nog (0,7-0,9)?
- Zo nee: eerst loodgieterswerk, geen strategische conclusies uit kapotte
  meting.

**Tak 1: Is er überhaupt genoeg signaal?**
- Minder dan ~7 dagen data of minder dan ~50 events: wachten. Learning is
  normaal op klein budget. Trend beoordelen, niet status.

**Tak 2: Komt er verkeer maar koopt niemand?**
- CPC/CPM in lijn, CTR ok, sessies komen binnen, maar cart abandonment
  massaal of CVR ver onder eigen baseline:
  → **prijs/offer-probleem**. Naar offer-architect. Niet nog 10 creatives
  maken, dat is symptoombestrijding.
- Check ook de site zelf: laadtijd, checkout, maten/varianten op voorraad.

**Tak 3: Komt er geen (goed) verkeer?**
- CPM binnen eigen baseline maar CTR/thumbstop laag:
  → **creative-probleem**. Hook faalt (payload na seconde 5?) of angle
  versleten. Naar ad-creative, nieuwe angle (nieuw verhaal, geen iteratie).
- CPM ver boven eigen baseline: seizoen/veiling-effect of te smal signaal.
  Check anomaly_signal en de kalender (BFCM, feestdagen, concurrent-pieken).

**Tak 4: Draaide het eerst wel en zakt het nu in?**
- Frequency hoog + CTR-daling over 7-14 dagen: fatigue-kandidaat. Maar:
  14-dagenregel respecteren, niet paniek-refreshen op dag 3.
- Kernmaten/kernvarianten bijna uitverkocht? Dan is de daling geen mysterie:
  → voorraad-actie (SKU's uit de ad, of accepteren en spend terugschroeven).
- Eén slechte dag is ruis. Drie slechte dagen is een signaal. Zeven is
  een beslissing.

**Tak 5: Alles groen maar marge rood?**
- Platform zegt winst, je boekhouding zegt verlies: attributie-inflatie.
  Blended CAC en contribution margin zijn de waarheid. Spend terug naar
  het niveau waar de marge klopt.

## Aanvullende boom: performance zakt langzaam weg (Steede/Adflue)

Voor sluipende daling (niet acuut) deze vier vragen op volgorde:

1. Draait de top-creative al 4+ weken zonder dat er een nieuwe winner
   is opgestaan? → **Audience exhaustion**: zelfde mensen, zelfde verhaal.
   Fix: nieuwe persona of nieuw verhaal (niet een kleurvariant).
2. Komen er structureel te weinig nieuwe concepten bij? → **Production
   cadence probleem**. Grote-account-norm is 5 concepten/week; vertaal
   naar je tier (tier 1: is de maandelijkse leervraag überhaupt gedraaid?).
3. Is de offer al maanden identiek, los van seizoen of aanleiding? →
   **Offer staleness**: naar offer-architect ("why today?" is verlopen).
4. Anders → **hard metrics over-obsessie**: te veel op CPA staren, te
   weinig naar de zachte signalen (thumbstop, hold, comments, kwalitatief).
   Terug naar het knoppen-model met verse ogen.

## De lat voor elke review (gemiddeld vs excellent, Steede)

- Rapporteer new-customer CAC en acquisitie-MER (totale omzet nieuwe
  klanten / totale spend), nooit één platform-ROAS-getal
- Performance zakt? Eerst een meetbare oorzaak zoeken (tak 0-5), nooit
  "het algoritme" als verklaring accepteren
- Schalen zit niet alleen in meer creative: de vijf ontgrendelaars zijn
  offer, landing page, launches/drops, positionering én creative. Benoem
  in elk advies welke van de vijf je aanspreekt
- Optimaliseer de business achter Meta, niet Meta alleen

## Kill / keep / scale-regels (uit meta-media-buyer, hier operationeel)

- **Kill**: een volle week onder de margin-floor (uit BRAND-CONFIG) én geen
  leerwaarde meer. Niet vóór dag 7, niet ná dag 14 blijven hopen.
- **Keep**: rond de floor, of duidelijke leerwaarde (angle-informatie).
- **Scale**: 7-14 dagen stabiel boven floor + voorraad kan het aan +
  geen owned-media-piek in de komende dagen. Dan +20-30%, daarna 14 dagen
  afblijven.
- Verhouding bewaken: 70/30 winners/testen, nooit lopsided dumpen.

## Weekly review protocol (elke week, vast ritme)

1. Data ophalen: advertiser_context + performance_trend (7 en 28 dagen) +
   anomaly_signal + entities met status
2. Waarheid ernaast: cijfers uit je shop-backend en financiële
   waarheidslaag (omzet, orders, blended CAC, contribution margin,
   e-mailcaptures)
3. Loodgieters-check: errors + dataset quality (pixel/dataset-ID uit
   BRAND-CONFIG)
4. Voorraad-check: kernmaten/kernvarianten per actieve SKU
5. Kalender-check: drops of campagne-momenten, nieuwsbrieven, feestdagen
   komende 14 dagen (pull-back-regel uit meta-media-buyer)
6. Rapport in het vaste format (zie SKILL.md): wat draaide, wat zegt de
   marge, signalen, voorraad, 1-3 beslissingen
7. Mutaties alleen via het veiligheidsprotocol, per actie een "ja"

## Maandelijks extra

- CORREL-check platform-revenue vs new-customer revenue
- Competitor-scan via `ads_library_search` (welke angles draaien
  concurrenten al maanden = werkt waarschijnlijk)
- Benchmarks alleen als sanity check, met post-LPA-disclaimer
- Learnings die het bewaren waard zijn: voorstellen om te loggen in je
  eigen AB-testlog (alleen schrijven op expliciet verzoek)
