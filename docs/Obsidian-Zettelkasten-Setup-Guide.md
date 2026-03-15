# Obsidian Zettelkasten Setup Guide

> **Purpose:** This file lives inside your Mastery vault as a permanent reference. Consult it whenever you need to understand the system, move notes, or set up a new feature.

---

## Table of Contents

1. [Initial Setup](#1-initial-setup)
2. [Folder Structure — What Each Folder Means](#2-folder-structure--what-each-folder-means)
3. [How Notes Flow Between Folders](#3-how-notes-flow-between-folders)
4. [Sample Notes in Each Folder](#4-sample-notes-in-each-folder)
5. [How to Write a Good Zettelkasten Note](#5-how-to-write-a-good-zettelkasten-note)
6. [Linking — The Heart of Zettelkasten](#6-linking--the-heart-of-zettelkasten)
7. [Tags Strategy](#7-tags-strategy)
8. [Templates Setup & Usage](#8-templates-setup--usage)
9. [Essential Plugins (Add After Week 4)](#9-essential-plugins-add-after-week-4)
10. [Daily Workflow](#10-daily-workflow)
11. [Weekly Maintenance Routine](#11-weekly-maintenance-routine)
12. [Keyboard Shortcuts Worth Learning](#12-keyboard-shortcuts-worth-learning)
13. [Common Mistakes to Avoid](#13-common-mistakes-to-avoid)
14. [Settings to Change on Day 1](#14-settings-to-change-on-day-1)

---

## 1. Initial Setup

### Step 1: Install Obsidian
- Download from [obsidian.md](https://obsidian.md) (Windows/Mac/Linux)
- Install the mobile app too (iOS/Android) — for capturing ideas on the go
- Both apps are **free** for personal use

### Step 2: Create Your Vault
1. Open Obsidian → "Create new vault"
2. Name: `Mastery`
3. Location: Choose a folder synced by your cloud service (OneDrive, Google Drive, iCloud, or Dropbox) — this gives you automatic backup + mobile access

### Step 3: Create the Folder Structure
Create these 8 folders inside your vault:

```
Mastery/
├── 00 Inbox/              ← Quick captures, raw thoughts, unprocessed
├── 01 Zettelkasten/       ← Permanent, atomic, linked notes (your knowledge base)
├── 02 Synthesis/          ← Cross-domain connections & original thinking
├── 03 Book Notes/         ← One file per book (summary + key ideas)
├── 04 Essays & Writing/   ← Your weekly essays, drafts, published pieces
├── 05 Decision Journal/   ← Major decisions logged with the decision framework
├── 06 Daily Notes/        ← Daily reflections, Stoic journal, wins
├── Templates/             ← Note templates (see Section 8)
```

> **Why these numbers?** Obsidian sorts folders alphabetically. Numbers force the order you want. `00` always stays at the top (your starting point), `Templates` at the bottom (rarely accessed).

### Step 4: Copy This File Into Your Vault
Move this file into the root of your `Mastery/` vault so you can always reference it.

---

## 2. Folder Structure — What Each Folder Means

### 00 Inbox — The Capture Net

**What goes here:** Everything. Any thought, quote, idea, or note that hasn't been processed yet. This is the "dump it now, sort it later" zone.

**Examples:**
- A quote you heard in a podcast
- A half-formed idea during a meeting
- A concept you want to explore later
- A link to an article you want to read
- A random connection that popped into your head

**Rules:**
- Speed over quality. Don't organize, don't format, don't think — just capture.
- Process this folder regularly (see Section 11). Don't let it grow past ~20 notes.
- Every note here is TEMPORARY. It either gets promoted to another folder or deleted.

**Mindset:** The Inbox is a conveyor belt, not a storage room.

---

### 01 Zettelkasten — Your Permanent Knowledge Base

**What goes here:** Atomic, permanent, linked notes. Each note contains ONE idea, explained in YOUR words, connected to other notes via `[[links]]`.

**The rules of a Zettelkasten note:**
1. **One idea per note** — if you're writing about two ideas, make two notes
2. **In your own words** — never copy-paste. Rephrase = understanding
3. **Self-contained** — someone (or future you) should understand it without context
4. **Linked** — every note must link to at least 1 other note
5. **Titled clearly** — the title IS the idea: `First Principles Thinking`, not `Note #47`

**This folder is the core of the system.** Over months, it becomes a dense web of interconnected ideas — your external brain.

---

### 02 Synthesis — Where Original Thinking Lives

**What goes here:** Notes that CONNECT ideas from different domains. This is where cross-pollination happens (Section 17.4 & 22.6 of The Complete Mastery System).

**These are your most valuable notes.** They represent original thinking — ideas that didn't exist before you connected them.

**Examples:**
- "How entropy (physics) explains why teams lose alignment without active effort"
- "The connection between compound interest (finance) and spaced repetition (learning)"
- "How natural selection applies to startup ecosystems"

**Rules:**
- Must reference at least 2 notes from DIFFERENT domains in `01 Zettelkasten/`
- Write why the connection matters, not just that it exists
- One synthesis per week minimum (from your weekly routine)

---

### 03 Book Notes — Your Reading Archive

**What goes here:** One file per book. Contains your summary, key ideas, favorite quotes, and what you'll apply.

**When to create:** After finishing a book (or a major section). Use the Read-to-Teach method (Section 9C of the Mastery System) — close the book first, write what you remember, then check.

**Rules:**
- One file per book, named: `Book - [Title] - [Author].md`
- Extract key ideas INTO `01 Zettelkasten/` as individual atomic notes (and link back)
- The book note is the overview; the Zettelkasten notes are the reusable atoms

---

### 04 Essays & Writing — Your Thinking Output

**What goes here:** Weekly essays, drafts, LinkedIn posts, any long-form writing.

**Rules:**
- Date-prefix your files: `2026-03-15 - Why Meetings Fail.md`
- Don't edit in here during the first draft — write freely, edit later
- Published pieces get a `#published` tag

---

### 05 Decision Journal — Your Judgment Tracker

**What goes here:** Major decisions logged using the framework from Section 19.4 of the Mastery System.

**Rules:**
- One file per decision
- Include a review date
- Come back on the review date and evaluate the PROCESS, not just the outcome

---

### 06 Daily Notes — Your Stoic Journal

**What goes here:** Daily reflections, morning intentions, evening reviews, wins, observations.

**Rules:**
- One file per day, auto-created by the Daily Notes plugin (or manually: `2026-03-15.md`)
- Keep it short — 5–10 lines max
- Use the Daily Note template (Section 8)

---

### Templates — Your Note Blueprints

**What goes here:** Template files used to quickly create consistent notes. See Section 8 for full template library.

---

## 3. How Notes Flow Between Folders

```
                        ┌──────────────────────┐
                        │      00 INBOX        │
                        │  (capture everything) │
                        └──────────┬───────────┘
                                   │
                          Process (daily/weekly)
                                   │
                    ┌──────────────┼──────────────┐
                    ▼              ▼              ▼
          ┌─────────────┐  ┌────────────┐  ┌──────────┐
          │01 Zettelkasten│ │03 Book Notes│ │ 🗑 Delete │
          │ (atomic idea) │ │ (if it's a  │ │(not worth │
          │               │ │  book note) │ │  keeping) │
          └───────┬───────┘ └─────┬──────┘ └──────────┘
                  │               │
                  │    Extract key ideas
                  │◄──────────────┘
                  │
           Connect & link
                  │
                  ▼
          ┌─────────────┐
          │ 02 Synthesis │
          │(cross-domain │
          │ connections)  │
          └──────────────┘
```

### When to Move Notes — The Decision Tree

Ask these questions about every Inbox note:

```
Is this a fleeting thought with no lasting value?
  → YES → Delete it. Don't hoard.
  → NO ↓

Is this a single, clear idea I can explain?
  → YES → Rewrite in your own words → Move to 01 Zettelkasten/
  → NO ↓

Is this a book summary or reading notes?
  → YES → Move to 03 Book Notes/ → Extract atomic ideas to 01 Zettelkasten/
  → NO ↓

Is this a connection between two different domains?
  → YES → Move to 02 Synthesis/
  → NO ↓

Is this a draft or essay?
  → YES → Move to 04 Essays & Writing/
  → NO ↓

Is this a decision I need to track?
  → YES → Move to 05 Decision Journal/
  → NO → It probably belongs in 01 Zettelkasten/. Rewrite it as an atomic note.
```

### The Golden Rule of Moving Notes

**Never move a note out of Inbox without rewriting it.** A copy-paste is not processing. Rewriting in your own words is what turns information into understanding. This IS the Feynman Technique applied to your note system.

---

## 4. Sample Notes in Each Folder

### 00 Inbox — Raw Captures

**File:** `00 Inbox/podcast idea about incentives.md`
```markdown
From Naval podcast - "Show me the incentive and I'll show you the outcome"
Charlie Munger quote - means people do what they're rewarded for, not what they're told
Think about this re: why code reviews at work are done carelessly — nobody's incentivized to do them well
```

**File:** `00 Inbox/meeting observation.md`
```markdown
Noticed today: when Rahul asked "what do you think?" instead of presenting his solution, 
the team generated 3 better ideas. Leadership = asking, not telling. 
Connect to GROW model?
```

**File:** `00 Inbox/random book quote.md`
```markdown
"The test of a first-rate intelligence is the ability to hold two opposing ideas 
in mind at the same time and still retain the ability to function." — F. Scott Fitzgerald
Relates to steelmanning? And dialectical thinking?
```

---

### 01 Zettelkasten — Atomic, Linked Notes

**File:** `01 Zettelkasten/Incentives - Show Me the Incentive.md`
```markdown
# Incentives — Show Me the Incentive and I'll Show You the Outcome

Charlie Munger's most powerful mental model: **never think about what people SHOULD 
do — think about what they're INCENTIVIZED to do.**

People respond to incentives, not instructions. If you want to predict behavior, 
look at the reward structure. If you want to change behavior, change the incentives.

## Examples
- Code reviews are sloppy → because engineers are measured on features shipped, 
  not review quality. Fix: make review quality part of performance evaluation.
- Sales teams oversell → because commission is based on closed deals, not customer 
  retention. Fix: tie part of commission to 6-month retention.
- Students cram → because exams reward short-term memorization, not understanding. 
  Fix: use [[Retrieval Practice]] and frequent low-stakes testing.

## The Danger
When incentives are misaligned, good people do bad things — not because they're 
bad, but because the system rewards it. Always ask: "What behavior is this 
incentive structure actually encouraging?"

---
**Related:** [[Second-Order Thinking]] | [[First Principles Thinking]] | [[Cobra Effect]]
**Source:** Poor Charlie's Almanack, Naval Ravikant
**Tags:** #mental-model #decision-making #systems
```

**File:** `01 Zettelkasten/Retrieval Practice.md`
```markdown
# Retrieval Practice

The act of PULLING information out of your brain strengthens the memory far more 
than putting information IN (re-reading, highlighting).

## Why It Works
Every retrieval attempt strengthens the neural pathway. Failed retrieval attempts 
are especially powerful — the struggle signals to your brain "this matters, store 
it better." This is why testing yourself is learning, not just assessment.

## How to Apply
1. Close the book. Write what you remember. Check. (Retention Ritual)
2. Use [[Anki]] for spaced retrieval of key concepts
3. Explain what you learned out loud — the 60-Second Teach drill
4. The [[Feynman Technique]] is retrieval practice disguised as teaching

## The Paradox
It FEELS harder than re-reading. Your brain prefers the fluency illusion of 
re-reading ("this looks familiar, I must know it"). But the difficulty IS the 
learning. This is [[Desirable Difficulty]].

---
**Related:** [[Spaced Repetition]] | [[Feynman Technique]] | [[Forgetting Curve]] | [[Desirable Difficulty]]
**Source:** Make It Stick (Brown, Roediger, McDaniel)
**Tags:** #learning-science #core-concept
```

**File:** `01 Zettelkasten/Dichotomy of Control.md`
```markdown
# Dichotomy of Control (Epictetus)

The foundational Stoic principle: separate everything into what you CAN control 
and what you CANNOT. Invest 100% of energy in column A. Release column B completely.

## What You Control
- Your preparation, effort, response, words
- How early you arrive, how much you practice
- Your attitude toward the outcome

## What You Don't Control
- Other people's opinions, reactions, decisions
- Whether you get the promotion, the deal, the applause
- External events, weather, timing, luck

## The Paradox
By focusing ONLY on what you control, outcomes you can't control tend to improve. 
The person who stops obsessing about the audience's reaction and focuses entirely 
on preparation delivers a better talk — and gets a better reaction.

## Daily Practice
Before any stressful event, draw two columns. Write everything in the right 
column. Put energy only into the left. This takes 2 minutes and eliminates 
80% of anxiety.

---
**Related:** [[Premeditatio Malorum]] | [[Amor Fati]] | [[Stoic Evening Reflection]]
**Source:** Epictetus — Discourses; Marcus Aurelius — Meditations
**Tags:** #stoicism #mental-model #resilience
```

---

### 02 Synthesis — Cross-Domain Connections

**File:** `02 Synthesis/Compounding Applies to Everything.md`
```markdown
# Compounding Applies to Everything — Not Just Money

## The Connection
[[Compound Interest]] in finance: small returns, reinvested consistently, produce 
extraordinary results over time. But this principle isn't limited to money.

## Cross-Domain Applications

| Domain | How Compounding Works |
|---|---|
| **Finance** | ₹10K/month at 12% → ₹1 crore in 20 years |
| **Learning** | [[Spaced Repetition]] + daily reading → expertise in 2 years |
| **Reputation** | Weekly LinkedIn posts → "known for" status in 6 months |
| **Relationships** | Small consistent gestures → deep trust over years |
| **Health** | 30 min daily exercise → dramatically different body in 1 year |
| **Writing** | 500 words/week → 26,000 words/year → a book |

## The Key Insight
In ALL domains, compounding has the same shape: boring and invisible early, 
then explosive later. The most dangerous moment is the "boring phase" — months 
1-6 where results seem negligible. Most people quit here. The ones who don't 
get the exponential payoff.

## Why This Matters for the Mastery System
The 80 min/day practice schedule IS a compounding investment. Day 30 looks 
almost the same as Day 1. Day 365 is unrecognizable. The system works because 
of compounding — but only if you don't break the chain.

---
**Connects:** [[Compound Interest]] (finance) + [[Spaced Repetition]] (learning science) + [[Habit Loop]] (behavior design)
**Tags:** #synthesis #cross-domain #compounding
```

**File:** `02 Synthesis/Natural Selection in Startups.md`
```markdown
# Natural Selection Explains Why Most Startups Die

## The Connection
[[Natural Selection]] in biology: organisms with traits suited to their environment 
survive and reproduce. Those without die. No judgment, no fairness — just fit.

Startups work the same way. The "environment" is the market. The "traits" are 
product-market fit, team quality, and timing. Most startups have poor fit with 
their environment — so they die. Not because the founders are bad, but because 
evolution is brutal and indifferent.

## The Parallels

| Biology | Startups |
|---|---|
| Random mutations | Pivots and experiments |
| Environmental pressure | Market competition |
| Survival of the fittest | Product-market fit |
| Extinction | Running out of funding |
| Adaptation | Iterating on customer feedback |
| Speciation (new species branch off) | New market categories emerge |

## The Insight
Understanding this removes the emotional charge from startup failure. It's not 
personal — it's selection pressure. The useful response isn't "I failed" but 
"what trait was missing, and how do I mutate?" This is [[Amor Fati]] applied 
to entrepreneurship.

---
**Connects:** [[Natural Selection]] (biology) + [[First Principles Thinking]] (reasoning) + [[Amor Fati]] (stoicism)
**Tags:** #synthesis #cross-domain #evolution #startups
```

---

### 03 Book Notes — Reading Archive

**File:** `03 Book Notes/Book - Make It Stick - Brown Roediger McDaniel.md`
```markdown
# Make It Stick — Brown, Roediger, McDaniel

**Read:** March 2026
**Rating:** 10/10 — foundational. Read this before anything else.
**One-sentence summary:** Most popular study methods (re-reading, highlighting) 
are nearly useless; the techniques that actually work (retrieval, spacing, 
interleaving) feel harder but produce dramatically better results.

## Key Ideas

### 1. Retrieval Practice Is King
Testing yourself is not assessment — it IS learning. Every time you pull 
information out of memory, you strengthen the pathway. → [[Retrieval Practice]]

### 2. The Fluency Illusion
Re-reading feels effective because the material looks "familiar." But 
recognition ≠ recall. You can recognize something without being able to 
retrieve it. This illusion causes most people to think they know things 
they actually can't use. → [[Fluency Illusion]]

### 3. Spaced Repetition Beats Massed Practice
Studying the same thing over multiple sessions, with gaps, beats cramming. 
The gaps allow partial forgetting — and the re-learning effort strengthens 
memory. → [[Spaced Repetition]] → [[Forgetting Curve]]

### 4. Desirable Difficulty
Learning should feel hard. If it feels easy, you're probably not learning 
much. The effort of retrieval, the struggle of spacing, the confusion of 
interleaving — these difficulties are DESIRABLE because they force deeper 
processing. → [[Desirable Difficulty]]

### 5. Interleaving
Mixing up different topics/skills in a single study session beats blocking 
(doing all of one thing, then all of another). It feels worse but works 
better. → [[Interleaving]]

## Favorite Quotes
- "Learning is deeper and more durable when it's effortful."
- "The illusion of mastery is the greatest barrier to learning."

## What I'll Apply
- Close the book and recall BEFORE checking (Retention Ritual)
- Use Anki daily (spaced repetition)
- Mix practice types in evening sessions (interleaving)
- Stop re-reading. Start self-testing.

---
**Atomic notes extracted:** [[Retrieval Practice]], [[Spaced Repetition]], 
[[Forgetting Curve]], [[Desirable Difficulty]], [[Fluency Illusion]], [[Interleaving]]
**Tags:** #book-notes #learning-science #foundational
```

---

### 04 Essays & Writing

**File:** `04 Essays & Writing/2026-03-15 - Why Meetings Fail.md`
```markdown
# Why Meetings Fail

**Draft:** 2026-03-15
**Status:** First draft
**Word count:** ~500

---

Most meetings are a waste of time. Not because meetings are inherently bad, 
but because the organizer hasn't done their thinking yet.

A meeting should be the RESULT of clear thinking, not a SUBSTITUTE for it. 
When someone calls a meeting without knowing exactly what decision needs to 
be made or what outcome they want, they're outsourcing their thinking to a 
room full of people — most of whom also haven't thought about it.

[... continue writing ...]

---
**Connected ideas:** [[First Principles Thinking]], [[Minto Pyramid]], [[Deep Work]]
**Tags:** #essay #draft #communication
```

---

### 05 Decision Journal

**File:** `05 Decision Journal/2026-03-15 - Accept Senior Role at Startup.md`
```markdown
# Decision: Accept Senior Role at Startup X

**Date:** 2026-03-15
**Decision type:** Career — high stakes, partially reversible
**Deadline to decide:** 2026-03-22

## Options Considered
1. Accept the offer at Startup X
2. Stay at current company and push for promotion
3. Counter-offer: accept but negotiate remote + higher equity
4. Decline and continue searching

## What I Chose and Why
Option 3. The role aligns with my growth goals and the tech stack is 
modern. But the base salary is 15% below market and the remote policy 
was verbal only. I'll negotiate both in writing before accepting.

## Pre-Mortem (What Could Go Wrong)
1. Startup runs out of money in 12 months (checked: 18-month runway)
2. "Senior" title but no team to lead (verified: team of 4)
3. Remote policy disappears after 3 months (getting it in writing)
4. Culture is toxic (talked to 2 current employees — seems good)
5. Tech debt makes the role maintenance, not building (did technical 
   due diligence — acceptable)

## What I Expect to Happen
70% chance this accelerates my career significantly. 20% chance it's 
neutral. 10% chance I regret it and need to leave within a year.

## Confidence: 75%

## Review Date: 2026-09-15

---
**Framework used:** [[Decision-Making Framework]], [[Pre-Mortem]]
**Tags:** #decision #career
```

---

### 06 Daily Notes

**File:** `06 Daily Notes/2026-03-15.md`
```markdown
# Saturday, March 15, 2026

## Morning Intention
Focus on deep reading today. Finish Chapter 4 of Make It Stick.

## What I Practiced
- ☑ Meditation (10 min)
- ☑ Vocal warm-up (5 min)
- ☑ Shadowing — Barack Obama commencement speech (10 min)
- ☑ Reading — Make It Stick, Ch 4: Embrace Difficulties (15 min)
- ☑ Anki review — 23 cards, 87% correct
- ☑ 60-Second Teach: explained Desirable Difficulty
- ☐ Hot Seat drill (skipped — will do tomorrow)

## Key Insight Today
The idea that learning SHOULD feel hard is counterintuitive but explains 
why my previous "study by re-reading" never worked. → Created note: 
[[Desirable Difficulty]]

## Stoic Evening Reflection
- **What went well:** Deep reading session was focused. 45 min without 
  checking phone. The concept of desirable difficulty clicked.
- **Where I failed:** Skipped Hot Seat drill because I was tired. 
  Should have done minimum 2 questions.
- **Tomorrow:** Do Hot Seat first, before energy dips.

## Wins
- Used PREP framework in a WhatsApp discussion about AI. First time 
  using it outside of practice. It worked — people actually engaged.
```

---

## 5. How to Write a Good Zettelkasten Note

### The Anatomy of a Perfect Note

```markdown
# [Clear Title That IS the Idea]

[2-4 sentences explaining the concept in YOUR OWN words. No copy-paste. 
If you can't explain it without looking at the source, you don't 
understand it yet — go back and study.]

## Why It Matters
[1-2 sentences on why this concept is useful or important]

## Examples
- [Real-world example 1]
- [Real-world example 2]
- [Personal application]

## Key Insight
[The non-obvious takeaway — the "surprise" you discovered while writing]

---
**Related:** [[Link 1]] | [[Link 2]] | [[Link 3]]
**Source:** [Where you learned this]
**Tags:** #tag1 #tag2
```

### The Quality Checklist

Before moving a note to `01 Zettelkasten/`, verify:

- [ ] Title is the idea itself (not "Note about X" — just "X")
- [ ] Contains ONE idea (if there are two, split into two notes)
- [ ] Written in MY words (not copy-pasted from a book)
- [ ] I can understand this note 6 months from now without context
- [ ] Links to at least 1 other note via `[[double brackets]]`
- [ ] Has at least 1 concrete example
- [ ] Tagged with relevant tags

---

## 6. Linking — The Heart of Zettelkasten

### How to Link

Type `[[` and start typing the note title. Obsidian will autocomplete.

```markdown
This connects to [[First Principles Thinking]] because both 
require questioning assumptions rather than accepting them.
```

### Types of Links

| Link Type | Example | When to Use |
|---|---|---|
| **"Relates to"** | `[[Retrieval Practice]]` | Two concepts are connected |
| **"Is an example of"** | `This is an example of [[Incentives]]` | Concrete instance of abstract idea |
| **"Contradicts"** | `This contradicts [[Sunk Cost Fallacy]]` | Ideas in tension |
| **"Builds on"** | `Extends the idea in [[Second-Order Thinking]]` | One idea deepens another |
| **"Opposite of"** | `The opposite approach is [[Reasoning by Analogy]]` | Contrasting concepts |

### The Backlinks Panel

Click any note → open the **Backlinks** panel (right sidebar). This shows you EVERY other note that links TO this note. This is how you discover unexpected connections — notes you wrote months ago suddenly connect to what you're learning now.

### The Graph View

Press `Ctrl+G` to open Graph View. This shows your entire knowledge network as a visual web. Clusters of densely-linked notes = areas where your understanding is deep. Isolated notes with few links = areas to develop.

---

## 7. Tags Strategy

Keep tags simple. Don't over-tag. Use these categories:

### Domain Tags (What field is this from?)
```
#mental-model  #learning-science  #stoicism  #economics  
#psychology  #communication  #biology  #physics  
#history  #philosophy  #decision-making  #leadership
```

### Type Tags (What kind of note is this?)
```
#core-concept    — Foundational idea you'll reference often
#technique       — A specific method or framework
#synthesis       — Cross-domain connection
#book-notes      — Book summary
#essay           — Your writing
#decision        — Decision journal entry
#quote           — A quote worth keeping
```

### Status Tags (For essays/writing only)
```
#draft  #in-progress  #published
```

**Rule:** A note should have 1 domain tag + 1 type tag. Maximum 3-4 tags total. If you're adding more than 4 tags, you're over-categorizing — let links do the work instead.

---

## 8. Templates Setup & Usage

### How to Set Up Templates

1. Create the `Templates/` folder in your vault (already done in folder structure)
2. Go to **Settings → Core Plugins → Templates** → Enable it
3. Set "Template folder location" → `Templates`
4. Set a hotkey: **Settings → Hotkeys → search "Insert template"** → assign `Alt+T`
5. Now when you press `Alt+T` in any note, you can pick a template to insert

### Template Files

Create these files inside your `Templates/` folder (see Section 8 below for the actual template content to copy):

```
Templates/
├── Zettelkasten Note.md
├── Book Note.md  
├── Synthesis Note.md
├── Decision Journal Entry.md
├── Daily Note.md
├── Essay Draft.md
├── Weekly Review.md
└── Meeting Note.md
```

---

## 9. Essential Plugins (Add After Week 4)

> **IMPORTANT:** Do NOT install plugins on Day 1. Use Obsidian with zero plugins for 4 weeks. Learn the basics first. Plugins added too early create complexity and distraction.

### Tier 1 — Install at Week 4 (High Value, Low Complexity)

#### 1. Calendar
- **What:** Adds a calendar widget. Click any date → opens that day's Daily Note.
- **Why:** Makes Daily Notes effortless. Visual streak tracking.
- **Setup:** Install → Settings → set "Daily note folder" to `06 Daily Notes/` → set template to `Templates/Daily Note.md`

#### 2. Templater
- **What:** Advanced template engine. Lets templates auto-fill dates, create files in specific folders, and more.
- **Why:** Faster note creation with auto-population of dates and metadata.
- **Setup:** Install → Settings → set template folder to `Templates/` → enable "Trigger Templater on new file creation"
- **Key feature:** `<% tp.date.now("YYYY-MM-DD") %>` auto-inserts today's date

#### 3. Dataview
- **What:** Query your notes like a database using simple syntax.
- **Why:** Create dynamic lists like "all unprocessed Inbox notes," "all decisions due for review," "all books read this year."
- **Setup:** Install → use in any note with a dataview code block
- **Example queries:**
  ```dataview
  // Show all Inbox notes older than 7 days (need processing!)
  TABLE file.cday as "Created"
  FROM "00 Inbox"
  WHERE file.cday < date(today) - dur(7 days)
  SORT file.cday ASC
  ```
  ```dataview
  // Show all decisions due for review
  TABLE review-date as "Review Date"
  FROM "05 Decision Journal"
  WHERE review-date <= date(today)
  ```
  ```dataview
  // Count notes per folder
  TABLE length(rows) as "Count"
  FROM ""
  GROUP BY file.folder
  ```

#### 4. Obsidian Git (if you use Git)
- **What:** Auto-commit and push your vault to a Git repo.
- **Why:** Version history + remote backup. Never lose a note.
- **Setup:** Install → set auto-backup interval (e.g., every 30 min) → connect to a private GitHub/GitLab repo

### Tier 2 — Install at Month 3+ (When You Feel the Need)

#### 5. Excalidraw
- **What:** Draw diagrams, mind maps, and visual notes inside Obsidian.
- **Why:** Some ideas are better as pictures. Mental model diagrams, concept maps, flow charts.

#### 6. Kanban
- **What:** Create Kanban boards (like Trello) inside Obsidian.
- **Why:** Useful for tracking essay drafts, project stages, or weekly goals.

#### 7. Natural Language Dates
- **What:** Type "next Friday" and it converts to `2026-03-20`.
- **Why:** Faster date entry in Decision Journal and Daily Notes.

#### 8. Periodic Notes
- **What:** Extends Daily Notes with weekly, monthly, and quarterly notes.
- **Why:** Perfect for Weekly Reviews (Section 38 of Mastery System) and Monthly Reviews.

#### 9. Strange New Worlds
- **What:** Shows a count badge on each `[[link]]` indicating how many other notes link to it.
- **Why:** Instantly see which concepts are central hubs in your knowledge network.

#### 10. Tag Wrangler
- **What:** Right-click tags to rename, merge, or search them.
- **Why:** When your tag system gets messy (it will), this cleans it up.

### Plugins to AVOID

| Plugin | Why to Skip |
|---|---|
| Sliding panes | Cool but distracting. Focus on writing, not UI. |
| Obsidian Publish | Premature. You don't need to publish your vault. |
| Any "daily dashboard" plugin | Over-engineered. A simple Daily Note template is enough. |
| More than 10 plugins total | Obsidian becomes slow and confusing. Less is more. |

---

## 10. Daily Workflow

### Morning (2 minutes in Obsidian)

1. Open today's Daily Note (click today on Calendar, or `Ctrl+N` → use template)
2. Write your morning intention (1 sentence)
3. Done. Close Obsidian. Go practice.

### During the Day (capture as needed)

1. Idea hits? Open Obsidian → create note in `00 Inbox/` → dump the thought → close
2. Don't organize. Don't format. Speed is everything. You'll process later.
3. On mobile? Use the Obsidian mobile app or just text yourself — move it to Inbox later.

### Evening (5-10 minutes in Obsidian)

1. Open today's Daily Note → fill in what you practiced, key insight, Stoic reflection
2. Create any new Zettelkasten notes from today's learning (use template, `Alt+T`)
3. Add new Anki cards for key concepts
4. Glance at `00 Inbox/` — if anything is easy to process, do it now

---

## 11. Weekly Maintenance Routine

**Every Sunday, spend 15–20 minutes on vault maintenance:**

### Process the Inbox (10 min)
1. Open `00 Inbox/`
2. For each note, ask: "Is this worth keeping permanently?"
   - **Yes, it's a clear idea** → Rewrite as atomic note → Move to `01 Zettelkasten/`
   - **Yes, it's a cross-domain connection** → Expand → Move to `02 Synthesis/`
   - **Yes, but it's not ready** → Add more context, leave in Inbox for next week
   - **No** → Delete it. Be ruthless. A cluttered Inbox kills the system.

### Link New Notes (5 min)
- Open each new Zettelkasten note from this week
- Add 2–3 links to existing notes: `[[related concept]]`
- Check backlinks — any surprising connections?

### Review Graph View (2 min)
- Press `Ctrl+G`
- Look for orphan notes (no links). Can you connect them?
- Look for clusters. Are knowledge hubs forming?

### Write One Synthesis Note (5 min)
- Pick 2 concepts from different domains
- Force a connection
- Write it up in `02 Synthesis/`
- This is your weekly cross-pollination exercise

---

## 12. Keyboard Shortcuts Worth Learning

| Shortcut | Action |
|---|---|
| `Ctrl+N` | New note |
| `Ctrl+O` | Quick open (search any note by name) |
| `Ctrl+P` | Command palette (search any action) |
| `Ctrl+E` | Toggle edit/preview mode |
| `Ctrl+G` | Graph view |
| `Ctrl+Shift+F` | Search across entire vault |
| `Ctrl+Click` on a `[[link]]` | Open that note |
| `Ctrl+K` | Insert a hyperlink |
| `Alt+T` | Insert template (after setting hotkey) |
| `[[` | Start typing to link to an existing note |
| `Ctrl+,` | Open settings |

---

## 13. Common Mistakes to Avoid

### Mistake 1: Treating Obsidian as a Filing Cabinet
**Wrong:** Organizing notes into 20 nested subfolders by topic.
**Right:** Flat structure with links. Let `[[links]]` and search do the organizing. The 8 folders above are all you need — ever.

### Mistake 2: Writing Long Notes
**Wrong:** A 2,000-word note covering 5 concepts.
**Right:** Five 200-word notes, each atomic, each linked. Shorter notes get linked more often and are more reusable.

### Mistake 3: Copy-Pasting from Books
**Wrong:** Copying entire passages into your vault.
**Right:** Close the book. Write what you remember in your own words. Then check. This IS retrieval practice — your note system reinforces your learning system.

### Mistake 4: Spending More Time Organizing Than Writing
**Wrong:** 30 minutes perfecting tags, templates, and CSS themes.
**Right:** 5 minutes writing a note, 1 minute linking it. Content > cosmetics. Always.

### Mistake 5: Never Processing the Inbox
**Wrong:** 200 notes sitting in Inbox for months.
**Right:** Process weekly. Delete aggressively. If a note has sat in Inbox for 3 weeks and you haven't processed it, it's probably not important. Delete it.

### Mistake 6: Installing Too Many Plugins
**Wrong:** 15 plugins installed on Day 1. Half of them conflict.
**Right:** Zero plugins for 4 weeks. Then add 1 at a time, only when you feel a genuine need. If you can't articulate WHY you need a plugin, you don't need it.

### Mistake 7: Waiting Until You "Have Enough Notes" to Start Linking
**Wrong:** "I'll start linking once I have 50 notes."
**Right:** Link from Note #2 onward. The network grows incrementally. Start immediately.

### Mistake 8: Perfectionism
**Wrong:** Refusing to create a note because you "don't understand the concept well enough yet."
**Right:** Write what you know NOW. A rough note that exists is infinitely more valuable than a perfect note you never wrote. You can always improve it later — that's what editing is for.

---

## 14. Settings to Change on Day 1

Go to **Settings** (gear icon or `Ctrl+,`) and change:

| Setting | Location | Change To |
|---|---|---|
| Default location for new notes | Files & Links | `00 Inbox` |
| New link format | Files & Links | Shortest path when possible |
| Use Wikilinks | Files & Links | ON (enabled) |
| Spell check | Editor | ON |
| Readable line length | Editor | ON (prevents lines from stretching across your full screen) |
| Auto pair brackets | Editor | ON |
| Default view for new tabs | Editor | Editing view |
| Confirm deletion | Files & Links | ON (safety net) |

### Core Plugins to Enable (Built-In, Not Community)

| Plugin | Why |
|---|---|
| **Backlinks** | Shows what links TO a note. Essential. |
| **Graph view** | Visual network of your knowledge. |
| **Search** | Full-text search across vault. |
| **Templates** | Insert note templates. Set folder to `Templates/`. |
| **Quick switcher** | `Ctrl+O` to jump to any note. |
| **Outline** | Shows heading structure of current note in sidebar. |
| **Tags** | Tag search panel. |
| **Daily notes** | Enable for daily journaling. Set folder to `06 Daily Notes/`. |

### Core Plugins to Disable (Reduce Noise)

| Plugin | Why Off |
|---|---|
| Slides | You won't use it |
| Publish | Unnecessary for personal vault |
| Audio recorder | Phone is better for this |
| Workspaces | Adds complexity you don't need yet |

---

## Quick Start Checklist

```
☐ Downloaded Obsidian (desktop + mobile)
☐ Created vault "Mastery" in cloud-synced folder
☐ Created all 8 folders (00 Inbox through Templates)
☐ Changed Day 1 settings (Section 14)
☐ Enabled core plugins, disabled unnecessary ones
☐ Created template files in Templates/ folder
☐ Copied this guide into the vault root
☐ Created first note in 00 Inbox/ (anything — break the ice)
☐ Processed that note into 01 Zettelkasten/ (practice the flow)
☐ Linked it to at least one other note
☐ YOU'RE DONE. Start your Mastery System daily routine.
```

---

> **Remember:** Obsidian is a TOOL for thinking, not a replacement for it. The value is in the NOTES you write and the CONNECTIONS you make — not in the app, plugins, or templates. Keep it simple. Write daily. Link aggressively. Process weekly. That's the whole system.
