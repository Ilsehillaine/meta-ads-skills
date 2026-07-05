# Instellingen-catalogus: elke knop, elk niveau

De volledige checklist achter Laag 3 van de preflight. Vier niveaus:
account (eenmalig + periodiek), campagne, ad set, ad. Plus de
rapportage-instellingen waarmee je resultaat beoordeelt.

Merk-specifieke waarden (pixel/dataset-ID, margin-floor, verboden claims,
taal) komen uit `.claude/skills/BRAND-CONFIG.md`; deze catalogus verwijst
daarnaar waar dat speelt. Secties gemarkeerd met "voor EU-adverteerders"
gelden alleen als je in de EU adverteert (zie je geo-antwoord in
BRAND-CONFIG).

Kernfilosofie bij alle Advantage+/AI-opties: **alles wat Meta automatisch
"verbetert" aan jouw creative staat standaard UIT voor een merk dat op
consistentie stuurt.** Enhancements verschuiven controle naar Meta én
vervormen de meting: als Meta muziek, crops of tekst wijzigt, weet je
nooit meer wélke creative eigenlijk won. Aanzetten mag, maar alleen als
bewuste, gelogde test.

---

## Niveau 0: Account & Business Manager (eenmalig, daarna per kwartaal)

- [ ] Business verification afgerond; tweefactor-authenticatie aan voor
      alle gebruikers
- [ ] Gebruikersrechten minimaal (least privilege); geen oude bureaus of
      ex-partners met toegang
- [ ] Domein geverifieerd (je storedomein)
- [ ] Dataset/pixel gekoppeld aan het ad-account; CAPI actief
      (server-side; bij Shopify: data sharing op Maximum)
- [ ] **Event Match Quality Purchase >= 6** (Events Manager); daaronder
      eerst de tracking-audit draaien, niet adverteren op een blinde pixel
- [ ] Account spending limit ingesteld als vangnet (bijv. maandbudget
      x1,5, voorkomt runaway spend bij een fout)
- [ ] Valuta en tijdzone correct (achteraf onomkeerbaar zonder nieuw account)
- [ ] Betaalmethode + factuurgegevens kloppen (btw-nummer voor de
      boekhouding waar van toepassing)
- [ ] **DSA (voor EU-adverteerders): beneficiary en payer ingevuld**
      (zonder deze levert Meta niet uit in de EU)
- [ ] Brand safety: inventory filter op moderaat/strikt, block lists
      indien relevant, comment-moderatie op de pagina ingericht
- [ ] **"Existing customers"-definitie ingesteld** in account settings
      (klantenlijst-audience + pixel-based purchasers). Dit is de
      voorwaarde om kopers te kunnen uitsluiten of te cappen in
      Advantage+ Sales
- [ ] Naamconventies afgesproken (campagne/ad set/ad bevatten angle-naam,
      zodat UTM's en rapportage per angle werken)

## Niveau 1: Campagne

- [ ] Objective = Sales; unified Advantage+ Sales flow (geen legacy-opzet)
- [ ] Special ad categories: alleen aan als je categorie er echt onder
      valt (krediet, werk, huisvesting, politiek); reguliere e-commerce
      zoals kleding is dat niet. Per ongeluk aan = gekortwiekte delivery
- [ ] Dagbudget conform je kickoff-tier (campagne-kickoff in
      meta-media-buyer); geen "aanbevolen" Meta-bedrag klakkeloos accepteren
- [ ] Campaign spending limit: bewuste keuze (aan als vangnet bij tests)
- [ ] **Existing customer budget cap op 0-5% voor cold campagnes.** Dit is
      anno 2026 de manier om recente kopers uit te sluiten; de klassieke
      exclusion-audience bestaat in de unified flow nauwelijks nog.
      Let op (voor EU-adverteerders): post-LPA is de uitsluiting niet
      waterdicht, accepteer restlekkage
- [ ] A/B-test-toggle uit, tenzij er bewust een test loopt
- [ ] Campagnenaam volgens conventie (angle erin)

## Niveau 2: Ad set

- [ ] Conversion location: website; performance goal: maximise conversions
- [ ] **Optimalisatie-event = Purchase** (niet ATC, niet LP views, tenzij
      expliciet besloten en genoteerd waarom)
- [ ] Dataset/pixel = de juiste (check het ID tegen BRAND-CONFIG, niet
      alleen de naam)
- [ ] **Attributie-setting = 7-day click** (eventueel + 1-day engaged view,
      bewuste keuze). En: de rapportage-kolom in Ads Manager op hetzelfde
      venster zetten, anders beoordeel je op een ander getal dan waarop
      Meta optimaliseert
- [ ] Geo: doelland op "people living in" (niet "recently in": vakantie-
      verkeer)
- [ ] Leeftijd: alleen inperken met een reden; Advantage+ audience werkt
      met signalen, niet met hekken
- [ ] Geen legacy detailed-targeting-restanten of overbodige exclusions
      (interesses zijn 2025-2026 geconsolideerd/gedeprecieerd; oude
      instellingen kunnen dode filters zijn)
- [ ] **Placements: Advantage+ (automatisch) als default.** Bij manual:
      bewust en gelogd. Check dat elke placement een passend asset heeft
      (9:16 voor Stories/Reels, 1:1 of 4:5 voor feed); placement zonder
      passend asset = geld naar een vervormde ad
- [ ] Start (en eventueel eind) datum correct; geen dayparting tenzij bewust
- [ ] Ad set-naam volgens conventie

## Niveau 3: Ad

- [ ] Identity: juiste Facebook-pagina én Instagram-account gekoppeld
- [ ] **Advantage+ creative enhancements, stuk voor stuk (de "filters"):**
      - [ ] Music: UIT (Meta plakt anders willekeurige muziek onder je
            video of static; sloopt AI-voiceovers en merkgevoel)
      - [ ] 3D motion / image animation: UIT (vervormt productbeelden)
      - [ ] Visual touch-ups / image enhancements: UIT (kleurechtheid van
            je product is vaak een koopfactor; Meta mag er niet aan zitten)
      - [ ] Image expansion (AI-uitbreiden van beeld): UIT (AI-gegenereerde
            randen en artefacten zijn een merkrisico)
      - [ ] Text improvements / text generation: UIT (Meta herschrijft
            anders je copy; brand-truth-risico: als Meta er een verboden
            claim van maakt, bijvoorbeeld "100% natural", is dat jouw
            juridische probleem; zie de verboden-claims-lijst in
            BRAND-CONFIG)
      - [ ] Overlays (prijs/verzend-badges): UIT tenzij bewust
      - [ ] Add catalog items / site links: UIT tenzij bewust
      - [ ] CTA-variaties: UIT tenzij bewust
      - [ ] Standard enhancements "bundel": nooit als bundel accepteren,
            altijd uitklappen en per onderdeel beslissen
- [ ] Flexible ad format: bewuste keuze (uit bij een strak getest concept)
- [ ] Primary text, headline, description gevuld; afkapping gecheckt in
      alle placement-previews; safe zones voor 9:16
- [ ] CTA-knop passend ("Shop now" voor sales)
- [ ] Destination URL: werkt echt (geen 404, geen password-page), juiste
      variant/kleur vooraf geselecteerd indien relevant
- [ ] **URL-parameters via dynamische template, nooit handwerk:**
      `utm_source={{site_source_name}}&utm_medium=paid&utm_campaign={{campaign.name}}&utm_content={{ad.name}}&utm_term={{adset.name}}`
      Zo is elke ad automatisch traceerbaar per angle in je
      store-analytics/GA
- [ ] Pixel/dataset-tracking aangevinkt op ad-niveau
- [ ] Preview op mobiel bekeken (waar 95%+ van de views vandaan komt)

## Rapportage-instellingen (waarmee je beoordeelt)

- [ ] Attributie-kolom = 7-day click; zet 1-day click ernaast als
      vergelijking, niet als waarheid
- [ ] Custom columns ingericht: spend, purchases, CAC, 3-sec views,
      thumbstop-ratio, ThruPlay/holdrate, outbound CTR, LP views, ATC,
      cost per e-mailcapture (het knoppen-model stage voor stage)
- [ ] Breakdown per placement en leeftijd maandelijks bekijken (niet om
      te sturen, wel om rare lekken te zien)
- [ ] Je financiële waarheidslaag (uit BRAND-CONFIG: boekhouding,
      dashboard of store-data) blijft de waarheid; Ads Manager-kolommen
      zijn de kruispeiling

## Gebruik in de preflight

Laag 3 van de preflight loopt de niveaus 1-3 volledig af; niveau 0 is een
kwartaal-audit plus verplicht onderdeel van elke eerste campagne-setup.
Elke afwijking van een default hierboven is toegestaan, mits bewust,
benoemd in het preflight-rapport en gelogd als test.
