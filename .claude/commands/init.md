# /init — New User Setup

You are setting up a new user's Personal Board of Directors system. Walk them through building their profile interactively, then write it to `memory/profile.md`.

## Step 1 — Welcome

Start with this message (adapt tone naturally, don't read it verbatim):

> Welcome to your Personal Board of Directors — a multi-agent AI advisory system that gives you honest, research-backed advice on career, social life, personal growth, and wherever you are in life.
>
> Before your advisors can help you properly, they need to know who you are. I'll ask you a few questions — the more honestly you answer, the better every future response will be. This takes about 5 minutes.
>
> Everything stays on your machine. Ready?

Wait for the user to confirm before continuing.

## Step 2 — Ask Questions (one section at a time)

Ask these in natural conversation — don't send all questions at once. Ask a section, wait for the answer, then move to the next. Acknowledge what they say before asking the next question.

**Section 1 — The basics**
- What's your name?
- How old are you, and where are you based right now?
- Where are you originally from?

**Section 2 — What you're doing**
- Are you a student, working, or both? What are you studying or doing?
- What's your career goal — what do you want to be doing in 3–5 years?
- If you're an international student or on a work permit, mention that — it matters for career advice.

**Section 3 — Social life (honest answer)**
- How would you describe your social situation right now — thriving, building, or starting from scratch?
- Are you single or in a relationship? Are you looking?
- Who are the important people in your life right now (friends, family, mentors)?

**Section 4 — Who you are**
- How would you describe yourself in 3–5 honest words?
- What do people come to you for? And what do you know is a blind spot for you?
- What do you actually care about — your real values, not the polished version?

**Section 5 — Right now**
- What's your #1 priority this year?
- What's the hardest thing going on right now?
- What does a genuinely good year look like for you?

## Step 3 — Write the Profile

Once you have all their answers, write `memory/profile.md` using the template below. Fill in every field with what they told you — don't leave any section as a placeholder if they gave you the information. Write in third person ("they are", "their goal") — it reads better for the advisory agents.

```markdown
# My Profile

> Update anytime with: /update-profile [new info]

## Basic Info
- **Name:** [name]
- **Age:** [age]
- **Location:** [city, country]
- **Originally From:** [country/city]
- **Languages:** [languages]

## Academic / Work Life
- **Current situation:** [student / working / both — details]
- **Program or Role:** [degree or job title]
- **Institution / Company:** [name]
- **Expected graduation or tenure:** [date if applicable]
- **Immigration status:** [citizen / PR / student visa / work permit — if relevant]

## Career
- **Career goal:** [what they want to do in 3–5 years]
- **Current experience:** [jobs, internships, projects]
- **Dream role / company:** [specific if they said so]

## Social Life
- **Relationship status:** [single / dating / etc.]
- **Social situation:** [their honest description]
- **Important people:** [who they named]
- **What they're looking for:** [romantic / friendships / community / all]

## Personality & Values
- **Self-description:** [their 3–5 words]
- **Strengths:** [what they said]
- **Known blind spots:** [what they said]
- **Core values:** [what they said]

## Goals (this year)
- **#1 priority:** [their answer]
- **Other goals:**
  - [any additional goals mentioned]

## Context
- **Why they set this up:** [their reason if given]
- **Biggest current challenge:** [their answer]
- **What good looks like:** [their answer]
```

## Step 4 — Confirm and Orient

After writing the file, tell them:

1. Their profile has been saved to `memory/profile.md` — they can update it anytime with `/update-profile [new info]`
2. Give them 2–3 starter commands that are most relevant to what they shared. Examples:
   - If they mentioned a career question → `/research [their specific question]`
   - If they mentioned something social → `/research [their situation]`
   - If they mentioned a specific decision → `/compare [option A] vs [option B]`
3. Remind them that every advisor reads their profile before responding — no generic advice, ever.

Keep the closing message brief and warm. They're ready to go.
