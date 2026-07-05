---
name: ad-preflight
description: |
  De GO/NO-GO poort voordat een ad of campagne live gaat. Loopt een
  volledige checklist af op vijf lagen: creative, offer, instellingen
  (campagne/ad set/ad), tracking en landingspagina-congruentie. Output is
  een hard oordeel: GO, of NO-GO met concrete blockers en fixes. Reviewt
  ook ads die je zelf hebt gemaakt. Geen enkele mutatie in Meta; dat
  blijft bij meta-ads-review.
  AUTO-ACTIVATE bij: "preflight", "check deze ad", "review deze ad",
  "klaar om live te gaan", "mag deze live", "launch check", "controleer
  de campagne", "laatste check voor launch".
---

# Ad Preflight

Doel: geen euro spend naar een ad met een vermijdbare fout. Dit is de
laatste poort. Streng zijn is de functie; een NO-GO is een goede uitkomst,
geen vervelende.

## Stap 1: Verzamel wat er gecheckt wordt

Vraag om (of pak uit het gesprek): de creative(s) zelf (beeld/video/copy),
de offer, de beoogde instellingen, de landingspagina-URL en het budget.
Wat niet aangeleverd of uitleesbaar is, wordt in het rapport gemarkeerd
als NIET GEVERIFIEERD, nooit stilzwijgend overgeslagen.

Lees `.claude/skills/BRAND-CONFIG.md`. Daar komen de brand-truth en
verboden claims, de margin-floor, het pixel/dataset-ID, de taal en de
schrijfregels vandaan. Raadpleeg daarnaast je eigen kennisbank als die er
is. Geen ingevulde BRAND-CONFIG = de betreffende checks als NIET
GEVERIFIEERD markeren en dat hard benoemen.

## Laag 1: Creative

**Asset-inspectie eerst: kijk echt naar het ding, geen checklist op de
blinde vaart.** Per asset-type is dit de route:

| Asset | Hoe inspecteren | Hoe verbeteren |
|---|---|---|
| Static / foto | Bestandspad geven; Claude leest beeldbestanden direct (Read) en beoordeelt visueel: leesbaarheid, safe zones, brand-look, afkapping | Een gekoppelde image-edit-tool (bijv. Gemini image edit of Canva MCP, indien gekoppeld); anders concrete fix-aanwijzingen voor je eigen editor |
| Carrousel | Elke slide als los beeld lezen, in volgorde; swipe-logica beoordelen (verdient slide 1 de swipe, loopt het verhaal) | idem, per slide |
| Video | Drie sporen: (1) frames extraheren via ffmpeg in de scratchpad (`pip install imageio-ffmpeg` of static build) en de key frames visueel lezen: seconde 0-5 hook-frame, safe zones, tekst-timing; (2) indien een video-analyse-platform gekoppeld is (bijv. Higgsfield `video_analysis_create`): inhoudelijke analyse draaien; (3) indien beschikbaar een virality/hook-predictor (bijv. Higgsfield `virality_predictor`) als pre-flight score op hook strength en retention risk. Geen platform gekoppeld? Dan volstaan ffmpeg-key-frames of handmatige key-frame-screenshots die je aanlevert | Script/VO-fixes via ad-creative; nieuwe AI-VO via je eigen tooling; cut-aanwijzingen terug naar jou (final cut blijft mensenwerk) |
| Audio/VO | Transcript uitschrijven en tegen het script leggen; uitspraak merknaam checken | Nieuwe AI-VO genereren met je eigen tooling |

Eerlijke grens: Claude beoordeelt frames, structuur, tekst en voorspelde
performance, maar "voelt" geen pacing zoals een kijker. Key frames plus
eventuele analyse-tools vangen het meeste; de laatste smaak-check is aan
jou.

- [ ] Asset daadwerkelijk geïnspecteerd via de route hierboven (welke
      frames/slides bekeken: benoem het in het rapport)
- [ ] Brand-truth: elke claim in de creative getoetst aan de
      verboden-claims-lijst uit BRAND-CONFIG. Voorbeeld ter illustratie:
      een merk met 92% organic cotton + 8% spandex mag "polyester-free"
      zeggen, maar "plastic-free", "100% natural", "no synthetics" en
      "no microplastics" zijn blockers
- [ ] Copy in de taal en volgens de schrijfregels uit BRAND-CONFIG;
      spelling gecheckt
- [ ] Hook-payload vóór seconde 4-5 (video) of leesbaar in 1,5 sec (static)
- [ ] Awareness-fase benoemd en de creative past erbij (angle-werk in
      ad-creative)
- [ ] Geen onhoudbare gezondheids- of milieuclaims (elke claim heeft een
      bron of gaat eruit)
- [ ] Veilige zones: tekst niet onder UI-elementen in 9:16 placements
- [ ] 5-jarige-test op de copy (snapt een buitenstaander in één keer wat
      je verkoopt en waarom)

## Laag 2: Offer

- [ ] EU Omnibus (voor EU-adverteerders): elke van-prijs is de laagste
      prijs van de afgelopen 30 dagen
- [ ] Urgentie/schaarste is feitelijk waar (echte aantallen, echte deadline)
- [ ] "Why today?" beantwoord
- [ ] Marge na offer nog first-order winstgevend (margin-floor uit
      BRAND-CONFIG; geen floor bekend = NIET GEVERIFIEERD markeren)
- [ ] Geen discount-erosie van je positionering (zeker bij premium)

## Laag 3: Instellingen (per niveau)

Loop de VOLLEDIGE catalogus af: `references/instellingen-catalogus.md`.
Die dekt account (verificatie, spending limits, DSA beneficiary/payer,
EMQ >= 6, existing-customers-definitie), campagne (objective, budget,
existing customer budget cap 0-5% voor cold), ad set (Purchase-event,
juiste dataset, 7-day click, geo, placements met passende assets) en ad
(alle Advantage+ creative enhancements stuk voor stuk UIT als default,
inclusief music, image expansion en text improvements; dynamische
UTM-template; CTA; previews).

De snelle kern, altijd expliciet in het rapport:
- [ ] Optimalisatie-event = Purchase, dataset-ID geverifieerd tegen het
      ID in BRAND-CONFIG
- [ ] Attributie-setting = 7-day click ÉN rapportage-kolom op hetzelfde
      venster
- [ ] Existing customer budget cap ingesteld bij cold campagnes
- [ ] Alle creative enhancements uitgeklapt en per stuk beoordeeld
      (nooit de bundel accepteren)
- [ ] UTM's via dynamische template, geen handwerk
- [ ] Niet gelanceerd bovenop een draaiende winner (lopsided-regel uit
      meta-media-buyer: nieuwe ads verstoren delivery van winners)

## Laag 4: Tracking (spot-check)

- [ ] Purchase-event vuurt met correcte value en currency (testorder of
      recente events in dataset stats)
- [ ] CAPI + pixel dedupliceren (geen dubbele Purchases)
- [ ] Consent-setup (zoals beschreven in BRAND-CONFIG) actief en niet
      stuk na de laatste site-wijziging
- Volledige audit: zie de tracking-audit in de meta-ads-review skill
  (maandelijks en na elke theme/site-wijziging)

## Laag 5: Landingspagina-congruentie

- [ ] Message match: de belofte/angle uit de ad staat boven de vouw op de LP
- [ ] Zelfde taal (die uit BRAND-CONFIG), zelfde toon, zelfde beeldstijl
- [ ] Product op voorraad in kernmaten/varianten; geen ad naar een
      bijna-uitverkochte SKU
- [ ] Laadtijd mobiel acceptabel; checkout werkt
- [ ] Prijs in de ad (indien genoemd) = prijs op de LP
- Structurele LP-verbetering valt buiten deze skill; noteer bevindingen
  als input voor je LP-werk

## Launch-context (laatste check)

- [ ] Geen owned-media-piek (nieuwsbrief, drop, campagnemoment) in de
      komende dagen die met deze launch botst (pull-back-regel
      meta-media-buyer)
- [ ] Leerdoel van deze launch in één zin genoteerd (wat weten we straks
      wat we nu niet weten?)

## Output-format (verplicht)

```
PREFLIGHT: <ad/campagne-naam>
Oordeel: GO / NO-GO
Blockers (moet gefixt): ...
Waarschuwingen (mag live, wel fixen): ...
Niet geverifieerd: ...
Leerdoel: ...
```

NO-GO bij elke blocker in laag 1-4. Waarschuwingen blokkeren niet maar
worden expliciet benoemd. Na fixes: preflight opnieuw, niet half.

## Zusterskills

- **ad-creative**: maakt de creative (heeft eigen QC; preflight is de
  onafhankelijke tweede blik)
- **offer-architect**: fixt offer-blockers
- **meta-ads-review**: voert de launch uit ná een GO, met het
  veiligheidsprotocol (expliciete "ja" per mutatie)
- **meta-media-buyer**: kickoff-plan, budget en timing
