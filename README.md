# PatternOS
### Personal Operating System — Andy Styx

This repo is the context layer for my life and work. It makes any AI tool I use aware of who I am, what I'm working on, and how I operate — without re-explaining every session.

---

## How to Use This Repo

**If you are an AI tool:** Fetch `CLAUDE.md` first. It tells you everything else you need and where to find it.

**If you are me:** Update the context files when things change. The JSON files are the live state. CLAUDE.md and the skill files change less frequently.

**One URL to start any session:**
```
https://raw.githubusercontent.com/dudeitsandy/patternos/main/CLAUDE.md
```

---

## File Index

### Master Context
| File | Purpose | Update frequency |
|------|---------|-----------------|
| `CLAUDE.md` | Root context — who I am, agent roster, active projects, working style | Monthly or on major life change |

### Context Files (live state)
| File | Purpose | Update frequency |
|------|---------|-----------------|
| `context/career_compass.json` | Values, non-negotiables, opportunity filter rules | On career shift or values update |
| `context/current_load.json` | Active projects, capacity %, open decisions | Weekly |
| `context/decisions_log.json` | Append-only log of evaluated opportunities | On each decision |
| `context/health_goals.json` | Running, strength, nutrition, rehab targets | On goal change or race cycle |
| `context/hobby_log.json` | Hobby sessions, energy tracking, protection rules | Weekly |
| `context/people_personal.json` | Personal CRM — relationship tiers and cadences | On relationship changes |

### Skills (standing instruction sets by mode)
| File | Purpose | Load when... |
|------|---------|-------------|
| `skills/coding.md` | Stack, patterns, output standards, project context | Any code task |
| `skills/design.md` | Aesthetic, tools, UI principles, brand reference | Any visual or UI task |
| `skills/writing.md` | Voice rules, format by type, active writing projects | Any writing task |
| `skills/people_analytics.md` | Tacit domain knowledge — data instincts, edge cases, stakeholder patterns, RIF execution | Any people analytics or HR data task |

---

## Raw URLs (copy-paste into any AI tool)

### Master
```
https://raw.githubusercontent.com/dudeitsandy/patternos/main/CLAUDE.md
```

### Context
```
https://raw.githubusercontent.com/dudeitsandy/patternos/main/context/career_compass.json
https://raw.githubusercontent.com/dudeitsandy/patternos/main/context/current_load.json
https://raw.githubusercontent.com/dudeitsandy/patternos/main/context/decisions_log.json
https://raw.githubusercontent.com/dudeitsandy/patternos/main/context/health_goals.json
https://raw.githubusercontent.com/dudeitsandy/patternos/main/context/hobby_log.json
https://raw.githubusercontent.com/dudeitsandy/patternos/main/context/people_personal.json
```

### Skills
```
https://raw.githubusercontent.com/dudeitsandy/patternos/main/skills/coding.md
https://raw.githubusercontent.com/dudeitsandy/patternos/main/skills/design.md
https://raw.githubusercontent.com/dudeitsandy/patternos/main/skills/writing.md
https://raw.githubusercontent.com/dudeitsandy/patternos/main/skills/people_analytics.md
```

---

## Agent Roster (defined in CLAUDE.md)

| Agent | Role | Primary files |
|-------|------|--------------|
| DISPATCH | Orchestrator — routes to other agents | current_load.json |
| FILTER | Evaluates opportunities against values and capacity | career_compass.json, current_load.json |
| LEDGER | Weekly synthesis — capacity, health, hobby flags | current_load.json, health_goals.json, hobby_log.json |
| MIRROR | Personal relationship management | people_personal.json |
| SCOUT | Research and intel briefings | web fetch + any relevant context |
| FORGE | Ghostweave Labs business ops | current_load.json |
| LOOM | Creative projects and protection | hobby_log.json |

---

## Repo Structure

```
patternos/
├── CLAUDE.md
├── README.md
├── context/
│   ├── career_compass.json
│   ├── current_load.json
│   ├── decisions_log.json
│   ├── health_goals.json
│   ├── hobby_log.json
│   └── people_personal.json
└── skills/
    ├── coding.md
    ├── design.md
    ├── people_analytics.md
    └── writing.md
```

---

## Setup by AI Tool

**Claude Desktop / Claude Code**
Place `CLAUDE.md` at `C:\Users\subfl\workspace\patternos\CLAUDE.md`. Claude Code reads it automatically at session start.

**Claude.ai**
Paste the CLAUDE.md raw URL at the start of any conversation. Or attach the file to a Project for persistent context.

**ChatGPT**
Paste the CLAUDE.md raw URL into a Custom GPT system prompt, or at the start of any conversation.

**Gemini**
Paste the CLAUDE.md raw URL at the start of a conversation.

**Any other tool**
Same pattern — paste the CLAUDE.md raw URL. The file is self-documenting.

---

*GitHub: [dudeitsandy/Patternos](https://github.com/dudeitsandy/Patternos)*