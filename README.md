# Eris Cards — Agent Lense

> E.R.I.S. Architecture — One truth, seen through many eyes.

The **Agent Lense** of the E.R.I.S. Architecture. AI agents query this repo to access Eris's Skill Cards as structured data.

## E.R.I.S. Architecture

| Principle | This Repo |
|-----------|-----------|
| **E** — Essential Core | Cards carry the design philosophy (LDD) in their structure |
| **R** — Representation through Lenses | This is the **Agent Lense** — same data, optimized for machines |
| **I** — Independence from Infrastructure | Data lives here independent of any app or platform |
| **S** — Single Source of Truth | Auto-synced from the SOT (`eris-blog`) on every build |

### Three Lenses

| Lense | Repo | For |
|-------|------|-----|
| Human Lense | [eris-blog](https://eris-blog.vercel.app/cards) | Humans read cards as styled pages |
| **Agent Lense** | **eris-cards** (this repo) | **AI agents query structured data** |
| Interactive Lense | [eris-deck](https://eris-deck.vercel.app) | Users build decks interactively |

## Files

| File | Format | Use |
|------|--------|-----|
| `cards.json` | JSON | Structured card data (AI Agent First v2.0) |
| `llms-full.txt` | Plaintext | Full blog + cards content for LLMs |
| `llms.txt` | Plaintext | Site summary |

## cards.json — AI Agent First Design (v2.0)

Structured for the three phases of agent cognition:

| Phase | Fields | Purpose |
|-------|--------|---------|
| **Decision** | `when_to_use`, `rarity`, `tags` | Should I use this card? |
| **Execution** | `effect`, `steps`, `prompt` | How do I use it? |
| **Navigation** | `requires`, `synergies`, `trees` | What should I equip next? |

## Access

```
# JSON (structured)
https://raw.githubusercontent.com/eris-ths/eris-cards/main/cards.json

# Plaintext (full content)
https://raw.githubusercontent.com/eris-ths/eris-cards/main/llms-full.txt

# Summary
https://raw.githubusercontent.com/eris-ths/eris-cards/main/llms.txt
```

## Data Flow

```
src/content/cards/*.md (SOT, in eris-blog)
  ↓ git push
  ↓ GitHub Actions (auto)
  ├── Astro build → HTML on Vercel (Human Lense)
  ├── generate-cards-json.cjs → cards.json
  └── sync → this repo (Agent Lense)
                ↓ fetch
          eris-deck (Interactive Lense)
```

Humans edit the SOT only. Everything else is automatic.

## Related

- [E.R.I.S. Architecture](https://eris-blog.vercel.app/blog/2026-04-02-eris-architecture) — The pattern definition
- [Skill Cards](https://eris-blog.vercel.app/cards) — Human Lense
- [Eris Deck](https://eris-deck.vercel.app) — Interactive Lense
- [eris-blog](https://github.com/eris-ths/eris-blog) (private) — SOT

---

*Auto-synced from eris-blog by GitHub Actions*
*E.R.I.S. Architecture — One truth, seen through many eyes.*
