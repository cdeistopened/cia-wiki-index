# CIA Plugin & Wiki Index

Master catalog of all Creative Intelligence Agency plugins, wikis, and skill bundles. Each "Ask [Creator]" plugin turns a content archive into interactive AI coaching skills for Claude Code. Each wiki is the public-facing searchable site.

**Website:** [creativeintel.agency](https://creativeintel.agency)

---

## Creator Plugins (15 active)

Install any plugin by cloning the repo and adding its path to your Claude Code settings.

| Plugin | Skills | Repo (plugin) | Repo (site) | Live Domain | Status |
|--------|--------|---------------|-------------|-------------|--------|
| **Ask Sam** | 18 | [ask-sam](https://github.com/cdeistopened/ask-sam) | [mfm-wiki](https://github.com/cdeistopened/mfm-wiki) | [myfirstmillion.wiki](https://myfirstmillion.wiki) | Live |
| **Ask Kellblog** | 45 | — | — | — | Plugin built, no repo |
| **Ask Hormozi** | 22 | [hormozi-wiki](https://github.com/cdeistopened/hormozi-wiki) | same | [alexhormozi.wiki](https://alexhormozi.wiki) | Live |
| **Ask Naval** | 21 | [naval-wiki](https://github.com/cdeistopened/naval-wiki) | same | [naval-wiki.vercel.app](https://naval-wiki.vercel.app) | Live |
| **Ask GaryVee** | 20 | [garyvee-wiki](https://github.com/cdeistopened/garyvee-wiki) | same | [garyvaynerchuk.wiki](https://garyvaynerchuk.wiki) | Live |
| **Ask Dr. Miller** | 18 | [dr-richard-l-miller](https://github.com/cdeistopened/dr-richard-l-miller) | — | — | Plugin built |
| **Ask Huberman** | 12 | [huberman-wiki](https://github.com/cdeistopened/huberman-wiki) | same | [huberman.wiki](https://huberman.wiki) | Live |
| **Ask Balaji** | 16 | [balaji-wiki](https://github.com/cdeistopened/balaji-wiki) | same | [balaji.wiki](https://balaji.wiki) | Live |
| **David Perell** | 16 | [perell-wiki](https://github.com/cdeistopened/perell-wiki) | — | — | Plugin built |
| **Ask KDP Kings** | 15 | [kdp-kings-wiki](https://github.com/cdeistopened/kdp-kings-wiki) | same | [kdp-kings-wiki.vercel.app](https://kdp-kings-wiki.vercel.app) | Live |
| **Ask Scott Adams** | 13 | [scott-adams-wiki](https://github.com/cdeistopened/scott-adams-wiki) | same | [scottadams.wiki](https://scottadams.wiki) | Live |
| **Ask Matt McGarry** | 12 | [matt-mcgarry-wiki](https://github.com/cdeistopened/matt-mcgarry-wiki) | — | — | Plugin built |
| **Ask Lenny** | 11 | [lennys-wiki](https://github.com/cdeistopened/lennys-wiki) | same | [lennyrachitsky.wiki](https://lennyrachitsky.wiki) | Live |
| **Ask EndMyopia** | 9 | [endmyopia-wiki](https://github.com/cdeistopened/endmyopia-wiki) | — | — | Plugin built |
| **Ask Ray Peat** | 7 | [raypeat-wiki](https://github.com/cdeistopened/raypeat-wiki) | — | [raypeatdiet.com](https://raypeatdiet.com) | Plugin built |
| **Ask Neil Patel** | 6 | [neil-patel-wiki](https://github.com/cdeistopened/neil-patel-wiki) | same | [neil-patel-wiki.vercel.app](https://neil-patel-wiki.vercel.app) | Live |

**Archived:** Ask Zakery / How to Think (10 skills) — [ask-how-to-think](https://github.com/cdeistopened/ask-how-to-think)

### Quick Install

```bash
# Clone any plugin
git clone https://github.com/cdeistopened/ask-sam.git ~/.claude/plugins/ask-sam

# Add to Claude Code settings (~/.claude/settings.json)
{
  "plugins": [
    "/Users/you/.claude/plugins/ask-sam"
  ]
}

# Restart Claude Code, then:
/ask-sam
```

---

## Native Plugins (Domain Skill Packs)

Thematic skill bundles — not tied to a single creator. All 8 in one repo: [**cia-native-plugins**](https://github.com/cdeistopened/cia-native-plugins)

```bash
git clone https://github.com/cdeistopened/cia-native-plugins.git ~/.claude/plugins/cia-native-plugins
```

| Plugin | Skills | Domain |
|--------|--------|--------|
| **business-plugin** | 21 | Strategy, ops, scaling, mental models, sales |
| **podcast-plugin** | 15 | Transcript → clips → content engine |
| **publishing-plugin** | 12 | KDP, book production, covers, listings |
| **youtube-plugin** | 11 | Scripts, titles, thumbnails, outlier analysis |
| **social-plugin** | 11 | Content creation, virality, ad creative |
| **research-plugin** | 7 | Deep research, competitive intel, site audits |
| **seo-plugin** | 7 | Search optimization, content strategy |
| **writing-plugin** | 5 | Voice extraction, ghostwriting, clear prose |

---

## Standalone Skill Catalog

| Repo | What | Skills |
|------|------|--------|
| [skill-stack-skills](https://github.com/cdeistopened/skill-stack-skills) | Full catalog of all CIA-authored skills | 154 |

---

## Pipeline (Not Yet Plugin)

| Creator | Transcripts | Site | Next Step |
|---------|-------------|------|-----------|
| MoneyWise (Sam Parr) | 83 | [moneywise-wiki.vercel.app](https://moneywise-wiki.vercel.app) | Merge into ask-sam |
| RLM (Dr. Miller) | 337 | — | Build plugin (started at `clients/rlm/plugin/`) |
| Beekeeping | 183+ | — | Transcribe |
| Kellblog | 767 posts | — | Framework extraction |
| Colin & Samir | 12 | — | Extract frameworks |
| Kallaway | 8 | — | Extract frameworks |
| Jenny Hoyos | 5 | — | Extract frameworks |

---

## Architecture

Each wiki project follows the same structure:

```
[creator]-wiki/
├── site/              ← Quartz static site (deployed to Vercel)
│   └── content/       ← Episodes, articles, people, skills
├── plugin/            ← Claude Code plugin source
│   ├── skills/        ← Interactive SKILL.md files
│   └── references/    ← Frameworks, people, transcripts
├── data/              ← Raw transcripts, chunks, vectors (local only)
└── pipeline/          ← Transcription & enrichment scripts (local only)
```

**Shared infrastructure:**
- Shared Quartz theme: `_shared-theme/`
- Shared backend (RAG API): `shared-backend/` on Railway
- Pipeline library: `lib/` (transcriber, chunker, embedder, entity extractor)

---

## Totals

- **15 creator plugins** with **261 interactive skills**
- **8 native plugins** ([cia-native-plugins](https://github.com/cdeistopened/cia-native-plugins)) with **89 skills**
- **154 skills** in the standalone catalog
- **11 live wiki sites**
- **3,000+ transcripts** across all archives
- **7 creators** in the transcription pipeline

Built by [Creative Intelligence Agency](https://creativeintel.agency).
