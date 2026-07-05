---
name: ad-creative
description: |
  Ad-concepten, scripts, hooks en statics voor Meta ads: van angle tot
  post-ready asset. Gebouwd op het awareness/scriptwriting-framework
  (D2C Diaries 2025), Shackelford's smoke-test-methodiek en de creative-
  consensus 2026 (statics-comeback, 10-25 gedifferentieerde ads, hybride
  AI-pipeline). Bevat een voorbeeld-angle-bank plus stappenplan om je
  eigen angle-bank te bouwen, en een productie-pipeline die werkt met of
  zonder gekoppelde tools (Canva, AI image edit, AI-video). Leest je
  merkgegevens uit BRAND-CONFIG.md. Schrijft nooit naar je kennisbank
  zonder expliciete vraag.
  AUTO-ACTIVATE bij: "maak een ad", "ad script", "schrijf een advertentie",
  "hook", "ad creative", "ad concept", "video script", "statics",
  "ad varianten", "nieuwe angles", "advertentie maken".
---

# Ad Creative

Doel: creatives die het targeting-werk doen. De feed beslist in 2 seconden,
het algoritme beslist op verhalen. Elke ad krijgt een awareness-fase, een
angle en een leerdoel voordat er ook maar iets geproduceerd wordt.

## Stap 1: Context laden (verplicht, elke run)

1. `.claude/skills/BRAND-CONFIG.md` (ingevuld via INTAKE.md): merk,
   verboden en toegestane claims, doelgroep, market sophistication,
   invisible villain, assets, taal- en schrijfregels. Zonder ingevulde
   config: eerst de intake doorlopen, niet gokken.
2. Je eigen kennisbank (brand DNA, hooks-bibliotheek, formats die werken)
   indien aanwezig; vraag waar die leeft.
3. Vraag welke assets er zijn (shoot-footage, productfoto's, UGC,
   founder-materiaal).

## Kernprincipes

1. **De creative is de targeting.** Awareness-fase kiezen = audience kiezen.
   Minimaal 50-60% van alle creatives richt zich op unaware/problem-aware,
   want daar zit ~80% van de top-spenders en de minste concurrentie.
2. **Setup vóór product.** De funnel is gekanteld: 15-40 seconden probleem-
   opbouw voordat het product verschijnt (crossbow-principe). Maar de kijker
   moet binnen 5 seconden locked zijn en de hook-payload valt vóór seconde 4-5.
3. **Story boven iteratie.** "Creative-iteratie is the worst creative strategy
   idea ever" (Taylor Holiday). Groei komt uit nieuwe verhalen voor nieuwe
   cohorten, niet uit 15 kleurvarianten van dezelfde winner.
4. **Ken je market sophistication** (BRAND-CONFIG, blok 4 van de intake).
   In een verzadigde markt werkt educatie alleen niet; ageer op mislukte
   oplossingen die de koper al geprobeerd heeft. In een onontgonnen markt
   is educatie juist de hoofdangle.
5. **Mensen kopen gevoel, geen product-spec.** Vertaal elke feature naar
   Maslow: confidence, identity, belonging. "People want confidence, not
   collagen."

## Werkwijze per aanvraag

1. **Angle kiezen** uit je eigen angle-bank. Nog geen angle-bank? Bouw er
   eerst een met het stappenplan in `references/angle-bank.md` (bevat een
   volledig uitgewerkte voorbeeld-casus). Elke angle krijgt een
   awareness-fase.
2. **Format kiezen**: 2026-mix, geen "video wint altijd". Statics zijn terug.
   Richtvolume: 10-25 wérkelijk gedifferentieerde ads per campagne, maar bij
   kleine budgetten geldt de smoke-test-volgorde hieronder.
3. **Script of static-copy schrijven** met de frameworks in
   `references/bron-scriptwriting-2025.md` (sectie 2: alle script-frameworks,
   sectie 3: hook-formules met voorbeelden, sectie 4: storytelling).
4. **QC draaien** (checklist onderaan).
5. **Produceren of overdragen** (pipeline hieronder).

## Smoke-test-methodiek (het testdesign voor kleine budgetten)

1. Zelfde productfoto, witte balk met bolde tekst, drie angle-varianten,
   één campagne
2. Winnende angle wint een video-uitwerking
3. Daarna varianten (persona's, formats) van alleen de winnaar
4. Sequentieel, één leervraag tegelijk. Budgetkant: zie meta-media-buyer

## Productie-pipeline (wie maakt wat)

De toolnamen zijn voorbeelden; gebruik wat je gekoppeld hebt. Zonder
MCP-koppelingen lever je copy plus een productiebrief en bouw je zelf in
je eigen tools.

| Stap | Tool | Rol |
|---|---|---|
| Statics + carousels | Indien gekoppeld: Canva MCP. Anders: elk design-tool, of HTML-export | Claude bouwt of levert briefing |
| Foto-varianten, text overlays, achtergrond-edits op echte productfoto's | Indien gekoppeld: Gemini image edit (nanobanana MCP). Anders: elk AI-beeldbewerkingsplatform | Claude bouwt of levert prompts |
| AI-video, B-roll, UGC-achtige varianten | Indien gekoppeld: Higgsfield MCP (generate_video, UGC-workflows). Anders: elk AI-videoplatform | Claude bouwt, jij keurt |
| Pre-flight check video | Indien gekoppeld: Higgsfield virality_predictor. Anders: de QC-checklist hieronder plus hardop-test | Claude draait |
| Scripts, hooks, copy (taal volgens BRAND-CONFIG) | Claude | Claude schrijft |
| Echte shoot-footage, echte UGC, final cut met gevoel | Jij / creators | Mens |

**Harde waarschuwing AI-video:** AI-gegenereerde producten renderen details
(stof, fit, textuur, materiaal) vaak nét verkeerd. Voor een premium merk is
dat dodelijk. Echte shoot-footage is de hero-asset; AI alleen voor varianten,
B-roll en statics. Hybride pipeline is de 2026-consensus, geen volledig
AI-gegenereerde productvideo's.

## Benchmarks

- Hold rate: 8% is de lat (herijk op eigen data zodra je die hebt)
- Hook-payload vóór seconde 4-5
- Oordeel over een creative pas na de window-afspraken in meta-media-buyer
  (dag 7-14), niet op dag 2

## Veiligheid en schrijfregels

- Klantgerichte copy: volg de taal- en schrijfregels uit BRAND-CONFIG
- Toets elke claim aan de verboden-claims-lijst in BRAND-CONFIG
- Nooit naar je kennisbank of vault schrijven zonder expliciete vraag
- Live zetten van ads loopt via meta-ads-review met expliciete bevestiging

## QC-checklist (elke creative langs deze lat)

- [ ] Claim-check: elke bewering getoetst aan de verboden-claims-lijst in
      BRAND-CONFIG. (VOORBEELD van hoe streng die lijst moet zijn: een merk
      met 92% organic cotton en 8% spandex mag "polyester-free" zeggen,
      maar nooit "plastic-free", "100% natural", "no synthetics" of
      "no microplastics", want spandex is synthetisch.)
- [ ] Copy volgens de taal- en schrijfregels uit BRAND-CONFIG
- [ ] Awareness-fase expliciet benoemd
- [ ] Hook-payload vóór seconde 4-5 (video) of leesbaar in 1,5 sec (static)
- [ ] 5-jarige-test: snapt een kind van 5 wat hier staat (geen jargon)
- [ ] Cut-the-fluff: elke regel escaleert pijn of bouwt verlangen, rest weg
- [ ] Praat een echt mens zo? (hardop-test)
- [ ] Geen gezondheids- of milieuclaims die je niet kunt onderbouwen

## Verdieping

- `references/angle-bank.md`: volledig uitgewerkte voorbeeld-angle-bank
  plus stappenplan om je eigen angle-bank te bouwen
- `references/bron-scriptwriting-2025.md`: alle frameworks in detail
  (awareness-fasen, crossbow, cut-the-fluff 6 vragen, jargon-regels,
  hook-formules, sophistication-niveaus, cases, quotes)

## Zusterskills

- **meta-media-buyer**: budget en testvolgorde
- **offer-architect**: het aanbod dat de ad draagt
- **ad-preflight**: onafhankelijke GO/NO-GO check vlak voor launch
- **meta-ads-review**: performance-feedback per angle (knoppen-model)
