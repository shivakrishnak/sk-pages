# Anki Setup & Mastery Guide

> **Purpose:** This file is your permanent reference for using Anki as part of the Mastery System. Consult it whenever you need to create cards, adjust settings, or troubleshoot your review habit.

---

## Table of Contents

1. [What Is Anki and Why It Matters](#1-what-is-anki-and-why-it-matters)
2. [Day 1 Setup — Step by Step](#2-day-1-setup--step-by-step)
3. [Anki vs. Zettelkasten — What Goes Where](#3-anki-vs-zettelkasten--what-goes-where)
4. [How to Create Great Cards — The Rules](#4-how-to-create-great-cards--the-rules)
5. [Card Types and Templates](#5-card-types-and-templates)
6. [Sample Cards for Every Purpose](#6-sample-cards-for-every-purpose)
7. [How to Navigate Anki — The Interface](#7-how-to-navigate-anki--the-interface)
8. [Spaced Repetition Settings — What to Change](#8-spaced-repetition-settings--what-to-change)
9. [The Daily Review Workflow](#9-the-daily-review-workflow)
10. [When to Discard, Edit, or Make Cards Permanent](#10-when-to-discard-edit-or-make-cards-permanent)
11. [Common Mistakes to Avoid](#11-common-mistakes-to-avoid)
12. [Advanced Techniques (Month 2+)](#12-advanced-techniques-month-2)
13. [Anki + Mastery System Integration](#13-anki--mastery-system-integration)
14. [Quick Reference Card](#14-quick-reference-card)

---

## 1. What Is Anki and Why It Matters

### The Problem Anki Solves

You read a brilliant book. You highlight 30 ideas. Three weeks later, you remember... maybe 2. This is the **Forgetting Curve** (Ebbinghaus, 1885) — without reinforcement, you lose ~70% of new information within 48 hours and ~90% within a month.

### The Solution: Spaced Repetition

Anki is a flashcard app that uses a **spaced repetition algorithm** to show you cards at the EXACT moment you're about to forget them.

```
Day 1:    Learn "First Principles Thinking"
Day 2:    Review it (you almost forgot → strengthened)
Day 5:    Review again (interval grows)
Day 14:   Review again
Day 45:   Review again
Day 120:  Review again
...eventually: once every 6–12 months
```

Each successful review DOUBLES the interval. Each failure resets it. Over time, you maintain hundreds of concepts with just 5–10 minutes of daily review.

### Why This Matters for YOU

Your Mastery System asks you to learn 30+ mental models, hundreds of vocabulary words, dozens of frameworks, and concepts from 8+ disciplines. Without Anki, you'll forget most of them. With Anki, you'll retain ALL of them — permanently — with minimal daily effort.

**The math:** 5 min/day × 365 days = 30 hours/year to maintain your ENTIRE knowledge base. That's the best ROI in the system.

---

## 2. Day 1 Setup — Step by Step

### Step 1: Download and Install Anki

| Platform | Where to Get It | Cost |
|---|---|---|
| **Windows / Mac / Linux** | [apps.ankiweb.net](https://apps.ankiweb.net) | **Free** |
| **Android** | Google Play Store → "AnkiDroid" | **Free** |
| **iPhone / iPad** | App Store → "AnkiMobile Flashcards" | **₹2,000 (~$25)** — one-time, worth it |
| **Web** | [ankiweb.net](https://ankiweb.net) | **Free** (for reviewing on any browser) |

> **Note:** The iOS app is expensive but it funds the entire free ecosystem. If budget is tight, use AnkiWeb on Safari as a free alternative.

### Step 2: Create Your AnkiWeb Account (for sync)

1. Go to [ankiweb.net](https://ankiweb.net) → Sign up (free)
2. This account lets you sync cards between desktop and phone
3. You'll never lose your cards — they live in the cloud

### Step 3: Open Anki Desktop and Sync

1. Open Anki → **Tools → Preferences → Network** → sign in with your AnkiWeb account
2. Click **Sync** (the circular arrow at top right) — this connects desktop to cloud
3. Do this once. After this, just click Sync at the end of each session.

### Step 4: Create Your Deck Structure

A **deck** is a collection of cards. Think of it like a folder.

**Click "Create Deck" at the bottom of the main screen. Create these decks:**

```
Mental Models & Key Concepts     ← Your primary deck (frameworks, models, principles)
English Vocabulary               ← Words, phrases, idioms, pronunciation
Books & Reading                  ← Key ideas from books you read
Worldly Knowledge                ← Facts from economics, physics, history, etc.
```

> **Why 4 decks, not 1?** Separation lets you review specific areas when needed (e.g., cram vocabulary before a presentation). But during daily review, Anki mixes cards from ALL decks anyway — which is ideal (interleaving).

> **Why not 20 decks?** Over-categorization creates decision fatigue. 4 decks is enough for your entire Mastery System. If a card doesn't fit neatly, put it in "Mental Models & Key Concepts" — that's your catch-all.

### Step 5: Understand Card Types

Anki comes with 3 built-in note types:

| Note Type | What It Does | When to Use |
|---|---|---|
| **Basic** | Front → Back. One question, one answer. | 90% of your cards. Default for everything. |
| **Basic (and reversed card)** | Creates TWO cards: Front→Back AND Back→Front. | Vocabulary (see word → recall meaning AND see meaning → recall word) |
| **Cloze** | Fill-in-the-blank. "The {{c1::Forgetting Curve}} was discovered by {{c2::Ebbinghaus}}." | Definitions, formulas, multi-part facts |

### Step 6: Create Your First 5 Cards

Don't overthink this. Just create 5 cards to break the ice:

**Card 1 — Mental Model:**
- Front: `What is First Principles Thinking?`
- Back: `Breaking a problem down to its most fundamental truths (things you KNOW to be true) and reasoning up from there, instead of reasoning by analogy ("this is how it's always been done").`
- Deck: Mental Models & Key Concepts

**Card 2 — Mental Model:**
- Front: `What is the Forgetting Curve?`
- Back: `Ebbinghaus (1885): Without reinforcement, you lose ~70% of new information within 48 hours. Spaced repetition is the antidote — reviewing at increasing intervals prevents forgetting.`
- Deck: Mental Models & Key Concepts

**Card 3 — Vocabulary:**
- Front: `What does "cogent" mean?`
- Back: `Clear, logical, and convincing. Example: "She made a cogent argument for switching to PostgreSQL."`
- Deck: English Vocabulary

**Card 4 — Framework:**
- Front: `What is the PREP framework for structuring an opinion?`
- Back: `Point → Reason → Example → Point (restate). "I think X because Y. For example, Z. That's why X."`
- Deck: Mental Models & Key Concepts

**Card 5 — Cloze (Book Insight):**
- Type: Cloze
- Text: `The most effective learning technique is {{c1::retrieval practice}} — pulling information OUT of memory, not putting it in (re-reading). From: {{c2::Make It Stick}}.`
- Deck: Books & Reading

### Step 7: Do Your First Review

1. Click a deck → **Study Now**
2. Read the front. Think of the answer. Click **Show Answer**.
3. Rate yourself:
   - **Again** — I had no idea (card reappears in ~1 min)
   - **Hard** — I struggled but got part of it (short interval)
   - **Good** — I got it right with some effort (normal interval)
   - **Easy** — I knew it instantly (longer interval)
4. **Default choice: press "Good" most of the time.** Only use "Easy" if it was truly effortless. Only use "Again" if you completely blanked.

### Step 8: Sync

Click the **Sync** button (top right). Your cards are now in the cloud. Open your phone app → Sync → same cards appear. You can review anywhere.

### Day 1 Setup Checklist

```
☐ Downloaded Anki (desktop + phone)
☐ Created AnkiWeb account
☐ Signed in and synced
☐ Created 4 decks
☐ Created first 5 cards
☐ Did first review session
☐ Synced to phone
☐ YOU'RE DONE. Add cards daily as you learn.
```

---

## 3. Anki vs. Zettelkasten — What Goes Where

This is the most common confusion. Here's the clear rule:

### The Simple Rule

| Put in **Anki** | Put in **Zettelkasten** (Obsidian) |
|---|---|
| Things you need to **RECALL on demand** | Things you need to **UNDERSTAND deeply** |
| Short, atomic facts and definitions | Long explanations, examples, nuances |
| "What is X?" → 1-3 sentence answer | "Here's how X works, why it matters, how it connects to Y and Z" |
| The TRIGGER for memory | The DEPTH of understanding |

### Think of It This Way

**Anki = flash memory** (instant recall under pressure)
**Zettelkasten = hard drive** (deep storage with rich connections)

When someone asks you "What's the sunk cost fallacy?" in a meeting, Anki lets you answer in 5 seconds. When you need to WRITE about sunk cost fallacy, apply it to a complex situation, or connect it to other ideas — that's when you open your Zettelkasten note.

### The Workflow: Book → Zettelkasten → Anki

```
1. Read a book → encounter a key concept (e.g., "Retrieval Practice")

2. Write a Zettelkasten note in Obsidian:
   - Full explanation in your own words
   - Examples, connections, implications
   - Links to related notes
   - 200-400 words

3. Create an Anki card from that note:
   - Front: "What is Retrieval Practice?"
   - Back: Core definition + 1 example (2-3 sentences MAX)

4. LINK them: Add a reference in the Anki card's "Extra" field 
   pointing to the Obsidian note for deeper review
```

### What If I'm Not Sure?

| Scenario | Put it in... |
|---|---|
| A new English word I want to remember | Anki (English Vocabulary deck) |
| A mental model definition | Anki (Mental Models deck) + Zettelkasten (full note) |
| A cross-domain connection I discovered | Zettelkasten only (Synthesis folder) — too complex for a card |
| A framework (PREP, STAR, Pyramid) | Anki (the steps) + Zettelkasten (with examples and nuance) |
| A book summary | Zettelkasten only (Book Notes folder) |
| A specific quote I want to remember | Anki (quote on front, source + significance on back) |
| A cognitive bias definition | Anki (definition) + Zettelkasten (examples, connections) |
| A date/fact from history | Anki (if it's a fact worth recalling) |
| An essay I wrote | Zettelkasten only (Essays folder) |
| A decision I'm tracking | Zettelkasten only (Decision Journal) |

### The Golden Ratio

For every Zettelkasten note, create **1-3 Anki cards**. The Zettelkasten note is the master. The Anki cards are retrieval hooks that point back to it.

- **If a concept has 1 core idea** → 1 Anki card
- **If a concept has 3 components** (like the Pyramid Principle has Conclusion, Arguments, Evidence) → 3 cards, one per component
- **If a concept is complex** (like Thinking, Fast and Slow's System 1 vs System 2) → 2–3 cards covering the key distinctions

---

## 4. How to Create Great Cards — The Rules

### Rule 1: One Question, One Answer (Atomic Cards)

**Bad card:**
```
Front: What are Charlie Munger's mental models?
Back: First Principles, Inversion, Incentives, Second-Order Thinking, 
      Opportunity Cost, Occam's Razor, Hanlon's Razor, Map vs Territory,
      Circle of Competence, Probabilistic Thinking, Margin of Safety,
      Survivorship Bias...
```
This card is impossible to review. You'll fail it every time because you can't recall a list of 12+ items.

**Good cards (split into atomic pieces):**
```
Front: What is Inversion (mental model)?
Back: Instead of asking "How do I succeed?" ask "What would guarantee 
      failure?" Then avoid those things. Solve the problem backwards.

Front: What is Occam's Razor?
Back: Among competing explanations, the simplest one is usually correct. 
      Don't multiply assumptions unnecessarily.
```

### Rule 2: Use Your Own Words

Never copy-paste a definition from a book or Wikipedia. Rewrite it the way YOU would explain it to a friend. Your brain retrieves YOUR phrasing much better than someone else's.

**Book definition:** "Retrieval practice is the strategy of recalling learned information from memory, which has been shown to strengthen long-term retention."

**Your card:** "Pulling information OUT of your brain (by testing yourself), instead of putting it in (by re-reading). The struggle of recall IS the learning."

### Rule 3: Add Context and Examples

A bare definition without context is hard to remember and useless in practice.

**Bare card (weak):**
```
Front: What is opportunity cost?
Back: The cost of what you give up when making a choice.
```

**Contextual card (strong):**
```
Front: What is opportunity cost?
Back: Every choice has a hidden cost: the best alternative you gave up. 
      Choosing to scroll for 1 hour = losing 1 hour of reading/practice. 
      Choosing to buy a car = the returns that money would have earned 
      if invested. Always ask: "What am I NOT doing by choosing this?"
```

### Rule 4: Use Images When Possible

The brain remembers images far better than text (the picture superiority effect). For visual concepts, add a simple diagram or image.

- In the card editor, click the paperclip icon to attach an image
- Screenshot a diagram, draw one yourself, or find one online
- Especially useful for: frameworks (Eisenhower Matrix), charts, brain anatomy, physics diagrams

### Rule 5: Make Both Directions When It Matters

For vocabulary, create cards that test BOTH directions:

```
Card 1 (recognition): "What does 'cogent' mean?" → "Clear, logical, convincing"
Card 2 (production):  "What word means 'clear, logical, and convincing'?" → "Cogent"
```

Use the "Basic (and reversed card)" note type — it creates both automatically.

For mental models, you usually only need one direction (you won't be asked "What model says to break things down to first principles?" in real life — you'll be asked to APPLY first principles to a problem).

### Rule 6: Keep Answers Short

If it takes more than 10 seconds to read the answer, the card is too long. Target 1–3 sentences. If you need more depth, that's what your Zettelkasten note is for.

### Rule 7: Include the "So What?"

Don't just define — show WHY it matters. This makes the card useful, not just memorizable.

```
Front: What is the Dunning-Kruger Effect?
Back: People with LOW competence in an area OVERESTIMATE their ability 
      (they don't know enough to know what they don't know). People with 
      HIGH competence UNDERESTIMATE their ability. 
      → So what? When you feel most confident about a new skill, you're 
      probably in the danger zone. When you feel uncertain, you might 
      actually be getting good.
```

---

## 5. Card Types and Templates

### Type 1: The Basic Q&A (90% of your cards)

The workhorse. One question, one answer.

```
Front: [Clear, specific question]
Back:  [Concise answer in your own words + 1 example]
```

### Type 2: The Cloze Deletion (For facts with multiple parts)

Fill-in-the-blank. Great for definitions with specific terms, formulas, or multi-part facts.

```
Text: The {{c1::Forgetting Curve}} was discovered by {{c2::Ebbinghaus}} 
      in {{c3::1885}}, showing that without review, {{c4::~70%}} of 
      information is lost within 48 hours.
```

This creates 4 separate cards, each blanking one piece. You see the context, you recall the missing piece.

**How to create:** When adding a card, choose note type "Cloze." Wrap each blank in `{{c1::text}}`. Use `c1`, `c2`, `c3` for different blanks.

### Type 3: The Reversed Card (For vocabulary)

Creates two cards from one entry — tests you in both directions.

```
Front: cogent
Back:  (adj.) Clear, logical, and convincing. "A cogent argument."
```

Anki generates:
- Card A: "cogent" → what does it mean?
- Card B: "(adj.) Clear, logical, and convincing" → what's the word?

**How to create:** Choose note type "Basic (and reversed card)" when adding.

### Type 4: The Application Card (For frameworks)

Instead of "What is X?" ask "When would you use X?" This trains RETRIEVAL IN CONTEXT — which is how you'll actually use the knowledge.

```
Front: Your colleague rambles for 3 minutes giving you feedback 
       without a clear point. What framework would make this better?
Back:  SBI (Situation → Behavior → Impact).
       "In yesterday's client call (S), when you interrupted the client 
       mid-sentence (B), it made us look unprepared (I)."
```

### Type 5: The "Explain to Me" Card (For deep understanding)

```
Front: Explain the Dunning-Kruger Effect as if to a 10-year-old.
Back:  "Imagine you just learned 3 chess moves and think you're great. 
       But a real chess player knows 1,000 moves and STILL thinks they 
       have much to learn. When you know very little, you feel very 
       confident. When you know a lot, you realize how much you don't know."
```

---

## 6. Sample Cards for Every Purpose

### A. English Vocabulary Words

**Card 1 — Formal/Professional Word:**
```
Note Type: Basic (and reversed card)
Front: Pragmatic
Back:  (adj.) Dealing with things sensibly and practically, rather than 
       ideally. "We need a pragmatic solution, not a perfect one."
       Pronunciation: /præɡˈmæt.ɪk/
Tags: #vocabulary #professional
```

**Card 2 — Idiomatic Expression:**
```
Note Type: Basic
Front: What does "move the needle" mean?
Back:  To make a noticeable difference or impact. Used in business: 
       "Will this feature actually move the needle on user retention?"
       Similar: "make a dent," "shift the dial"
Tags: #vocabulary #idiom #business
```

**Card 3 — Commonly Confused Words:**
```
Note Type: Basic
Front: What's the difference between "affect" and "effect"?
Back:  Affect = VERB (to influence). "The rain affected the match."
       Effect = NOUN (a result). "The effect of rain was a cancellation."
       Memory trick: A for Action (Affect = verb), E for End result (Effect = noun)
Tags: #vocabulary #grammar
```

**Card 4 — Pronunciation Trap:**
```
Note Type: Basic
Front: How do you pronounce "hierarchy"? (Common Indian English mistake)
Back:  ✅ /ˈhaɪ.ə.rɑːr.ki/ — "HIGH-uh-rar-kee" (4 syllables)
       ❌ Not "hi-RAAR-chee" (3 syllables)
       Practice: "There's a clear hierarchy in the organization."
Tags: #vocabulary #pronunciation
```

**Card 5 — Power Phrase:**
```
Note Type: Basic
Front: What phrase can you use to respectfully disagree in a meeting?
Back:  "I see it differently. Here's why..."
       Also: "I understand that perspective. Another way to look at it is..."
       Also: "That's a valid point. I'd push back slightly because..."
Tags: #vocabulary #phrases #meetings
```

---

### B. Mental Models

**Card 1 — Core Definition:**
```
Note Type: Basic
Front: What is Second-Order Thinking?
Back:  First-order: "What happens if I do X?"
       Second-order: "And then what? What happens AFTER that?"
       Example: Rent control (1st: cheaper rent → 2nd: landlords stop 
       maintaining buildings → 3rd: housing quality drops → 4th: fewer 
       developers build rental units → 5th: housing shortage worsens)
Tags: #mental-model #decision-making
```

**Card 2 — Application:**
```
Note Type: Basic
Front: You're deciding whether to take a pay cut to join a startup. 
       Apply Second-Order Thinking.
Back:  1st order: Less money now
       2nd order: More equity + faster learning + bigger network
       3rd order: Skills and network compound → better opportunities in 3 years
       4th order: If startup fails, the experience still makes you more 
       valuable than 3 years of incremental growth at a safe company
       → Second-order analysis often reverses the obvious first-order conclusion
Tags: #mental-model #decision-making #application
```

**Card 3 — Paired Comparison:**
```
Note Type: Basic
Front: What's the difference between Occam's Razor and Hanlon's Razor?
Back:  Occam's: Among competing EXPLANATIONS, prefer the simplest.
       Hanlon's: Among competing MOTIVES, prefer stupidity/carelessness over malice.
       Occam's = about truth. Hanlon's = about people.
       Example: Colleague didn't invite you to a meeting. 
       Hanlon's: they forgot (most likely). Not: they're sabotaging you.
Tags: #mental-model #paired
```

---

### C. Abstract Concepts

**Card 1 — The Cloze for a Complex Idea:**
```
Note Type: Cloze
Text: The {{c1::Dunning-Kruger Effect}} describes a cognitive bias where 
      people with {{c2::low ability}} tend to {{c3::overestimate}} their 
      competence, while people with {{c4::high ability}} tend to 
      {{c5::underestimate}} theirs.
Tags: #psychology #cognitive-bias
```

**Card 2 — The Analogy Card:**
```
Note Type: Basic
Front: Explain "entropy" in a way that's useful outside of physics.
Back:  Everything naturally moves toward disorder unless energy is invested 
       to maintain order. 
       → Your desk gets messy unless you clean it.
       → Teams lose alignment unless leaders actively communicate.
       → Skills decay unless you practice.
       → Relationships weaken unless you invest attention.
       Entropy is the universal tax on inaction.
Tags: #physics #mental-model #cross-domain
```

**Card 3 — The Principle Behind a Concept:**
```
Note Type: Basic
Front: What is "desirable difficulty" and why does it matter for learning?
Back:  Learning strategies that FEEL harder (retrieval practice, spacing, 
       interleaving) work BETTER than strategies that feel easy (re-reading, 
       highlighting). The difficulty isn't a bug — it's the feature. 
       The struggle signals to your brain: "this matters, store it deeply."
       → So what? If studying feels comfortable, you're probably not learning much.
Tags: #learning-science #core-concept
```

---

### D. Definitions (Precise Terms)

**Card 1 — Technical Definition:**
```
Note Type: Basic
Front: What is "cognitive load"?
Back:  The total amount of mental effort being used in working memory at 
       any moment. Working memory can hold ~4 items at once. Exceed that, 
       and learning/performance collapses.
       → Practical: When explaining something, limit to 3-4 points at once. 
       More = cognitive overload = nobody remembers anything.
Tags: #psychology #learning-science
```

**Card 2 — Cloze for Precise Terminology:**
```
Note Type: Cloze
Text: {{c1::Motivated reasoning}} is the tendency to process information 
      in a way that supports {{c2::what you already believe}}, regardless 
      of evidence. Smart people are {{c3::MORE}} susceptible because 
      they're better at {{c4::constructing convincing justifications}}.
Tags: #cognitive-bias #psychology
```

**Card 3 — Contrast Definition:**
```
Note Type: Basic
Front: What's the difference between "correlation" and "causation"?
Back:  Correlation: X and Y happen together (ice cream sales and drownings 
       both rise in summer). 
       Causation: X actually CAUSES Y.
       Correlation ≠ causation. The hidden variable (summer heat) causes 
       both. Most wrong conclusions come from confusing these two.
Tags: #statistics #critical-thinking
```

---

### E. Frameworks & Processes

**Card 1 — Steps of a Framework:**
```
Note Type: Cloze
Text: The PREP framework for structuring an opinion:
      {{c1::P}}oint → {{c2::R}}eason → {{c3::E}}xample → {{c4::P}}oint (restate)
Tags: #framework #communication
```

**Card 2 — When to Use It:**
```
Note Type: Basic
Front: When should you use the Pyramid Principle instead of PREP?
Back:  PREP = quick opinions in conversations and meetings (30-60 sec)
       Pyramid = longer documents, presentations, proposals (conclusion 
       first, then supporting arguments, then evidence)
       Rule of thumb: speaking < 2 min → PREP. Writing or presenting → Pyramid.
Tags: #framework #communication #application
```

**Card 3 — Framework Application:**
```
Note Type: Basic
Front: Use the SBI framework to give feedback: your teammate showed up 
       15 minutes late to a client demo.
Back:  S (Situation): "In this morning's client demo..."
       B (Behavior): "...you arrived 15 minutes after it started..."
       I (Impact): "...which meant the client was waiting and it made 
       our team look disorganized."
       (No judgment, no "you're always late," just facts + impact)
Tags: #framework #leadership #application
```

---

### F. Quotes Worth Remembering

```
Note Type: Basic
Front: Complete the Charlie Munger quote: "Show me the _____ and I'll 
       show you the _____."
Back:  "Show me the INCENTIVE and I'll show you the OUTCOME."
       Meaning: People respond to reward structures, not instructions. 
       To predict behavior, look at what's being rewarded.
Tags: #quote #mental-model #incentives
```

---

### G. Worldly Knowledge Facts

```
Note Type: Basic
Front: What percentage of actively managed funds underperform index 
       funds over a 20-year period?
Back:  ~90%. This is why index funds are the default recommendation for 
       most investors. You're paying fund managers to LOSE to the market.
       (Source: S&P SPIVA scorecards)
Tags: #finance #worldly-knowledge
```

```
Note Type: Basic
Front: What did Ebbinghaus discover about memory in 1885?
Back:  The Forgetting Curve: without reinforcement, you lose ~70% of new 
       information within 48 hours and ~90% within a month. This is the 
       scientific basis for spaced repetition (Anki).
Tags: #psychology #learning-science
```

---

## 7. How to Navigate Anki — The Interface

### The Main Screen

When you open Anki, you see your deck list:

```
┌──────────────────────────────────────────────────────┐
│  Decks                                    Due  New   │
│  ────────────────────────────────────────────────── │
│  Mental Models & Key Concepts              12    3   │
│  English Vocabulary                         8    5   │
│  Books & Reading                            4    2   │
│  Worldly Knowledge                          2    0   │
│                                                      │
│               [Create Deck]                          │
└──────────────────────────────────────────────────────┘
```

- **Due** = cards scheduled for review today (you've seen them before)
- **New** = cards you haven't studied yet

Click a deck → **Study Now** to begin reviewing.

### The Review Screen

```
┌──────────────────────────────────────────────────────┐
│                                                      │
│          What is First Principles Thinking?           │
│                                                      │
│                                                      │
│                 [Show Answer]                         │
│                                                      │
└──────────────────────────────────────────────────────┘
```

After clicking Show Answer:

```
┌──────────────────────────────────────────────────────┐
│          What is First Principles Thinking?           │
│  ──────────────────────────────────────────────────  │
│  Breaking a problem down to its fundamental truths   │
│  and reasoning up from there, instead of...          │
│                                                      │
│   [Again]    [Hard]     [Good]     [Easy]            │
│    <1m        <6m       <10m        4d               │
└──────────────────────────────────────────────────────┘
```

The numbers below each button show when Anki will show you this card again.

### The Add Card Screen

**Click "Add" at the top (or press `A`)**

```
┌──────────────────────────────────────────────────────┐
│  Type: [Basic          ▼]   Deck: [Mental Models  ▼] │
│                                                      │
│  Front:                                              │
│  ┌──────────────────────────────────────────────┐    │
│  │ What is ______?                              │    │
│  └──────────────────────────────────────────────┘    │
│                                                      │
│  Back:                                               │
│  ┌──────────────────────────────────────────────┐    │
│  │ Your answer here...                          │    │
│  └──────────────────────────────────────────────┘    │
│                                                      │
│  Tags: mental-model decision-making                  │
│                                                      │
│              [Add]    [Close]                         │
└──────────────────────────────────────────────────────┘
```

- **Type dropdown:** Choose Basic, Basic (reversed), or Cloze
- **Deck dropdown:** Choose which deck this card belongs to
- **Tags:** Add tags (space-separated) for filtering later
- Click **Add** (or `Ctrl+Enter`) to save the card and immediately create another

### The Browse Screen

**Click "Browse" at the top (or press `B`)**

This is your card database. You can:
- Search cards by text, tag, deck, or date
- Edit any card
- Delete cards
- See card statistics (how often you got it right/wrong)
- Move cards between decks
- Suspend cards (temporarily remove from review)

**Useful search queries in Browse:**
```
deck:"English Vocabulary"           → all cards in that deck
tag:mental-model                    → all cards with that tag
is:due                              → all cards due today
is:new                              → all cards you haven't studied
is:suspended                        → all suspended cards
added:7                             → cards added in the last 7 days
rated:7:1                           → cards you got WRONG in the last 7 days
prop:ivl>180                        → cards with interval > 180 days (mastered)
```

### Key Keyboard Shortcuts

| Shortcut | Action |
|---|---|
| `A` | Add new card |
| `B` | Browse all cards |
| `D` | Open deck list |
| `S` | Open Statistics |
| `Y` or `Ctrl+Z` | Undo last review |
| `1` | Again (during review) |
| `2` | Hard (during review) |
| `3` | Good (during review) |
| `4` | Easy (during review) |
| `Space` | Show answer / Rate "Good" |
| `Ctrl+Enter` | Save card (when adding) |
| `E` | Edit current card (during review) |
| `@` | Suspend current card (during review) |

---

## 8. Spaced Repetition Settings — What to Change

### Access Settings

Click a deck → gear icon (⚙) → **Options**

### Recommended Settings for Beginners

#### New Cards Tab

| Setting | Default | Change To | Why |
|---|---|---|---|
| **Learning steps** | 1m 10m | **1m 10m 1d** | Adds a next-day review before the card enters the "review" phase. Catches cards you only *thought* you knew. |
| **Graduating interval** | 1 day | **3 days** | After passing all learning steps, first review is in 3 days (not 1). Slight spacing improves retention. |
| **Easy interval** | 4 days | **7 days** | Cards you mark "Easy" jump further ahead. |
| **New cards/day** | 20 | **10** | Start with 10 new cards/day. You can increase later. Too many new cards = overwhelming reviews in 2 weeks. |

#### Reviews Tab

| Setting | Default | Change To | Why |
|---|---|---|---|
| **Maximum reviews/day** | 200 | **9999** | Never cap your reviews. If you have 50 due, do 50. Skipping reviews defeats the entire system. |
| **Easy bonus** | 130% | **130%** (keep) | Fine as-is |
| **Interval modifier** | 100% | **100%** (keep) | Only change after 3+ months of data. If you're forgetting too many cards (~90% retention target), lower to 80-90%. |
| **Maximum interval** | 36500 | **365** | Cap at 1 year. No card should go longer than 365 days between reviews for the first year. |

#### Lapses Tab

| Setting | Default | Change To | Why |
|---|---|---|---|
| **Relearning steps** | 10m | **10m 1d** | When you fail a card, it becomes a "lapse." This ensures you see it again in 10 min AND the next day. |
| **Minimum interval** | 1 day | **1 day** (keep) | After failing, minimum 1 day before next review |
| **Leech threshold** | 8 fails | **5 fails** | If you fail a card 5 times, Anki tags it as a "leech." This signals: the card is poorly written and needs to be rewritten or deleted. |
| **Leech action** | Suspend Card | **Tag Only** | Don't auto-suspend. Instead, get notified so you can fix the card. |

### How to Apply Settings to All Decks

1. Edit settings for one deck (following above)
2. Name the preset: "Mastery System" (click "Save" at top of options)
3. For each other deck → gear icon → Options → select "Mastery System" from the preset dropdown

---

## 9. The Daily Review Workflow

### The Routine (5–10 minutes)

```
1. Open Anki (desktop or phone)
2. Click deck with most due cards → Study Now
3. For each card:
   a. Read the question
   b. THINK of the answer before clicking Show Answer (this is the retrieval!)
   c. Click Show Answer
   d. Rate: Again / Hard / Good / Easy
4. After finishing one deck, do the next
5. Sync when done
```

### When to Review

**Best time: morning, after meditation, before deep work.** Your brain is freshest and Anki primes the knowledge you'll use during the day.

**Alternative:** During dead time — commute, waiting in line, lunch break. This is why the phone app matters.

**Non-negotiable rule:** Review ALL due cards every day. If you skip one day, tomorrow's pile doubles. Skip two days, it triples. The Mastery System's Minimum Viable Day (Section 40) includes "Anki (5 min)" for exactly this reason — even on terrible days, do your reviews.

### How Long Will It Take?

| Cards in Collection | Daily Reviews (approx.) | Time (approx.) |
|---|---|---|
| 50 | 5–10 | 2–3 min |
| 100 | 10–20 | 3–5 min |
| 200 | 15–30 | 5–8 min |
| 500 | 30–60 | 8–15 min |
| 1,000 | 50–80 | 12–20 min |

If reviews take more than 15 min/day, slow down on adding new cards. Let the existing pile stabilize first.

### The Grading Strategy

| Button | When to Press | Effect |
|---|---|---|
| **Again** | You completely blanked. No idea. | Resets the card. You'll see it again in minutes. |
| **Hard** | You struggled. Got it partially or after a long pause. | Short interval. You'll see it soon. |
| **Good** | You recalled it correctly with moderate effort. | Normal interval increase. **This is your default.** |
| **Easy** | You knew it instantly, without thinking. | Longer interval. Card is mastered for now. |

**The Rule:** Press **Good** 70–80% of the time. If you're pressing Easy on everything, your cards are too easy. If you're pressing Again on everything, you're adding too many new cards or your cards need rewriting.

**Target retention rate:** ~85–90%. Check in **Stats** (`S`). If your "mature correct %" is below 80%, either reduce new cards or rewrite the cards you're failing.

---

## 10. When to Discard, Edit, or Make Cards Permanent

### When to EDIT a Card

**Signal:** You keep getting it wrong, but the concept is important.

The card is probably poorly written. Fix it:
- Make the question more specific
- Shorten the answer
- Add an example or analogy
- Split into 2 smaller cards

**Example fix:**
```
BEFORE (too vague):
Front: What is availability bias?
Back: A cognitive bias about availability.

AFTER (specific + example):
Front: What is the Availability Heuristic?
Back: Judging probability by how easily examples come to mind.
      Plane crashes feel more likely than heart disease because 
      crashes are vivid and dramatic (available in memory), even 
      though heart disease kills 1,000x more people.
```

### When to DELETE (Discard) a Card

**Signal 1 — Leech card:** Anki flags it after 5+ failures. This means the card is fundamentally broken or the concept isn't clear enough in your mind. Options:
- Rewrite the card completely (if the concept matters)
- Delete the card and go BACK to the source material — re-read the Zettelkasten note, then create a fresh card

**Signal 2 — You don't care anymore:** You created a card about something that turned out to be unimportant. Delete it. Don't waste review time on knowledge that doesn't serve your goals.

**Signal 3 — Duplicate:** You realize two cards test the same thing. Delete the weaker one.

**Signal 4 — Too trivial:** The fact is so basic you'd never forget it. "What color is the sky?" → Delete. Your brain doesn't need Anki for this.

**How to delete:** During review, press `E` to edit → Delete button. Or go to Browse → select card → Delete.

### When to SUSPEND a Card (Temporary Pause)

**Signal:** The card is fine, but you don't need it right now. Maybe you created cards about a framework you won't use until Month 6.

- Press `@` during review to suspend
- The card disappears from reviews but stays in your collection
- Unsuspend later: Browse → `is:suspended` → select → right-click → Unsuspend

### When a Card Becomes "Permanent" (Mastered)

You don't do anything — Anki handles this automatically. As you keep pressing "Good," the interval grows:

```
1d → 3d → 8d → 21d → 60d → 180d → 365d
```

When a card's interval exceeds ~180 days, it's effectively permanent. You'll see it once every 6 months — a few seconds twice a year to maintain a piece of knowledge forever.

**In Anki Stats, these are called "mature" cards** (interval > 21 days). Over time, most of your collection becomes mature. Your daily reviews consist mostly of a few mature cards coming up for their long-interval check-in, plus whatever new cards you're learning.

### The Lifecycle of an Anki Card

```
New Card                              ← You just created it
    ↓
Learning (seen 2-3 times in 24hrs)    ← Short intervals, still fragile
    ↓
Young (interval < 21 days)            ← Growing stronger
    ↓
Mature (interval > 21 days)           ← Solidifying in long-term memory
    ↓
Mastered (interval > 180 days)        ← Effectively permanent
    
At ANY stage:
  → Leech (5+ failures) → REWRITE or DELETE
  → No longer relevant  → DELETE
  → Not needed now       → SUSPEND
```

---

## 11. Common Mistakes to Avoid

### Mistake 1: Adding Too Many Cards at Once

**The trap:** You read a great book and excitedly create 40 cards in one day.

**The problem:** In 2 weeks, those 40 cards all come due for review on similar days. Your daily review balloons from 5 minutes to 30 minutes. You get overwhelmed and abandon Anki entirely.

**The fix:** Add 5–10 new cards per day maximum. If you have 30 cards from a book, spread them over a week. The"New cards/day" setting (set to 10) enforces this automatically.

### Mistake 2: Making Cards Too Long

**The trap:** Your "back" field is a 200-word paragraph.

**The problem:** You can't retrieve it. You get frustrated. The card becomes a leech.

**The fix:** 1–3 sentences max. If you need more, split into multiple cards or link to your Zettelkasten note.

### Mistake 3: Cards That Are Too Easy

**The trap:** "What does H₂O stand for?" → "Water"

**The problem:** You're wasting review time on things you'll never forget.

**The fix:** Only create cards for knowledge that's at the EDGE of your understanding — things you'd forget without reinforcement. If something is truly obvious, don't add it.

### Mistake 4: Never Deleting Cards

**The trap:** 1,000 cards, 200 of which are irrelevant, poorly written, or duplicates.

**The problem:** Your reviews include junk. You lose motivation. The noise drowns the signal.

**The fix:** Review your leech cards monthly. Delete ruthlessly. A lean deck of 300 excellent cards beats a bloated deck of 1,000 mediocre ones.

### Mistake 5: Skipping Days

**The trap:** "I'll skip today and do double tomorrow."

**The problem:** Skipping breaks the spaced repetition algorithm. Cards that were supposed to be reviewed at their optimal forgetting point are now overdue. The algorithm has to recalculate. Your retention drops. Your review pile balloons.

**The fix:** Never skip. Even on Minimum Viable Days, Anki reviews (5 min) are non-negotiable. Use the phone app during dead time if you can't sit at a computer.

### Mistake 6: Reviewing Without Thinking

**The trap:** You flip through cards on autopilot — see question, immediately flip, glance at answer, press "Good."

**The problem:** You're not doing retrieval practice. You're doing recognition practice. Your brain sees the question, doesn't attempt to recall, and then confirms "yeah, that rings a bell." This wastes time and teaches nothing.

**The fix:** Before pressing "Show Answer," actually formulate the answer in your head (or say it out loud). The struggle is the entire point. If you can't produce the answer, that's valuable information — press "Again."

### Mistake 7: Pretty-Fying Cards Instead of Writing Them

**The trap:** Spending 20 minutes on fonts, colors, formatting, and images for each card.

**The problem:** You create 2 beautiful cards instead of 10 functional ones.

**The fix:** Plain text is fine. Formatting only when it genuinely aids understanding (e.g., a table, a diagram). Content > cosmetics. Always.

### Mistake 8: Using Someone Else's Deck

**The trap:** Downloading a pre-made "30 Mental Models" deck from AnkiWeb.

**The problem:** The cards are in someone else's words. Your brain doesn't have the same understanding attached to their phrasing. You'll struggle to remember because the cards don't connect to YOUR experiences or YOUR understanding.

**The fix:** Always create your own cards. The ACT OF CREATING the card is half the learning. It forces you to articulate the idea in your own words — which IS the Feynman Technique.

**Exception:** Language pronunciation decks with audio are fine to download — native pronunciation is objective, not personal.

---

## 12. Advanced Techniques (Month 2+)

### Technique 1: The "Extra" Field

Every Basic card has a hidden "Extra" field (visible in the card editor). Use it for:
- The source (book name, page number)
- A link to your Obsidian Zettelkasten note
- A deeper explanation you don't need for the quick review but might want to reference

The Extra field appears below the Back field when you reveal the answer — like bonus context.

### Technique 2: Custom Study Sessions

Before a presentation about decision-making, you want to review ONLY those cards:

1. Click your deck → **Custom Study** (at bottom)
2. Choose "Study by card state or tag"
3. Filter by tag: `decision-making`
4. Review just those cards

This is targeted retrieval practice — cramming (in a good way) before you need the knowledge.

### Technique 3: Filtered Decks (for focused review)

**Tools → Create Filtered Deck:**
- Name: "Pre-Presentation Review"
- Search: `tag:communication OR tag:framework`
- This creates a temporary deck with just those cards
- After studying, cards return to their original decks

### Technique 4: Image Occlusion (with add-on)

Install the "Image Occlusion" add-on. It lets you:
1. Import a diagram (e.g., the Eisenhower Matrix)
2. Cover parts of it with rectangles
3. Each rectangle becomes a card — "What goes in this quadrant?"

Great for: frameworks, charts, process diagrams, anatomy.

### Technique 5: The Forgetting Index

After 3+ months, check your Stats (`S`):
- **True retention rate** should be 85–90%
- If below 80%: lower the Interval Modifier to 85% (cards repeat more often)
- If above 95%: raise the Interval Modifier to 110% (cards repeat less — you're over-reviewing)

### Technique 6: Useful Add-Ons (Install via code from AnkiWeb)

| Add-On | Code | What It Does |
|---|---|---|
| **Review Heatmap** | 1771074083 | Visual heatmap of your review streak (like GitHub contribution graph) |
| **More Overview Stats** | 738807903 | Better statistics on your performance |
| **Edit Field During Review** | 1020366288 | Edit the current card without opening the full editor |
| **Image Occlusion** | 1374772155 | Cover parts of images to create visual cards |
| **Frozen Fields** | 516643804 | Keep certain fields sticky when adding multiple cards (e.g., keep the tag and deck constant) |

**How to install add-ons:** Tools → Add-ons → Get Add-ons → paste the code → Restart Anki.

> **Rule:** Like Obsidian plugins — don't install any add-ons for the first month. Learn the basics first. Add one at a time when you feel the need.

---

## 13. Anki + Mastery System Integration

### How Anki Fits Into Your Daily Routine

From your Mastery System daily schedule:

```
Phase 1 (Months 1-2):
  Morning block: ... → Anki review (5 min) ← HERE
  Evening block: ... → Stoic reflection + journal + Anki (5 min) 
                       ← AND HERE (adding new cards)

Phase 2+:
  Same pattern: morning REVIEW, evening ADD
```

**Morning = review.** Pull out what you know. 5 minutes.
**Evening = add.** Create 3–5 new cards from what you learned today. 3 minutes.

### What to Create Cards For (By Phase)

| Phase | Card Focus | Examples |
|---|---|---|
| **Month 1** | Learning science + first mental models | Forgetting Curve, Retrieval Practice, First Principles, Inversion, Incentives |
| **Month 2** | Cognitive biases + Stoic principles | Confirmation bias, Sunk cost, Dunning-Kruger, Dichotomy of Control |
| **Month 3** | Frameworks + vocabulary + economics | PREP, Pyramid, STAR, new professional words, supply/demand |
| **Month 4** | Persuasion + habits + more models | Cialdini's 6 principles, Habit Loop, Occam's Razor |
| **Month 5-8** | Discipline concepts + integration | Cross-domain cards (physics→business), advanced vocabulary |
| **Month 9+** | Refinement + maintenance | Fewer new cards, mostly maintaining the existing collection |

### Target Card Counts (Milestones)

| Milestone | Target Card Count |
|---|---|
| End of Month 1 | 50–80 cards |
| End of Month 2 | 100–150 cards |
| End of Month 4 | 200–300 cards |
| End of Month 8 | 400–500 cards |
| End of Month 12 | 500–700 cards |
| End of Month 24 | 700–1,000 cards |

These are guidelines, not rules. Quality > quantity. 300 excellent cards beat 1,000 mediocre ones.

### The Card Creation Triggers

Create an Anki card whenever:

```
✓ You learn a new mental model → card with definition + 1 example
✓ You learn a new English word → reversed card (word ↔ meaning)
✓ You finish a book chapter → 3-5 cards on the key ideas
✓ You learn a new framework → cloze card for the steps
✓ You hear a concept you want to remember forever → basic card
✓ You make a cross-domain connection → consider a card if the core
  insight is expressible in 2-3 sentences
✓ You discover a common bias or mistake → card with definition + example
```

Do NOT create a card for:
```
✗ Something you already know well (waste of review time)
✗ Something too complex for 1–3 sentences (put in Zettelkasten only)
✗ Something you won't need again (a specific meeting date, etc.)
✗ Raw book quotes without your interpretation (add your understanding)
✗ Entire processes with 10+ steps (break into pieces or keep in Obsidian)
```

---

## 14. Quick Reference Card

Print this or keep it open on Day 1:

```
╔══════════════════════════════════════════════════════════╗
║                    ANKI QUICK REFERENCE                  ║
║                                                          ║
║  SETUP:                                                  ║
║   • 4 Decks: Models, Vocabulary, Books, Worldly          ║
║   • Settings: 10 new/day, 1m-10m-1d learning steps       ║
║   • Sync desktop ↔ phone via AnkiWeb account             ║
║                                                          ║
║  DAILY ROUTINE:                                          ║
║   • Morning: Review all due cards (5 min)                ║
║   • Evening: Add 3-5 new cards from today's learning     ║
║   • NEVER skip. Minimum Viable Day = Anki reviews.       ║
║                                                          ║
║  CREATING CARDS:                                         ║
║   • One question, one answer (atomic)                    ║
║   • Your own words (never copy-paste)                    ║
║   • Include 1 example                                    ║
║   • 1–3 sentences on back (max)                          ║
║   • Tag every card (#mental-model, #vocabulary, etc.)    ║
║                                                          ║
║  REVIEWING:                                              ║
║   • THINK before flipping (retrieval = learning)         ║
║   • Default: press "Good" (3 key)                        ║
║   • "Again" = blank. "Easy" = instant recall.            ║
║   • Target: 85–90% correct on mature cards               ║
║                                                          ║
║  MAINTENANCE:                                            ║
║   • Monthly: review leech cards → rewrite or delete      ║
║   • Delete cards you don't care about anymore            ║
║   • Never let Inbox pile > comfortable daily review      ║
║                                                          ║
║  SHORTCUTS:                                              ║
║   • A = Add  B = Browse  S = Stats  Space = Show/Good    ║
║   • 1 = Again  2 = Hard  3 = Good  4 = Easy             ║
║   • E = Edit card during review  @ = Suspend             ║
║                                                          ║
║  THE RULE:                                               ║
║   • Make your own cards. Your words = your memory.       ║
║   • 300 great cards > 1,000 mediocre cards.              ║
║   • Review daily. The chain is everything.               ║
╚══════════════════════════════════════════════════════════╝
```

---

> **Remember:** Anki is NOT the learning. Anki is the RETENTION. You learn by reading, writing, thinking, and explaining (your Zettelkasten, your essays, your speaking drills). Anki makes sure you KEEP what you learn. Without Anki, you'll forget 90% of this system in 6 months. With Anki, you'll remember it forever — 5 minutes a day. That's the deal. Take it.
