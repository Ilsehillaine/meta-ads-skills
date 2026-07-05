# Meta Ads Skills voor Claude Code

Een complete set Claude Code skills om Meta ads (Facebook/Instagram) op
hoog niveau te draaien als klein of middelgroot e-commerce merk. Gebouwd
op geanalyseerde expert-kennis (Nick Shackelford, Taylor Holiday/Common
Thread Collective, Carl Weische, D2C-scriptwriting-practitioners) plus
een actualiteits-check van het Meta-landschap per juli 2026 (Andromeda +
GEM, Advantage+ Sales, EU LPA/DMA).

Ontwikkeld voor en getest op het merk LAINE HILL.

## Filosofie

1. **Contribution margin is de baas.** Platform-ROAS staat onderaan de
   metrics-hiërarchie; je boekhouding is de waarheid, Ads Manager het
   gerucht.
2. **De creative is de targeting.** Manual targeting is per 2026 feitelijk
   ontmanteld; awareness-fasen en verhalen doen het richtwerk.
3. **First-order winstgevend.** Geen verlies-op-eerste-aankoop zonder
   bewezen repeat-gedrag.
4. **Human-in-the-loop bij geld.** Geen enkele skill muteert je ad-account
   zonder expliciete bevestiging per actie.
5. **Eigen baseline of geen baseline.** Sinds EU LPA (jan 2026) zijn oude
   benchmarks onbruikbaar; je eigen data is de lat.

## De skills en hoe ze samenwerken

```
campagne-kickoff (10 vragen + budget-tiers)
        │
        ▼
ad-creative ──── offer-architect
   (angles,          (aanbod,
    scripts,          bundels,
    statics)          garanties)
        │                │
        └───────┬────────┘
                ▼
          ad-preflight  ←  GO/NO-GO poort, volledige
                │           instellingen-catalogus
                ▼
         meta-ads-review  ←  launch (met jouw ja per actie),
                │            weekly review, diagnose
                ▼
          knoppen-model  ←  welke knop faalt: hook, hold,
                             click, LP, offer of marge?
```

| Skill | Job |
|---|---|
| `meta-media-buyer` | structuur, budget, schalen, kickoff-vragen, budget-tier playbook |
| `ad-creative` | angles, scripts, hooks, statics, productie-pipeline |
| `offer-architect` | offers, bundels, garanties, eerlijke schaarste, EU Omnibus |
| `ad-preflight` | GO/NO-GO check op 5 lagen vóór elke launch, incl. volledige instellingen-catalogus |
| `meta-ads-review` | account uitlezen en diagnosticeren (Meta Ads MCP), weekly review, knoppen-model |
| `yt-learnings` | nieuwe expert-video's analyseren en de skillset actueel houden |

## Installatie

1. Kopieer de mappen uit `skills/` naar `.claude/skills/` in je project.
2. Kopieer `BRAND-CONFIG-template.md` naar `.claude/skills/BRAND-CONFIG.md`.
3. Kopieer `ADS-STATUS-template.md` naar `.claude/skills/ADS-STATUS.md`:
   dit is het werkgeheugen van je ads-operatie. Open je een nieuwe
   terminal, dan leest `meta-ads-review` dit eerst en weet Claude direct
   waar je staat (actieve campagnes, lopende tests, volgende acties).
4. Vul de config via de vragenlijst in `INTAKE.md`. Doe dit VOORDAT je
   iets anders doet: de skills weigeren terecht te adviseren zonder
   ingevulde marge-cijfers.
5. Optioneel: koppel een Meta Ads MCP-server voor `meta-ads-review`
   (de skill werkt ook zonder, via CSV-exports).

`BRAND-CONFIG.md` en `ADS-STATUS.md` staan in `.gitignore`: die bestanden
bevatten jouw privé-data (pixel-ID, marges, teststatus) en horen nooit in
een publieke repo.

## Wat je zelf moet aanleveren

Zie `INTAKE.md` voor de volledige vragenlijst. De kern:

- **Unit economics**: verkoopprijzen, inkoopprijs per product, verzend-
  kosten, betaalfees, retourpercentage. Hieruit volgt je break-even CAC,
  het getal waar elke beslissing op stuurt.
- **Merkwaarheid**: wat je product wél en níet is, en welke claims
  verboden zijn (juridisch en ethisch).
- **Business model**: continu of drop-based, en je owned-media-kalender.
- **Assets**: welke foto's/video's er zijn (echte beelden zijn je
  hero-assets; AI is voor varianten).
- **Tracking**: pixel/dataset-ID, CAPI-status, consent-setup.

## Wat deze skills bewust NIET doen

- Geen automatische mutaties in je ad-account
- Geen schaal-advies zonder marge-cijfers en voorraadstand
- Geen benchmarks van vóór 2026 als bewijs
- Geen discount-trucs die een premium merk slopen
- Geen beloftes: de skills structureren beslissingen, spend en iteratie
  doen het werk

## Bronnen

De `references/bron-*.md` bestanden bevatten geanonimiseerde, gedistil-
leerde analyses van publieke expert-video's, met bronvermelding. Ze zijn
de kennislaag onder de skills; de skills zelf zijn de operationele laag.

## Taal en roadmap

- v1 is Nederlands; een Engelse vertaling staat op de roadmap
- Geplande uitbreidingen: learnings-log skill (zodra 3+ maanden eigen
  data), Engelstalige versie, voorbeeldrapporten

## Licentie

MIT. Gebruik het, verbeter het, deel het terug.
