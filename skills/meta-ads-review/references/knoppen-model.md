# Het knoppen-model: waar lekt de funnel, welke knop draait het dicht

Antwoord op de vraag "de ad onderperformt, waar ligt het aan?". Loop de
keten van boven naar beneden; de eerste stage die faalt is meestal de
knop. Fix één knop tegelijk, anders weet je nooit wat werkte.

Belangrijk vooraf: richtwaarden hieronder zijn startpunten. Sinds EU LPA
(jan 2026) is de eigen baseline de enige echte lat. Na 4-6 weken spend:
vervang de richtwaarden door je eigen mediaan en stuur op afwijking
daarvan.

## De keten

| # | Stage | Metric | Startlat | Faalt hij? Dan is de knop: | Skill |
|---|---|---|---|---|---|
| 1 | Veiling | CPM vs eigen baseline | eigen mediaan | Niets aan de creative doen. Seizoen/veiling-effect of stuk signaal: check anomaly_signal, kalender, dataset quality | meta-ads-review |
| 2 | Hook | Thumbstop: 3s video views / impressions | ~25-30%, eigen baseline leidend | Eerste seconde: payload valt na seconde 4-5, of de angle spreekt de fase niet aan. Nieuwe hook op zelfde script eerst, dan pas nieuwe angle | ad-creative |
| 3 | Hold | Hold rate: ThruPlay of 15s+ / 3s views; video 25/50/75% curve | 8% (15s+/impressions) is de lat uit de bron | Verhaal: setup te traag of te snel (crossbow), fluff niet gecut, curiosity loop opent niet. Kijk WAAR de curve knakt: dat is de seconde waar het script faalt | ad-creative |
| 4 | Click | Outbound CTR | ~1%+, fashion-benchmark 2,84% (all-click, ruim genomen), eigen baseline leidend | Ze kijken wel, klikken niet: CTA ontbreekt of te laat, geen reden om NU door te klikken, of de after-state maakt niet nieuwsgierig naar het product. Soms: publiek vindt de video leuk maar het product niet relevant (angle-product mismatch) | ad-creative + offer-architect |
| 5 | Land | LP views / link clicks | >75-80% | Techniek: laadtijd mobiel, redirect, password-page. Niet creatief over-analyseren, dit is loodgieterswerk | preflight laag 5 / je LP-proces |
| 6 | Engage | Add to cart / LP views | eigen baseline (fashion ruw 5-10%) | Message match kapot (ad belooft X, LP toont Y), maat/variant niet op voorraad, prijs-schok (prijs stond niet in de ad), of productpagina beantwoordt de bezwaren niet | LP-optimalisatie + ad-preflight congruentie |
| 7 | Commit | Purchases / ATC | eigen baseline (ruw 25-35%) | Checkout-frictie (verzendkosten-verrassing, betaalmethodes, account-dwang) of twijfel: garantie/retour niet zichtbaar. Offer-persuasion-laag | offer-architect + checkout van je platform |
| 8 | Economics | AOV, first-order marge, blended CAC | margin-floor uit BRAND-CONFIG | Alles werkt maar het verdient niks: prijs, bundel/AOV-hefboom, of de CAC van deze angle is structureel te duur voor de marge | offer-architect + meta-media-buyer |

## Leesregels

1. **Volume eerst.** Onder de ~1.000 impressies (stage 2-4) of ~100 clicks
   (stage 5-8) is elke conclusie ruis. Wacht of verhoog niets.
2. **Eén lek tegelijk.** Grootste procentuele afwijking van eigen baseline
   eerst. Een matige hook mét een kapotte LP: eerst de LP (goedkoper te
   fixen, en anders test je de nieuwe hook tegen een lekke pagina).
3. **Stage 2-4 zijn creative-knoppen, 5-7 zijn site-knoppen, 8 is een
   business-knop.** Niet naar nieuwe creatives grijpen als het lek bij
   6-8 zit; dat is de prijs-eerst-diagnose uit de beslisboom.
4. **Kijktijd hoog + kliks laag (stage 3 goed, 4 slecht)** is entertainment
   zonder verlangen: het verhaal boeit maar verkoopt niet. Vaak de after-
   state of de CTA, niet de hook.
5. **Statics slaan stage 3 over**: daar is de keten hook (scroll-stop) →
   click → land. Bij statics zit "hold" in de eerste leesbeurt.
6. Elke diagnose + fix + uitkomst is een learning: voorstellen om te loggen
   in je eigen AB-testlog (schrijven alleen op expliciet verzoek).

## Data-bronnen per stage

- Stage 1-4: Meta insights (performance_trend, entity-level insights)
- Stage 5: Meta (LP views) + sessies uit je shop-analytics
- Stage 6-8: je shop-backend en financiële waarheidslaag (boekhouding of
  dashboard) zijn de waarheid, Meta alleen als kruispeiling;
  UTM-discipline maakt dit koppelbaar per angle
