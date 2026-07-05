---
name: yt-learnings
description: |
  Analyseer YouTube-video's (expert-talks, podcasts, masterclasses) op
  transcript-niveau en destilleer elk operationeel detail: frameworks,
  getallen, beslisregels, quotes. Draait parallelle analyse-agents per
  video, checkt actualiteit van de adviezen, en stelt voor welke bestaande
  skills een update verdienen. Werkt op captions; kan beeld niet zien
  (limitaties staan in de skill).
  AUTO-ACTIVATE bij: "analyseer deze video", "analyseer deze youtube",
  "haal learnings uit", "yt learnings", "analyseer deze podcast",
  "wat zegt deze video", "maak skills van deze video".
---

# YT Learnings

Doel: van een YouTube-link naar een exhaustief, gestructureerd
kennisdocument, en van dat document naar concrete skill-updates. Dit is de
pipeline waarmee deze Meta ads-skillset (juli 2026) is gebouwd.

## Wat deze skill wel en niet kan (eerlijk)

- **Wel:** volledige transcripts + metadata binnenhalen en uitpluizen.
  Voor gesproken kennis (talks, podcasts, masterclasses) vangt dit vrijwel
  alles: frameworks, getallen, redeneringen, quotes.
- **Niet:** beeld zien. Screenshots van dashboards, getoonde ad-voorbeelden
  en tabellen in beeld gaan verloren als de spreker ze niet voorleest.
  Flag dit per video ("in de video staat een tabel die niet wordt
  voorgelezen"). Voor visuele ad-breakdowns: lever zelf screenshots van
  de key frames aan, of gebruik een video-analyse-platform (bijv.
  Higgsfield `video_analysis_create`, indien gekoppeld) voor losse
  videobestanden.
- Auto-captions bevatten garbles (namen, productnamen). Corrigeer uit
  context en noteer de correctie.

## Stap 1: Setup (eenmalig per sessie)

Werk in de scratchpad-directory. Zet daar een venv op:

```bash
cd "$SCRATCHPAD" && python3 -m venv ytenv
./ytenv/bin/pip install -q yt-dlp youtube-transcript-api
```

## Stap 2: Metadata + transcript per video

Metadata (bij bot-detectie-fout "page needs to be reloaded": android client):

```bash
./ytenv/bin/yt-dlp --skip-download \
  --extractor-args "youtube:player_client=android" \
  --print "%(id)s | %(title)s | %(channel)s | %(upload_date)s | %(duration_string)s" \
  "https://www.youtube.com/watch?v=<ID>"
```

Transcript (betrouwbaarder dan yt-dlp voor captions):

```python
from youtube_transcript_api import YouTubeTranscriptApi
api = YouTubeTranscriptApi()
t = api.fetch("<VIDEO_ID>", languages=["en","nl"])
text = " ".join(s.text for s in t)
# wegschrijven naar $SCRATCHPAD/transcript_<ID>.txt
```

Faalt de transcript-API (geen captions): meld het eerlijk en stop voor die
video. Geen samenvattingen verzinnen op basis van titel en comments.

## Stap 3: Parallelle analyse-agents

Eén agent per video (Agent-tool, in één bericht bij meerdere video's).
Elke agent krijgt:

- Het transcript-pad + video-metadata
- De extractie-template uit `references/extractie-template.md`, aangepast
  aan het onderwerp van de video, met jouw merkcontext uit
  `.claude/skills/BRAND-CONFIG.md` ingevuld in de toepasbaarheids-sectie
- De opdracht om het volledige analyse-document naar de scratchpad te
  schrijven en max 400-500 woorden samenvatting terug te geven
- Bij transcripts boven ~100k tekens: instructie om in delen te lezen
  (offset/limit) maar alles te dekken

## Stap 4: Actualiteits-check (bij tactisch advies altijd doen)

Expert-video's verouderen snel (platform-features, algoritmes, wetgeving).
Draai bij tactische onderwerpen een aparte research-agent (WebSearch) die
de huidige stand ophaalt en per video-advies een verdict geeft: nog geldig,
gewijzigd, of achterhaald. Zonder deze stap geen skills bouwen op de video.

## Stap 5: Synthese en skill-voorstellen

1. Kruisverbanden tussen de video's benoemen (waar spreken bronnen elkaar
   tegen, waar bevestigen ze elkaar)
2. Bias-check per bron: wat verkoopt de spreker (agency, cursus, tool)?
3. Voorstel: welke bestaande skills verdienen een update, of welke nieuwe
   skill is gerechtvaardigd. Analyse-documenten die bewaard moeten blijven
   horen in de references/ van de betreffende skill (scratchpad is
   tijdelijk!). Kopieer ze daarheen zodra jij akkoord geeft.
4. BRAND-CONFIG en je eigen kennisbank: nooit beschrijven zonder
   expliciete vraag.

## QC-checklist

- [ ] Elk analyse-document dekt het VOLLEDIGE transcript, niet alleen het
      eerste deel
- [ ] Upload-datum benoemd + wat mogelijk verouderd is per vandaag
- [ ] Meningen gescheiden van onderbouwde claims
- [ ] Bias van de spreker geflagd
- [ ] Visuele gaten benoemd (tabellen/voorbeelden die niet zijn voorgelezen)
- [ ] Waardevolle analyses veiliggesteld buiten de scratchpad
