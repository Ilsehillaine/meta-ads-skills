# Meta Ads Skills voor Claude Code

Een complete set Claude Code skills om Meta ads (Facebook/Instagram) op
hoog niveau te draaien als klein of middelgroot e-commerce merk. Gebouwd
op geanalyseerde expert-kennis (Nick Shackelford, Taylor Holiday/Common
Thread Collective, Carl Weische, D2C-scriptwriting-practitioners) plus
een actualiteits-check van het Meta-landschap per juli 2026 (Andromeda +
GEM, Advantage+ Sales, EU LPA/DMA).

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

| Skill | Job | Belangrijkste references |
|---|---|---|
| `meta-media-buyer` | structuur, budget, schalen, kickoff-vragen, budget-tier ladder (tier 0-4) | `campagne-kickoff.md` (tien vragen, tier-playbook met graduatie/kill-regels, creative-volume-formule), `bron-structuur-consensus-2026.md`, `bron-levi-steede-2026.md` |
| `ad-creative` | personas, angles, scripts, hooks, statics, productie-pipeline | `persona-playbook.md` (brief-format + naamgevings-conventie), `angle-research.md` (4-bronnen-scan), `angle-bank.md` (voorbeeld-casus), `script-bouwregels.md` |
| `offer-architect` | offers, bundels, garanties, eerlijke schaarste, EU Omnibus | `bron-weische-offers-2024.md` |
| `ad-preflight` | GO/NO-GO check op 5 lagen vóór elke launch | `instellingen-catalogus.md` (volledige catalogus, incl. existing-customer-cap-richtlijn) |
| `meta-ads-review` | account uitlezen en diagnosticeren (Meta Ads MCP), weekly review, knoppen-model | `diagnose-beslisboom.md` (incl. sluipende-daling-boom en de review-lat), `knoppen-model.md`, `tracking-audit.md` |
| `yt-learnings` | nieuwe expert-video's analyseren en de skillset actueel houden | `extractie-template.md` |

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

## Voor agencies

Deze set werkt voor één merk, maar ook als gestandaardiseerde
agency-werkwijze over meerdere klanten:

1. **Eén config-paar per klant.** Elke klant krijgt een eigen
   `BRAND-CONFIG.md` (merkwaarheid, unit economics, verboden claims) en
   een eigen `ADS-STATUS.md` (werkgeheugen: actieve campagnes, lopende
   tests, volgende acties), aangemaakt vanuit de templates en gevuld via
   `INTAKE.md`. Praktisch: één project of werkmap per klant, zodat de
   skills nooit configs kunnen verwisselen.
2. **Onderzoek is verplicht onderdeel van elke klant-onboarding.** De
   vorm is gestandaardiseerd, de context verschilt per klant: draai per
   klant de 4-bronnen-scan
   (`skills/ad-creative/references/angle-research.md`) en giet de output
   in persona-briefs volgens het vaste 10-velden-format
   (`skills/ad-creative/references/persona-playbook.md`). Geen
   campagne-kickoff zonder persona-brief; kickoff-vraag 6 dwingt dat af.
3. **Zelfde lat voor elke klant.** De naamgevings-conventie (persona-code
   in campagne-, ad set- en ad-naam plus utm_content) maakt learnings
   vergelijkbaar over klanten heen; de budget-tier ladder
   (`campagne-kickoff.md`) bepaalt per klant de structuur, nooit een
   standaard bureau-structuur.

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
