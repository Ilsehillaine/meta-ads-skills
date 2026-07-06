# Intake: vul je BRAND-CONFIG

Beantwoord deze vragen en zet de antwoorden in `.claude/skills/BRAND-CONFIG.md`
(kopie van `BRAND-CONFIG-template.md`). Tip: open dit bestand in Claude Code
en zeg "loop de intake met me door", dan stelt Claude de vragen stapsgewijs
en vult hij de config voor je in.

Zonder ingevulde config werken de skills bewust op halve kracht: ze
weigeren schaal- en kill-adviezen zonder marge-cijfers. Dat is een feature.

## Blok 1: Merk & waarheid (voedt ad-creative, offer-architect, preflight)

1. Merknaam, product(categorie), prijssegment (budget/mid/premium)?
2. Wat is je product feitelijk (materiaal, samenstelling, werking)?
3. **Verboden claims**: welke beweringen mag je juridisch of feitelijk
   NIET maken, ook al klinken ze lekker? (Voorbeeld: een merk met 95%
   ingrediënten van natuurlijke oorsprong mag "synthetic fragrance free"
   claimen, maar nooit "100% natural" of "chemical-free".) Wees hier
   streng: dit is je belangrijkste guardrail.
4. Welke claims mag je wél maken, met welke onderbouwing?
5. Tone of voice in drie woorden; welke taal is je klantgerichte copy?
6. Schrijfregels/stijlregels (bijv. geen em-dashes, geen uitroeptekens)?

## Blok 2: Unit economics (voedt alles; het belangrijkste blok)

7. Verkoopprijs per product (incl. btw)?
8. Inkoopprijs/COGS per product?
9. Verzendkosten per order (incl. verpakkingsmateriaal)?
10. Betaalfee (percentage + vast bedrag per transactie)?
11. Retourpercentage (eigen data; anders: fashion ~20%, schat conservatief)
    en geschatte kosten per retour?
12. Reken uit (of laat Claude het doen): contribution margin per product,
    verwachte marge na retouren, break-even CAC, CAC-doel (~70% van
    break-even). Dit wordt je margin-floor.
13. Waar leeft je financiële waarheid (boekhouding, dashboard, sheet)?
    De skills sturen op dát cijfer, niet op Ads Manager.

## Blok 3: Business model & kalender (voedt meta-media-buyer)

14. Continu assortiment of drop-based? Bij drops: hoe groot, hoe vaak,
    hoeveel voorraad per drop?
15. Welke owned-media-kanalen heb je (nieuwsbrief, community) en hoe
    groot zijn ze? (Regel: spend terugtrekken rond owned-media-momenten.)
16. Hoeveel mag er per maand naar ads zonder dat het pijn doet in de
    cashflow van de komende 13 weken? Dit bepaalt je budget-tier.
17. Repeat purchase rate bekend? (Zonder bewezen repeat: first-order
    winstgevend sturen, geen verlies-op-eerste-aankoop.)

## Blok 4: Doelgroep & markt (voedt ad-creative)

18. Wie koopt dit, en welk dieper verlangen bedient het (aantrekkelijkheid,
    status, ergens bij horen, veiligheid)?
19. Hoe verzadigd is je markt (market sophistication)? Hebben kopers al
    3-5 alternatieven geprobeerd? (Bepaalt of educatie of failed-solution-
    agitatie je hoofdangle wordt.)
20. Wat is de "invisible villain" in jouw categorie: de verborgen oorzaak
    van het probleem die de industrie niet benoemt?
21. Welke bezwaren hoor je nu al (prijs, pasvorm, vertrouwen, levertijd)?

Valideer de antwoorden uit dit blok met echte klant-taal via de
4-bronnen-scan (`skills/ad-creative/references/angle-research.md`) en
giet ze in persona-briefs volgens het vaste format
(`skills/ad-creative/references/persona-playbook.md`). Voor agencies is
deze research-stap een verplicht onderdeel van elke klant-onboarding.

## Blok 5: Assets & productie (voedt ad-creative pipeline)

22. Welke echte assets zijn er: productfoto's, shoot-video, UGC,
    founder-materiaal? (Echte beelden = hero; AI = varianten.)
23. Is er materiaal zonder voice-over dat met AI-voiceover bruikbaar wordt?
24. Wie kan er filmen (founder, creators) en hoe vaak?

## Blok 6: Tracking & tech (voedt meta-ads-review, preflight)

25. Platform (Shopify/WooCommerce/anders) en storedomein?
26. Meta pixel/dataset-ID? CAPI actief (server-side)? Event Match Quality
    van Purchase bekend (lat: ≥ 6)?
27. Consent-setup (EU): consent mode, GTM-gates?
28. UTM-conventie afgesproken?
29. Geo-doelmarkt(en) en of EU-regels gelden (LPA, Omnibus, DSA
    beneficiary/payer)?

## Blok 7: Status & doelen

30. Wat draait er nu al aan ads en wat waren de resultaten?
31. Wat is het doel voor de komende 90 dagen: leren (welke vraag) of
    winst (welk bedrag)?
32. Wie beslist over launches en budget? (De skills vragen die persoon
    om expliciete bevestiging per mutatie.)
