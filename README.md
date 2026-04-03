# CIA Wiki Index

Master catalog of all Creative Intelligence Agency wiki projects. Each wiki turns a creator's archive into a searchable site and an AI coaching plugin for Claude Code.

**Website:** [creativeintel.agency](https://creativeintel.agency)

---

## Live Sites

| Creator | Domain | Repo | Status |
|---------|--------|------|--------|
| Sam Parr / MFM | [myfirstmillion.wiki](https://myfirstmillion.wiki) | [mfm-wiki](https://github.com/cdeistopened/mfm-wiki) | Live |
| Naval Ravikant | [naval-wiki.vercel.app](https://naval-wiki.vercel.app) | [naval-wiki](https://github.com/cdeistopened/naval-wiki) | Live |
| Alex Hormozi | [alexhormozi.wiki](https://alexhormozi.wiki) | [hormozi-wiki](https://github.com/cdeistopened/hormozi-wiki) | Live |
| Andrew Huberman | [huberman.wiki](https://huberman.wiki) | [huberman-wiki](https://github.com/cdeistopened/huberman-wiki) | Live |
| Lenny Rachitsky | [lennyrachitsky.wiki](https://lennyrachitsky.wiki) | [lennys-wiki](https://github.com/cdeistopened/lennys-wiki) | Live |
| Scott Adams | [scottadams.wiki](https://scottadams.wiki) | [scott-adams-wiki](https://github.com/cdeistopened/scott-adams-wiki) | Live |
| Balaji Srinivasan | [balaji.wiki](https://balaji.wiki) | [balaji-wiki](https://github.com/cdeistopened/balaji-wiki) | Live |
| GaryVee | [garyvaynerchuk.wiki](https://garyvaynerchuk.wiki) | [garyvee-wiki](https://github.com/cdeistopened/garyvee-wiki) | Live |
| KDP Kings | [kdp-kings-wiki.vercel.app](https://kdp-kings-wiki.vercel.app) | [kdp-kings-wiki](https://github.com/cdeistopened/kdp-kings-wiki) | Live |
| Neil Patel | [neil-patel-wiki.vercel.app](https://neil-patel-wiki.vercel.app) | [neil-patel-wiki](https://github.com/cdeistopened/neil-patel-wiki) | Live |
| MoneyWise | [moneywise-wiki.vercel.app](https://moneywise-wiki.vercel.app) | [moneywise-wiki](https://github.com/cdeistopened/moneywise-wiki) | Live |

All sites built with [Quartz 4.5](https://quartz.jzhao.xyz/) and deployed on Vercel.

---

## Claude Code Plugins

Install any plugin by cloning the repo and adding its path to your Claude Code settings.

| Plugin | Repo | Skills | What it does |
|--------|------|--------|-------------|
| **Ask Sam** | [ask-sam](https://github.com/cdeistopened/ask-sam) | 18 | Business frameworks from MFM + MoneyWise (876 episodes) |
| **Ask Naval** | [naval-wiki](https://github.com/cdeistopened/naval-wiki) | 21 | Philosophy, wealth, happiness, startups |
| **Ask Hormozi** | [hormozi-wiki](https://github.com/cdeistopened/hormozi-wiki) | 22 | Offers, scaling, acquisition, leads |
| **Ask Huberman** | [huberman-wiki](https://github.com/cdeistopened/huberman-wiki) | 18 | Neuroscience protocols, health optimization |
| **Ask Lenny** | [lennys-wiki](https://github.com/cdeistopened/lennys-wiki) | 11 | Product management, growth, hiring |
| **Ask Scott Adams** | [scott-adams-wiki](https://github.com/cdeistopened/scott-adams-wiki) | 13 | Persuasion, systems thinking, talent stacking |
| **Ask Balaji** | [balaji-wiki](https://github.com/cdeistopened/balaji-wiki) | 16 | Network state, crypto, geopolitics |
| **Ask GaryVee** | [garyvee-wiki](https://github.com/cdeistopened/garyvee-wiki) | 20 | Social media, personal brand, hustle |
| **Ask KDP Kings** | [kdp-kings-wiki](https://github.com/cdeistopened/kdp-kings-wiki) | 17 | Amazon self-publishing pipeline |
| **Ask Neil Patel** | [neil-patel-wiki](https://github.com/cdeistopened/neil-patel-wiki) | 6 | SEO, content marketing, traffic |
| **Ask Ray Peat** | [raypeat-wiki](https://github.com/cdeistopened/raypeat-wiki) | 50 | Bioenergetic health, nutrition, hormones |
| **Ask EndMyopia** | [endmyopia-wiki](https://github.com/cdeistopened/endmyopia-wiki) | 9 | Natural vision improvement |
| **David Perell** | [perell-wiki](https://github.com/cdeistopened/perell-wiki) | 16 | Nonfiction writing craft (editorial passes) |

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

Thematic skill bundles — not tied to a single creator.

| Plugin | Repo | Domain |
|--------|------|--------|
| Publishing | [cia-publishing-plugin](https://github.com/cdeistopened/cia-publishing-plugin) | KDP, book production |
| Social | [cia-social-plugin](https://github.com/cdeistopened/cia-social-plugin) | Social media content |
| Business | — | Business strategy |
| Podcast | — | Podcast production |
| Research | — | Research workflows |
| SEO | — | Search optimization |
| Writing | — | Writing craft |
| YouTube | — | YouTube content |

---

## Pipeline Status

| Creator | Transcripts | Plugin | Site | Next Step |
|---------|-------------|--------|------|-----------|
| Dr. Richard Louis Miller | 337 | — | — | Build plugin |
| Beekeeping | 183+ | — | — | Transcribe |
| Kellblog | 767 posts | — | — | Framework extraction |
| Colin & Samir | 12 | — | — | Extract frameworks |
| Kallaway | 8 | — | — | Extract frameworks |
| Jenny Hoyos | 5 | — | — | Extract frameworks |

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

- **13 plugins** with **237 interactive skills**
- **11 live wiki sites**
- **3,000+ transcripts** across all archives
- **6 creators** in the transcription pipeline

Built by [Creative Intelligence Agency](https://creativeintel.agency).
