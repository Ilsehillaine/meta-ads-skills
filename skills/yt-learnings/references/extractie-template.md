# Extractie-template voor video-analyse-agents

Pas de secties aan op het onderwerp, maar behoud de structuur. De agent
schrijft het volledige document naar de scratchpad en geeft een korte
samenvatting terug.

## Vaste secties (elke video)

1. **Spreker(s) & context**: wie spreekt, welke autoriteit of track record
   claimen ze, wat verkopen ze (bias-flag)
2. **Kernthese**: het centrale argument in 3-8 zinnen
3. **Frameworks**: elk framework VOLLEDIG gereproduceerd (stappen, volgorde,
   onderdelen), niet samengevat
4. **Alle getallen**: budgetten, percentages, thresholds, benchmarks,
   case-resultaten, met de context waarin ze genoemd werden
5. **Beslisregels**: elke als-dit-dan-dat regel die operationeel bruikbaar is
6. **Concrete cases**: elk voorbeeld met resultaten indien genoemd
7. **Letterlijke quotes**: 10-18 meest waardevolle (licht opgeschoond qua
   interpunctie mag)
8. **Meningen vs onderbouwde claims**: waar zit data, waar opinie of
   verkooppraatje
9. **Tijdgebonden vs tijdloos**: wat is mogelijk verouderd per vandaag
   (upload-datum expliciet meewegen), wat is structureel
10. **Toepasbaarheid op jouw merk**: vul hier bij het spawnen van de agent
    de merkcontext uit `.claude/skills/BRAND-CONFIG.md` in (product,
    positionering, markt, business model, budget-tier). De agent
    beoordeelt: wat past, wat vloekt met de positionering of de
    brand-truth
11. **Visuele gaten**: tabellen, screenshots of voorbeelden die in beeld
    waren maar niet voorgelezen werden
12. **Tegenstrijdigheden**: waar spreekt de spreker zichzelf tegen

## Instructies aan de agent

- Auto-captions hebben geen interpunctie en garbelen namen: corrigeer uit
  context en noteer de correcties
- Wees exhaustief: elk operationeel bruikbaar detail, niets overslaan
- Lange transcripts (>100k tekens) in delen lezen maar volledig dekken
- Guardrail in sectie 10: toets elke claim of tactiek die de video
  aanraadt aan de verboden-claims-lijst uit BRAND-CONFIG
