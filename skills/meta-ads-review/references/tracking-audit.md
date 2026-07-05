# Tracking-audit

Wanneer draaien: maandelijks, na elke theme/checkout-wijziging, na elke
GTM- of consent-aanpassing, en bij elke onverklaarbare datadip (tak 0 van
de beslisboom). In de EU is dit sinds LPA (jan 2026) geen hygiëne meer
maar levensader: server-side signaal is het belangrijkste dat er nog is.

## Vaste setup (de waarheid om tegen te checken)

Lees deze waarden uit `.claude/skills/BRAND-CONFIG.md`:

- Leidende pixel/dataset: [ID uit BRAND-CONFIG]
- CAPI: [status uit BRAND-CONFIG, bijv. Shopify "Maximum" data sharing]
- Consent: [setup uit BRAND-CONFIG, bijv. GTM consent-gates + datum live]
- Store: [platform + domein uit BRAND-CONFIG]

Ontbreken deze velden in BRAND-CONFIG: eerst de intake (Blok 6) afronden,
anders audit je tegen een onbekende waarheid.

## Checklist

**1. Dataset-gezondheid (MCP)**
- [ ] `ads_get_dataset_quality` + `ads_get_dataset_stats` draaien
- [ ] Event Match Quality: Purchase-EMQ ≥ 6 is de lat (preflight-blocker
      daaronder); dalende EMQ = eerste signaal dat er iets stuk is
- [ ] Events komen binnen via ÉN browser ÉN server (CAPI); alleen-browser
      betekent dat de server-koppeling stuk is

**2. Deduplicatie**
- [ ] Pixel- en CAPI-events delen event_id zodat Meta ontdubbelt
- [ ] Purchases in Meta ≈ orders in je shop-backend over dezelfde periode
      (Meta iets lager is normaal post-LPA; Meta HOGER dan je shop =
      dubbeltelling, direct uitzoeken)

**3. Event-dekking**
- [ ] PageView, ViewContent, AddToCart, InitiateCheckout, Purchase vuren
      alle vijf (nodig voor het knoppen-model stage 5-7)
- [ ] Purchase heeft correcte value en currency, inclusief bij
      kortingen en giftcards

**4. Consent-keten (EU)**
- [ ] Consent-gates (bijv. GTM) staan nog goed na de laatste wijziging
      (test: weiger consent, check dat er geen browser-events vuren)
- [ ] Consent Mode stuurt de juiste signalen door naar de pixel

**5. UTM-discipline (koppelt Meta aan je shop-waarheid)**
- [ ] Elke actieve ad heeft utm_source=facebook (of ig), utm_campaign en
      een angle-tag in utm_content
- [ ] Shop-rapportage per UTM klopt met wat er live staat

**6. Praktijktest (kwartaal of bij twijfel)**
- [ ] Testorder plaatsen en het Purchase-event end-to-end volgen
      (Events Manager test-tool of recente events); value, currency,
      dedup en EMQ van die ene order controleren

## Output

Kort rapport: wat is gezond, wat is stuk (met fix), wat is NIET
GEVERIFIEERD. Een kapotte meting is een stop-signaal voor schaal-
beslissingen: eerst loodgieten, dan pas sturen.
