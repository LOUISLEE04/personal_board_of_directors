# Personal Board of Directors

A multi-agent AI advisory system built in Claude Code. Six specialized advisors work in parallel as your personal board of directors — giving strong opinions, honest verdicts, and specific action plans grounded in YOUR situation.

Not a generic chatbot. Not a search engine. A system that remembers your context, checks what you've already tried, and gives you the honest answer instead of the comfortable one.

---

## Quick Start

### Prerequisites
- Claude Pro ($20/mo) or Max ($100/mo recommended) subscription
- Claude Code installed: `npm install -g @anthropic-ai/claude-code`
- Make sure you do NOT have `ANTHROPIC_API_KEY` set (so it uses your subscription, not API credits)

```bash
# Check if API key is set (should return empty)
echo $ANTHROPIC_API_KEY

# If it's set, unset it
unset ANTHROPIC_API_KEY
```

### Setup

```bash
# Clone the repo
git clone https://github.com/[your-username]/personal-board-of-directors
cd personal-board-of-directors
```

No dependencies to install. That's it.

### Fill In Your Profile

Open `memory/profile.md` and fill in your details honestly. The more context you give, the better your advisors perform. **This file stays on your machine — it's in `.gitignore` by default once you've personalised it.**

### Start Using It

```bash
# Launch Claude Code in the project folder
claude

# Full multi-agent research on a life decision
/research should I take the startup offer or wait for big tech

# Quick single question
/quick-research best way to negotiate a first salary offer

# Go deeper on a specific angle
/deep-dive career-planning — which companies sponsor work visas for CS grads

# Compare two options head-to-head
/compare staying in this city vs moving for the job

# Situation-specific playbook
/tactical how do I bring up the promotion conversation with my manager

# Review your life across all areas
/review

# Update your profile as things change
/update-profile I just started a new internship at a fintech startup

# Clean up and compress memory (run weekly)
/memory-consolidate
```

---

## Your Board of Directors

| Advisor | Role |
|---------|------|
| **Social Advisor** | Dating, friendships, loneliness, social confidence, relationship strategy |
| **Local Life Guide** | Events, groups, activities, social spots, local community knowledge |
| **Evidence Researcher** | Studies, data, expert sources on any topic — goes 8–10 searches deep |
| **Career Advisor** | CS career, university resources, immigration pathways, internship strategy |
| **Chinese Internet Researcher** | Searches 知乎, 小红书, Bilibili in Mandarin — Asian diaspora perspective |
| **Real Talk (Synthesizer)** | The final word. Strong verdict, specific action plan, no wishy-washy |

---

## Smart Dispatch

Not every question needs all 6 advisors. The system classifies your question and dispatches only the relevant ones:

| Question Type | Agents Used |
|---|---|
| Social | Social Advisor + Local Life Guide + Real Talk |
| Career | Career Advisor + Evidence Researcher + Real Talk |
| Local life | Local Life Guide only |
| Health | Evidence Researcher only |
| Personal growth | Evidence Researcher + Social Advisor + Real Talk |
| Complex / life decisions | ALL agents + Real Talk |

---

## Commands

| Command | What It Does |
|---------|-------------|
| `/research [topic]` | Full multi-advisor deep research with evidence and action plan |
| `/quick-research [question]` | Light 1–2 advisor lookup for fast answers |
| `/deep-dive [topic] — [angle]` | Go deeper on a specific aspect of a previous research topic |
| `/compare [A] vs [B]` | Head-to-head comparison with a clear winner and reasoning |
| `/tactical [situation]` | Specific playbook for a real-life moment — exact scripts, failure modes |
| `/review` | Life dashboard across all areas — career, social, health, growth |
| `/brief` | Personalised morning news digest curated to your context |
| `/ai-brief` | AI and tech news brief — model releases, industry moves, CS career news |
| `/update-profile [info]` | Update your personal profile |
| `/memory-consolidate` | Clean up and compress memory files |
| `/reflect [topic]` | Deep personal reflection session |

---

## Memory Structure

```
memory/
├── profile.md          # YOU — fill this in first
├── cs-profile.md       # Your technical skills and project state
├── research-log.md     # Running log of all advisory sessions (auto-managed)
├── decisions.md        # Major decisions made — append-only audit trail
├── open-questions.md   # Unresolved questions from research sessions
├── nudges.md           # Free-time task list
└── outreach-tracker.md # Contacts and outreach attempts — agents read this to avoid repeating failed suggestions

research/
└── [topic]/
    ├── session-log.md        # Audit trail
    ├── evidence-findings.md  # Evidence Researcher output
    ├── social-findings.md    # Social Advisor output
    ├── career-findings.md    # Career Advisor output
    ├── pei-findings.md       # Local Life Guide output
    ├── chinese-findings.md   # Chinese Internet Researcher output
    └── final-report.md       # Real Talk final verdict
```

---

## Customising for Your Life

### /brief topics
By default `/brief` surfaces general world and tech news. To customise what it tracks, open `CLAUDE.md` and add a `/brief` preferences section:

```markdown
### /brief Preferences
Topics I want tracked:
- [e.g. "Canadian immigration policy"]
- [e.g. "early-stage startup funding"]
- [e.g. "machine learning research"]
```

### Local Life Guide
The `pei-local` agent is named after PEI (Prince Edward Island, Canada) but works for any location. Just tell it your city in `memory/profile.md` and it'll search locally.

### Chinese Internet Researcher
Optional — most valuable if you're from an Asian background or want the Chinese diaspora perspective on a topic. Skip it if not relevant to you.

---

## Tips

### Make It Personal
- Fill in `memory/profile.md` thoroughly — the advisors reference YOUR situation, not generic advice
- Be honest about your struggles — the system handles sensitive topics with care
- Update your profile whenever something changes

### Go Deep, Not Shallow
- After `/research`, do 1–2 `/deep-dive` follow-ups on the most important aspects
- Ask specific questions — the more context you give, the better the output

### Manage Your Usage
- On Pro ($20/mo): ~10–40 prompts per 5-hour window. A full `/research` uses ~10–20. Budget 2–3 sessions per window
- On Max 5x ($100/mo): ~50–200 prompts per window. Can do 5+ sessions comfortably
- Use `/quick-research` for follow-ups to save quota
- Single-agent dispatches (LOCAL-LIFE, HEALTH) are the cheapest

### Keep Memory Healthy
- Run `/memory-consolidate` every week or two
- Review `/review` dashboard periodically to spot patterns
- Update profile.md whenever something significant changes

---

All data stays on your machine. No API keys needed — runs on your Claude subscription.
