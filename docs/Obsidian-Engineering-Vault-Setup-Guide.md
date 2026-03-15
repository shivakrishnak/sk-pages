# Obsidian Engineering Vault — Setup Guide

> **Purpose:** This is your second brain for software engineering. Everything you learn, debug, decide, and build gets captured here. In 6 months, you'll be the person everyone comes to because you REMEMBER everything — not because your memory is better, but because your SYSTEM is better.

---

## Why This Vault Exists

Most engineers lose 80% of what they learn:
- You debug the same class of problem twice because you forgot how you fixed it last time
- You sit in architecture meetings and can't recall why a past decision was made
- You read about a design pattern, use it once, and forget the details
- New team members ask questions and you give vague answers instead of precise ones
- You know you read something about that API, but can't find it

**This vault fixes all of that.** Every debugging session, architecture decision, system insight, and meeting outcome gets captured, linked, and made retrievable. You stop relying on memory and start relying on a system.

**The goal:** Become the engineer who always has the answer — not because you're smarter, but because you wrote it down, linked it, and can find it in 10 seconds.

---

## Table of Contents

1. [Vault Setup](#1-vault-setup)
2. [Folder Structure — What Each Folder Means](#2-folder-structure--what-each-folder-means)
3. [How Notes Flow Between Folders](#3-how-notes-flow-between-folders)
4. [Sample Notes in Every Folder](#4-sample-notes-in-every-folder)
5. [How to Write Engineering Notes That Actually Help](#5-how-to-write-engineering-notes-that-actually-help)
6. [Linking Strategy for Engineering](#6-linking-strategy-for-engineering)
7. [Tags Strategy](#7-tags-strategy)
8. [Templates Setup & Usage](#8-templates-setup--usage)
9. [Essential Plugins](#9-essential-plugins)
10. [Daily Engineering Workflow](#10-daily-engineering-workflow)
11. [Weekly Engineering Review](#11-weekly-engineering-review)
12. [Retention System — How to Actually Remember](#12-retention-system--how-to-actually-remember)
13. [Becoming the Go-To Engineer](#13-becoming-the-go-to-engineer)
14. [Keyboard Shortcuts](#14-keyboard-shortcuts)
15. [Common Mistakes](#15-common-mistakes)
16. [Day 1 Settings](#16-day-1-settings)

---

## 1. Vault Setup

### Step 1: Create the Vault
1. Open Obsidian → "Create new vault"
2. Name: `Engineering` (keep it separate from your Mastery vault — different purpose, different rhythm)
3. Location: A cloud-synced folder (OneDrive/Google Drive) so you can access from work and home

### Step 2: Create the Folder Structure

```
Engineering/
├── 00 Inbox/                  ← Quick captures during the day
├── 01 Engineering Knowledge/  ← Atomic notes: concepts, patterns, tools, languages
├── 02 Architecture Decisions/ ← ADRs: why we chose what we chose
├── 03 Systems & Services/     ← Living docs of every system you work on
├── 04 Debugging Journal/      ← Every non-trivial bug you solve
├── 05 Incident Log/           ← Post-mortems and incident learnings
├── 06 Meeting Notes/          ← Decisions and context from meetings
├── 07 1-on-1 Notes/           ← Manager and direct report conversations
├── 08 Project Notes/          ← Per-project context, goals, decisions
├── 09 Runbooks/               ← Step-by-step operational procedures
├── 10 People & Teams/         ← Who knows what, team context, stakeholders
├── 11 Code Review Learnings/  ← Patterns and insights from reviewing code
├── 12 Weekly Log/             ← Weekly work summaries and reflections
├── Templates/                 ← Note templates
```

> **Why separate from your Mastery vault?** Different purposes require different structures. Your Mastery vault is for personal intellectual growth. This vault is for professional engineering excellence. Keeping them separate prevents clutter and lets each system serve its purpose cleanly.

---

## 2. Folder Structure — What Each Folder Means

### 00 Inbox — Capture Everything, Sort Later

**What goes here:** Anything work-related that pops into your head during the day. A Slack message worth remembering months later. A quick insight during a code review. A question you want to research later.

**Rules:**
- Capture in under 30 seconds. Don't format. Don't organize. Just dump.
- Process daily or at minimum every Friday.
- Nothing stays here more than 1 week.

**Examples:**
- "Redis SCAN is O(1) per call but O(N) total — look into why we use KEYS in prod"
- "Priya mentioned the payment service has a circuit breaker — find out which library"
- "That retry logic in OrderService looks like exponential backoff but isn't — check"

---

### 01 Engineering Knowledge — Your Technical Brain

**What goes here:** Atomic notes about engineering concepts, design patterns, language features, tools, algorithms, and anything technical you want to retain permanently.

**This is the core of your engineering vault.** Each note = one concept, explained in your words, with examples from YOUR codebase when possible.

**Rules:**
- One concept per note
- Explain it like you're teaching a junior engineer (forces clarity)
- Include a code example when relevant (preferably from YOUR actual work)
- Link to related concepts
- Title = the concept: `Circuit Breaker Pattern`, `PostgreSQL Index Types`, `CAP Theorem`

**What belongs here:**
- Design patterns (Circuit Breaker, Saga, CQRS, Event Sourcing...)
- Language deep-dives (Java generics, Python decorators, TypeScript utility types...)
- Database concepts (indexing, query optimization, replication, sharding...)
- Infrastructure (Kubernetes, Docker, CI/CD pipelines, load balancing...)
- Algorithms & data structures you encounter at work
- API design principles
- Security concepts (OAuth, JWT, CORS, SQL injection prevention...)
- Performance optimization techniques
- Testing strategies (unit, integration, contract, chaos...)

---

### 02 Architecture Decisions — Why We Built It This Way

**What goes here:** Architecture Decision Records (ADRs). Every significant technical decision — what was decided, what alternatives were considered, and WHY.

**Why this matters:** 6 months from now, someone (probably you) will ask "Why did we use Kafka instead of RabbitMQ?" or "Why is the user service separate from the auth service?" The ADR answers that question in 2 minutes instead of a 45-minute archaeology session through Slack and Git history.

**Rules:**
- One file per decision
- Record the CONTEXT (what problem we were solving)
- Record the OPTIONS (what we considered)
- Record the DECISION and the REASONING
- Record the CONSEQUENCES (trade-offs we accepted)
- Date everything

---

### 03 Systems & Services — Your Living System Map

**What goes here:** One note per system/service/major component your team owns or interacts with. A living document that answers: "What does this thing do, how does it work, and where does it break?"

**This is the folder that makes you the go-to person.** When someone asks "How does the notification service work?" you open one note and have everything: purpose, architecture, dependencies, common failure modes, key endpoints, deployment process.

**Rules:**
- One file per system/service
- Update whenever you learn something new about the system
- Include: purpose, architecture, dependencies, data flow, failure modes, key contacts
- This is a LIVING document — not write-once

---

### 04 Debugging Journal — Never Solve the Same Bug Twice

**What goes here:** Every non-trivial bug you investigate. The symptoms, what you tried, what worked, root cause, and the fix.

**Why this is gold:**
- You'll encounter similar bugs again. Future you will thank past you.
- Debugging patterns transfer across systems. A race condition in Service A teaches you to spot race conditions in Service B.
- During performance reviews, this folder is EVIDENCE of your impact.
- Junior engineers can learn from your debugging process.

**Rules:**
- Record the SYMPTOMS (what you observed)
- Record the INVESTIGATION (what you tried, including dead ends)
- Record the ROOT CAUSE (the actual problem)
- Record the FIX (what you changed)
- Record the LESSON (what you'd check first next time)
- Tag by category: `#race-condition`, `#memory-leak`, `#timeout`, `#data-corruption`, etc.

---

### 05 Incident Log — Post-Mortems and Outage Learnings

**What goes here:** Production incidents, outages, and near-misses. What happened, why, what was the blast radius, and what we changed to prevent recurrence.

**Rules:**
- One file per incident
- Blameless — focus on systems, not people
- Include timeline, root cause, impact, and action items
- Link to related systems in `03 Systems & Services/`
- Review quarterly — are patterns emerging?

---

### 06 Meeting Notes — Decisions, Not Transcripts

**What goes here:** Notes from meetings where DECISIONS were made or important CONTEXT was shared. Not every meeting — only ones with lasting value.

**Rules:**
- Only capture: decisions made, action items, context that won't be written elsewhere
- Skip meetings that produce no decisions or new information
- 5-10 lines is enough. This is not a transcript.
- Always record WHO decided WHAT and BY WHEN

---

### 07 1-on-1 Notes — Career and Relationship Tracking

**What goes here:** Notes from every 1-on-1 with your manager, and with anyone you manage.

**Why this matters:**
- Track feedback themes over time (what keeps coming up?)
- Remember commitments your manager made ("I'll advocate for your promotion in Q3")
- Prepare for performance reviews with 12 months of documented conversations
- Track career goals and progress

**Rules:**
- One file per person, running chronologically (not one file per meeting)
- Record: what was discussed, feedback given/received, commitments, action items
- Before each 1-on-1, review the last entry to follow up

---

### 08 Project Notes — Per-Project Context

**What goes here:** One file per project or major initiative. Goals, scope, key decisions, stakeholders, timeline, risks, and learnings.

**Rules:**
- Create at project kickoff
- Update as the project evolves
- At project end, write a "What I Learned" section — this is how you compound engineering judgment

---

### 09 Runbooks — Step-by-Step Procedures

**What goes here:** Operational procedures you or your team perform. Deployment steps, database migrations, scaling procedures, rollback processes, on-call triage steps.

**Why this matters:**
- You do these procedures infrequently enough to forget the details
- When it's 2am and the pager goes off, you need clear steps, not fuzzy memory
- Makes you replaceable in a GOOD way — the team can operate without you
- Onboarding new team members becomes "read the runbooks"

**Rules:**
- Step-by-step, numbered, no ambiguity
- Include prerequisites, verification steps, and rollback instructions
- Test the runbook by having someone else follow it
- Date and version everything — procedures change

---

### 10 People & Teams — Your Professional Network Map

**What goes here:** Notes on key people you work with. What they're experts in, what they care about, their communication style, and how to work effectively with them.

**This is the secret weapon for cross-team collaboration.** When you need help with the payment system, you don't Slack "does anyone know about payments?" — you open this folder and find "Raj — owns payment-service, prefers async communication, very responsive to well-written Slack messages with context."

**Rules:**
- One file per person (or per team for teams you interact with less frequently)
- Professional information only — expertise, projects, communication preferences
- Update when you learn something new about working with them
- NOT a gossip file — only information that helps you collaborate better

---

### 11 Code Review Learnings — Patterns Worth Remembering

**What goes here:** Insights from code reviews — both reviewing others' code and receiving feedback on yours.

**Why this matters:**
- Code reviews expose you to patterns and anti-patterns across the codebase
- Feedback you receive repeatedly = a blind spot to fix
- Patterns you notice repeatedly = teaching material for the team

**Rules:**
- Short notes: the pattern/anti-pattern + why it matters + example
- Link to relevant concepts in `01 Engineering Knowledge/`
- Review monthly — are you seeing the same issues? Time to write a team guide or propose a linting rule.

---

### 12 Weekly Log — Your Engineering Journal

**What goes here:** Weekly summaries of what you worked on, what you learned, what was hard, and what you'd do differently.

**Why this matters:**
- Performance reviews become trivial — you have 52 weeks of documented impact
- You spot patterns: recurring blockers, skills you need to develop, time sinks
- Career growth becomes visible: compare Week 1 to Week 50

**Rules:**
- One file per week
- 10-15 minutes every Friday
- Use the Weekly Engineering Review template (Section 11)

---

## 3. How Notes Flow Between Folders

```
                    ┌─────────────────────┐
                    │     00 INBOX        │
                    │  (quick captures)    │
                    └─────────┬───────────┘
                              │
                      Process (daily)
                              │
         ┌────────┬───────┬───┴───┬────────┬─────────┐
         ▼        ▼       ▼       ▼        ▼         ▼
   ┌──────────┐ ┌─────┐ ┌─────┐ ┌──────┐ ┌──────┐ ┌─────┐
   │01 Eng    │ │04   │ │03   │ │09    │ │11    │ │ 🗑  │
   │Knowledge │ │Debug│ │Sys &│ │Run-  │ │Code  │ │Del- │
   │(concept) │ │Jrnl │ │Svc  │ │books │ │Rev   │ │ete  │
   └────┬─────┘ └──┬──┘ └──┬──┘ └──────┘ └──────┘ └─────┘
        │          │       │
        └────┬─────┘       │
             │    Link     │
             ├─────────────┘
             ▼
     Everything links to
     everything relevant
```

### The Decision Tree for Inbox Notes

```
Is this a technical concept I want to remember?
  → YES → Rewrite as atomic note → 01 Engineering Knowledge/

Is this about a bug I solved or am investigating?
  → YES → Write up with symptoms/cause/fix → 04 Debugging Journal/

Is this about how a system works?
  → YES → Add to the system's note → 03 Systems & Services/

Is this a step-by-step procedure?
  → YES → Write as numbered steps → 09 Runbooks/

Is this a pattern I noticed in code review?
  → YES → Write up the pattern → 11 Code Review Learnings/

Is this something someone told me about their expertise?
  → YES → Update their note → 10 People & Teams/

Is this not worth keeping?
  → YES → Delete it. Don't hoard.
```

---

## 4. Sample Notes in Every Folder

### 00 Inbox — Raw Captures

**File:** `00 Inbox/redis ttl issue.md`
```markdown
OrderCache TTL is set to 3600s but we're seeing stale data after 10 min.
Amit mentioned maybe the TTL is being reset on every read? Check if we're 
using GET or GETEX. Also check if there's a background job refreshing cache.
```

**File:** `00 Inbox/interesting pattern from PR review.md`
```markdown
Saw in Priya's PR: she used a discriminated union type instead of optional 
fields for the API response. Much cleaner — forces the consumer to handle 
each case. Look into this pattern more.
```

---

### 01 Engineering Knowledge — Atomic Technical Notes

**File:** `01 Engineering Knowledge/Circuit Breaker Pattern.md`
```markdown
# Circuit Breaker Pattern

A resilience pattern that prevents cascading failures. When a downstream 
service fails repeatedly, the circuit breaker "opens" and stops sending 
requests — returning a fallback immediately instead of waiting for timeouts.

## The Three States

```
CLOSED → requests flow normally, failures are counted
  ↓ (failure threshold exceeded)
OPEN → all requests fail fast with fallback, no calls to downstream
  ↓ (after timeout period)
HALF-OPEN → one test request sent through
  ↓ success → back to CLOSED
  ↓ failure → back to OPEN
```

## Why It Matters
Without a circuit breaker, one failing service causes ALL callers to 
hang on timeouts, exhausting thread pools and cascading the failure 
upstream. With a circuit breaker, the failure is isolated in milliseconds.

## In Our Codebase
- We use **Resilience4j** in the payment-service → calls to stripe-api
- Configuration: `failureRateThreshold=50`, `waitDurationInOpenState=30s`
- Fallback: return cached last-known-good price when circuit is open
- See: [[payment-service]] for full architecture

## Code Example
```java
CircuitBreakerConfig config = CircuitBreakerConfig.custom()
    .failureRateThreshold(50)
    .waitDurationInOpenState(Duration.ofSeconds(30))
    .slidingWindowSize(10)
    .build();

CircuitBreaker breaker = CircuitBreaker.of("stripe", config);

Supplier<Price> decorated = CircuitBreaker.decorateSupplier(
    breaker, () -> stripeClient.getPrice(productId)
);

Try<Price> result = Try.ofSupplier(decorated)
    .recover(CallNotPermittedException.class, 
             e -> priceCache.getLastKnown(productId));
```

## When to Use
- Any call to an external service (APIs, databases, third-party)
- Any call across service boundaries in a microservice architecture
- NOT for in-process calls (overhead doesn't make sense)

## Related Patterns
- [[Retry with Backoff]] — try again, but carefully
- [[Bulkhead Pattern]] — isolate resources so one failure doesn't consume all
- [[Timeout Pattern]] — set hard limits on how long you wait
- [[Fallback Pattern]] — what to return when the primary path fails

---
**Source:** Release It! (Michael Nygard), Our payment-service implementation
**Tags:** #design-pattern #resilience #microservices
```

**File:** `01 Engineering Knowledge/PostgreSQL Index Types.md`
```markdown
# PostgreSQL Index Types

## B-Tree (Default)
- Best for: equality (`=`) and range (`<`, `>`, `BETWEEN`) queries
- The default. Use this unless you have a specific reason not to.
- Works with: `ORDER BY`, `UNIQUE` constraints
- Example: `CREATE INDEX idx_users_email ON users(email);`

## Hash
- Best for: equality (`=`) only. NOT for range queries.
- Slightly faster than B-Tree for pure equality lookups
- Rarely used — B-Tree handles equality well enough
- Example: `CREATE INDEX idx_users_id_hash ON users USING hash(id);`

## GIN (Generalized Inverted Index)
- Best for: full-text search, JSONB queries, array containment
- Slower to build and update, faster to search
- Example: `CREATE INDEX idx_products_tags ON products USING gin(tags);`
- In our codebase: used on [[product-service]] for JSONB metadata queries

## GiST (Generalized Search Tree)
- Best for: geometric data, full-text search, range types
- More versatile than GIN but sometimes slower for lookups

## BRIN (Block Range Index)
- Best for: very large tables with naturally ordered data (timestamps, sequences)
- Tiny index size — stores min/max per block range, not per row
- Example: `CREATE INDEX idx_events_created ON events USING brin(created_at);`
- In our codebase: used on [[analytics-service]] events table (100M+ rows, time-ordered)

## Decision Guide

| Query Pattern | Best Index |
|---|---|
| `WHERE email = 'x'` | B-Tree |
| `WHERE created_at > '2026-01-01'` | B-Tree (small table) or BRIN (huge table) |
| `WHERE metadata @> '{"type": "premium"}'` | GIN |
| `WHERE tags @> ARRAY['urgent']` | GIN |
| `WHERE to_tsvector(description) @@ 'search query'` | GIN or GiST |

## The Gotcha
Indexes speed up reads but slow down writes. Every INSERT/UPDATE must 
also update every index on that table. Don't create indexes "just in case" 
— create them to solve a measured performance problem.

Use `EXPLAIN ANALYZE` to verify your index is actually being used.

---
**Related:** [[Query Optimization]] | [[EXPLAIN ANALYZE]] | [[Database Partitioning]]
**Tags:** #database #postgresql #performance
```

**File:** `01 Engineering Knowledge/Discriminated Union Types.md`
```markdown
# Discriminated Union Types (Tagged Unions)

A pattern where a "type" or "status" field determines which other fields 
exist. Forces the consumer to handle each case explicitly — impossible to 
access fields that don't exist for that variant.

## The Problem Without It
```typescript
// BAD: Optional fields — caller has no idea what's actually present
interface ApiResponse {
  data?: UserData;
  error?: string;
  errorCode?: number;
}
// Caller: is response.data null because of an error? Or just loading?
```

## The Solution With Discriminated Union
```typescript
// GOOD: Each variant is explicit. Compiler enforces handling.
type ApiResponse = 
  | { status: 'success'; data: UserData }
  | { status: 'error'; error: string; errorCode: number }
  | { status: 'loading' };

function handle(response: ApiResponse) {
  switch (response.status) {
    case 'success':
      // TypeScript KNOWS response.data exists here
      renderUser(response.data);
      break;
    case 'error':
      // TypeScript KNOWS response.error exists here
      showError(response.error);
      break;
    case 'loading':
      showSpinner();
      break;
  }
}
```

## Why This Is Better
- Impossible to access `data` when status is `'error'` — compiler catches it
- Adding a new variant (e.g., `'cancelled'`) → compiler shows every 
  switch/if that needs updating
- Self-documenting: the type definition IS the documentation

## Where I've Seen This
- Priya's PR on the order-status endpoint (learned from code review)
- React Redux: action types are discriminated unions
- Rust enums — the entire language is built on this pattern

---
**Related:** [[TypeScript Utility Types]] | [[Exhaustive Switch]] | [[Code Review - Order Status PR]]
**Source:** Learned from [[Priya Sharma]]'s PR review
**Tags:** #typescript #design-pattern #type-safety
```

---

### 02 Architecture Decisions

**File:** `02 Architecture Decisions/ADR-001 - Kafka over RabbitMQ for event streaming.md`
```markdown
# ADR-001: Kafka over RabbitMQ for Event Streaming

**Date:** 2026-02-15
**Status:** Accepted
**Decided by:** Architecture review — Amit, Raj, me
**Context for:** [[order-service]] → [[notification-service]] communication

## Context
We need an event bus for order lifecycle events. Multiple consumers need 
the same events (notifications, analytics, billing). Current approach is 
direct HTTP calls, which creates tight coupling and cascading failures.

## Options Considered

| Option | Pros | Cons |
|---|---|---|
| **Kafka** | Event replay, multiple consumers, high throughput, event sourcing ready | Operational complexity, overkill for low volume |
| **RabbitMQ** | Simpler, good for task queues, lower ops overhead | No replay, single consumer per queue (without fanout), not built for event streaming |
| **AWS SNS+SQS** | Managed, low ops | Vendor lock-in, limited replay, higher latency |

## Decision
**Kafka.** Primary reasons:
1. We need multiple independent consumers reading the same events
2. Event replay is critical for rebuilding analytics after schema changes
3. We're planning event sourcing for the order domain (future-proofing)
4. Team has Kafka experience (Raj operated Kafka at previous company)

## Consequences
- **Positive:** True decoupling, event replay, supports future event sourcing
- **Negative:** Must operate Kafka cluster (or use managed Confluent), 
  team needs training on consumer group mechanics, message ordering 
  requires partition key strategy
- **Accepted trade-off:** Higher ops complexity in exchange for architectural flexibility

## Review Date
2026-08-15 — Evaluate: was the complexity worth it?

---
**Related:** [[order-service]] | [[notification-service]] | [[Event Sourcing]] | [[Kafka Consumer Groups]]
**Tags:** #adr #architecture #messaging
```

---

### 03 Systems & Services

**File:** `03 Systems & Services/order-service.md`
```markdown
# order-service

**Owner:** Commerce team (tech lead: Amit Kumar)
**Repo:** github.com/company/order-service
**Language:** Java 17, Spring Boot 3.2
**Database:** PostgreSQL 15 (RDS)
**Messaging:** Kafka producer → topic `order-events`

## What It Does
Manages the full order lifecycle: creation, payment processing, fulfillment 
tracking, cancellation, and refunds. The source of truth for all order data.

## Architecture
```
[API Gateway] → [order-service] → [PostgreSQL]
                      ↓
                  [Kafka: order-events]
                      ↓
        ┌─────────────┼──────────────┐
        ▼             ▼              ▼
[notification-svc] [analytics-svc] [billing-svc]
```

## Key Endpoints
| Endpoint | Method | Purpose |
|---|---|---|
| `/api/v1/orders` | POST | Create new order |
| `/api/v1/orders/{id}` | GET | Get order by ID |
| `/api/v1/orders/{id}/cancel` | POST | Cancel order |
| `/api/v1/orders/{id}/refund` | POST | Initiate refund |

## Data Flow
1. Client creates order → service validates inventory (calls [[inventory-service]])
2. Payment initiated → calls [[payment-service]] (has [[Circuit Breaker Pattern]])
3. On success → order persisted to PostgreSQL + event published to Kafka
4. Consumers pick up event for notifications, analytics, billing

## Known Issues / Gotchas
- **Stale cache:** Order status cache TTL is 5 min. For real-time status, 
  hit the DB endpoint (`/internal/orders/{id}?cache=false`)
- **Idempotency:** POST /orders requires `Idempotency-Key` header. Without 
  it, retries create duplicate orders. (Learned this the hard way — see 
  [[Debug - Duplicate Orders Incident 2026-01]])
- **Partition key:** Kafka events keyed by `orderId` — ordering guaranteed 
  within an order, NOT across orders

## Deployment
- Deployed via ArgoCD → Kubernetes (EKS)
- Canary deployment: 10% → 50% → 100% over 30 min
- Rollback: `argocd app rollback order-service`
- See [[Runbook - Deploy order-service]] for full steps

## Monitoring
- Grafana dashboard: "Order Service Health"
- Key metrics: p99 latency, error rate, Kafka consumer lag
- Alerts: PagerDuty → on-call rotation (Commerce team)

## Common Debugging Entry Points
- Orders not processing? Check Kafka consumer lag in Grafana
- Payment failures? Check [[payment-service]] circuit breaker state
- Slow queries? Check `order_items` table — needs index on `order_id + status`
  (see [[Debug - Slow Order Queries 2026-02]])

---
**Last updated:** 2026-03-15
**Related:** [[payment-service]] | [[inventory-service]] | [[notification-service]]
**Tags:** #system #commerce #core-service
```

---

### 04 Debugging Journal

**File:** `04 Debugging Journal/2026-03-10 - Memory leak in notification-service.md`
```markdown
# Memory Leak in notification-service

**Date:** 2026-03-10
**Severity:** P2 (service degraded, not down)
**Time to resolve:** 3 hours
**System:** [[notification-service]]

## Symptoms
- notification-service pods restarting every 2-3 hours (OOMKilled)
- Memory usage climbing linearly from deploy time
- No increase in traffic — same load, growing memory

## Investigation Timeline

### Dead End 1: Checked for obvious leaks (30 min)
- Reviewed recent PRs — nothing suspicious
- Checked connection pools — all properly configured with max limits
- Heap dump showed growing `ArrayList` instances in `TemplateCache`

### Dead End 2: Template caching (45 min)  
- Suspected template cache was growing unbounded
- Cache had a max size of 1000 — verified it wasn't exceeding
- BUT: the cache key included a timestamp → every request created 
  a new cache entry because the key was always unique
- Cache eviction was LRU, but at max 1000 entries × 50KB per 
  template = 50MB constant, not growing — so this wasn't the leak

### Root Cause Found (45 min)
- The REAL leak: Kafka consumer was creating a new `ObjectMapper` 
  per message for deserialization (instead of reusing a singleton)
- Each `ObjectMapper` registers type serializers that are never GC'd
- At 500 messages/min, this leaked ~200KB/min → OOM in ~2-3 hours
- **Line:** `NotificationEventConsumer.java:47`

## The Fix
```java
// BEFORE (leaked): new ObjectMapper created per message
public void onMessage(ConsumerRecord<String, String> record) {
    ObjectMapper mapper = new ObjectMapper();  // LEAK!
    NotificationEvent event = mapper.readValue(record.value(), NotificationEvent.class);
}

// AFTER (fixed): shared singleton ObjectMapper
private static final ObjectMapper MAPPER = new ObjectMapper();

public void onMessage(ConsumerRecord<String, String> record) {
    NotificationEvent event = MAPPER.readValue(record.value(), NotificationEvent.class);
}
```

## Root Cause
Object creation inside a hot loop (Kafka consumer) with objects that 
hold internal state (ObjectMapper caches type metadata). The GC couldn't 
reclaim the type metadata because the ObjectMapper's internal registry 
held strong references.

## Lesson / What I'll Check First Next Time
1. **Memory leak + Kafka consumer = check object creation in the consumer loop**
2. Always grep for `new ObjectMapper()` in hot paths — it's a common anti-pattern in Java
3. Heap dump → look at which class has growing instance count, not just total size
4. The first obvious suspect (template cache) was a red herring. Don't stop at the first plausible explanation — VERIFY with data.

## Prevention
- Added a Checkstyle rule: flag `new ObjectMapper()` anywhere except configuration classes
- Added memory usage alert at 70% threshold (not just OOMKill)

---
**Related:** [[notification-service]] | [[Kafka Consumer Groups]] | [[Java Memory Management]]
**Tags:** #debugging #memory-leak #java #kafka
```

---

### 05 Incident Log

**File:** `05 Incident Log/2026-01-22 - Duplicate Orders Incident.md`
```markdown
# Incident: Duplicate Orders

**Date:** 2026-01-22
**Duration:** 45 minutes (detection to resolution)
**Severity:** P1 — customers charged twice
**Systems affected:** [[order-service]], [[payment-service]]

## Timeline
- 14:15 — Alert: order creation rate 2x normal
- 14:20 — Customer complaints: charged twice for same order
- 14:25 — Root cause identified: API gateway retry + missing idempotency
- 14:30 — Mitigation: disabled gateway retry temporarily
- 14:45 — Fix deployed: idempotency check on order creation
- 15:00 — Refunds initiated for 47 affected customers

## Root Cause
API gateway was configured with automatic retry on 5xx errors. 
The order-service returned 503 on one pod restart. Gateway retried 
the request → second order created → second payment charged.

The order-service had no idempotency protection on the POST /orders 
endpoint. It treated every request as a new order.

## Impact
- 47 customers charged twice
- Total overcharge: ₹2.3L
- Customer trust impact: 12 support tickets, 3 social media complaints
- Refunds completed within 24 hours

## What We Changed
1. Added `Idempotency-Key` header requirement on POST /orders
2. Idempotency check: hash(userId + cartId + timestamp_rounded_to_minute)
3. Added duplicate detection alert (>1 order from same user within 60s)
4. Documented in [[order-service]] gotchas section

## Lessons
- **Every mutating API endpoint needs idempotency protection** — not optional
- Gateway retries + non-idempotent endpoints = guaranteed duplicates
- We got lucky it was only 47 orders. High traffic would have been catastrophic.
- Added this pattern to [[Idempotency Patterns]] in engineering knowledge

---
**Related:** [[order-service]] | [[payment-service]] | [[Idempotency Patterns]] | [[API Design Principles]]
**Tags:** #incident #p1 #idempotency #payments
```

---

### 06 Meeting Notes

**File:** `06 Meeting Notes/2026-03-14 - Architecture Review - Cache Strategy.md`
```markdown
# Architecture Review: Cache Strategy

**Date:** 2026-03-14
**Attendees:** Amit, Priya, Raj, me
**Duration:** 45 min

## Decisions Made
1. **Redis for hot data caching** (product catalog, user sessions)
   - TTL: 5 min for catalog, 30 min for sessions
   - Cache-aside pattern (not write-through — too complex for now)
   - See [[ADR-002 - Redis Cache Strategy]]

2. **CDN for static assets** — move to CloudFront
   - Raj to create spike ticket

3. **No caching for order data** — consistency > performance
   - Exception: order history (read-heavy, stale-ok) → cache with 2 min TTL

## Action Items
- [ ] Me: Write ADR for cache strategy → Due: 2026-03-18
- [ ] Raj: CloudFront spike → Due: 2026-03-21
- [ ] Priya: Implement cache-aside in product-service → Due: 2026-03-28

## Key Context
- Current p99 on product lookup: 450ms (target: <100ms)
- 80% of product reads are the same 500 products → perfect cache candidates
- Redis cluster already running for session storage — no new infra needed

---
**Tags:** #meeting #architecture #caching
```

---

### 07 1-on-1 Notes

**File:** `07 1-on-1 Notes/1-on-1 - Amit Kumar (Manager).md`
```markdown
# 1-on-1 Notes — Amit Kumar (Manager)

---

## 2026-03-14

**Topics discussed:**
- Performance review cycle starting in April — Amit said to prepare a 
  self-review doc highlighting top 3 contributions this quarter
- I asked about senior engineer promotion timeline — he said Q3 is 
  realistic if I demonstrate cross-team technical leadership
- Feedback: "Your debugging skills are strong. To get to senior, I need 
  to see you influencing architecture decisions, not just implementing them."

**Action items:**
- [ ] Me: Write self-review by April 1 → pull from [[12 Weekly Log/]]
- [ ] Me: Volunteer to lead the next architecture review
- [ ] Amit: Share the senior engineer rubric by next 1-on-1

**My takeaway:**
Gap to close: move from "strong executor" to "technical decision-maker." 
This means writing more ADRs, proposing solutions in architecture reviews, 
and mentoring at least one junior engineer.

---

## 2026-03-07

**Topics discussed:**
- Sprint velocity discussion — we overcommitted last sprint
- I raised concern about tech debt in notification-service
- Amit agreed to allocate 20% of next sprint to tech debt

**Action items:**
- [ ] Me: Prioritize top 3 tech debt items with effort estimates
- [x] Amit: Approve tech debt sprint allocation ✓

---

## 2026-02-28

**Topics discussed:**
- ...

---
**Tags:** #1-on-1 #career #feedback
```

---

### 08 Project Notes

**File:** `08 Project Notes/Project - Cache Layer Implementation.md`
```markdown
# Project: Cache Layer Implementation

**Status:** In Progress
**Started:** 2026-03-14
**Target completion:** 2026-04-15
**Team:** Me (lead), Priya, intern Varun
**Stakeholder:** Amit (engineering manager), Product — Sneha

## Goal
Reduce product catalog API p99 latency from 450ms to <100ms by 
implementing a Redis cache layer in [[product-service]].

## Scope
- ✅ In scope: product catalog caching, cache invalidation on product update
- ❌ Out of scope: order data caching, CDN (separate project)

## Key Decisions
1. Cache-aside pattern (not write-through) — [[ADR-002 - Redis Cache Strategy]]
2. TTL: 5 minutes — balances freshness vs. performance
3. Cache key: `product:{id}:v{version}` — versioned to prevent stale data on schema changes

## Architecture
```
[Client] → [API Gateway] → [product-service]
                                 ↓
                          [Check Redis cache]
                           ↓ hit    ↓ miss
                        [return]  [Query PostgreSQL]
                                     ↓
                               [Store in Redis]
                                     ↓
                                  [return]
```

## Risks
| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Cache stampede on TTL expiry | Medium | High (DB overwhelmed) | Implement cache lock / single-flight |
| Stale data served after product update | High | Medium | Invalidate on write + short TTL |
| Redis downtime | Low | Medium | Fallback to DB-direct (degrade gracefully, don't fail) |

## Progress Log
- 2026-03-14: Architecture review completed, ADR written
- 2026-03-15: Spike on cache-aside implementation started
- ...

## What I Learned (fill at project end)
[Retrospective notes — what went well, what was harder than expected, 
what I'd do differently]

---
**Related:** [[product-service]] | [[ADR-002 - Redis Cache Strategy]] | [[Redis]]
**Tags:** #project #active #caching #performance
```

---

### 09 Runbooks

**File:** `09 Runbooks/Runbook - Deploy order-service.md`
```markdown
# Runbook: Deploy order-service

**Last verified:** 2026-03-10
**Last updated by:** Me
**Estimated time:** 15 minutes

## Prerequisites
- [ ] PR merged to `main` branch
- [ ] CI pipeline passed (all tests green)
- [ ] Docker image built and pushed to ECR
- [ ] No active P1/P2 incidents on order-service

## Steps

### 1. Check Current State
```bash
# Verify current version running
kubectl get deployment order-service -n commerce -o jsonpath='{.spec.template.spec.containers[0].image}'

# Check pod health
kubectl get pods -n commerce -l app=order-service
```

### 2. Trigger Deployment
```bash
# ArgoCD sync (preferred)
argocd app sync order-service

# OR manual: update image tag in values.yaml and push
```

### 3. Monitor Canary
- Watch Grafana dashboard: "Order Service Health"
- Canary rollout: 10% traffic → wait 5 min → check error rate
- If error rate > 1%: ROLLBACK (see below)
- If healthy: promote to 50% → wait 5 min → promote to 100%

### 4. Verify Deployment
```bash
# Check new version is running
kubectl get pods -n commerce -l app=order-service -o wide

# Hit health endpoint
curl https://internal.api.company.com/order-service/actuator/health

# Check logs for startup errors
kubectl logs -n commerce -l app=order-service --tail=50
```

### 5. Post-Deploy Smoke Test
```bash
# Create test order (staging)
curl -X POST https://staging.api.company.com/api/v1/orders \
  -H "Content-Type: application/json" \
  -H "Idempotency-Key: deploy-test-$(date +%s)" \
  -d '{"userId": "test-user", "items": [{"productId": "test-1", "qty": 1}]}'
```

## Rollback
```bash
# Immediate rollback via ArgoCD
argocd app rollback order-service

# Verify rollback
kubectl rollout status deployment/order-service -n commerce
```

## Troubleshooting

| Symptom | Check | Action |
|---|---|---|
| Pods in CrashLoopBackOff | `kubectl logs` — look for connection errors | DB or Kafka might be down. Check dependencies. |
| High error rate after deploy | Grafana error rate panel | Rollback immediately, investigate after |
| Deployment stuck | ArgoCD UI — check sync status | `argocd app terminate-op order-service` and retry |

---
**Related:** [[order-service]] | [[Kubernetes Cheat Sheet]]
**Tags:** #runbook #deployment #order-service
```

---

### 10 People & Teams

**File:** `10 People & Teams/Raj Patel.md`
```markdown
# Raj Patel

**Role:** Staff Engineer, Platform Team
**Expertise:** Kafka, Kubernetes, CI/CD, infrastructure
**Communication style:** Prefers async (Slack > meetings). Responds fast 
to well-structured messages with context. Gets frustrated by vague requests.

## What to Go to Raj For
- Kafka configuration and operational issues
- Kubernetes debugging (pod scheduling, resource limits, networking)
- CI/CD pipeline changes
- Infrastructure architecture decisions

## What NOT to Bother Raj With
- Application-level bugs (he'll say "that's an app problem")
- Questions easily answered by documentation (he'll send you the link)

## How to Get the Best Response from Raj
- Message format: "Context: [1 line]. Problem: [1 line]. What I've tried: 
  [2-3 lines]. What I need: [specific ask]."
- Include logs, error messages, and what you've already checked
- Don't say "it's broken" — say "Kafka consumer lag is 50K messages on 
  topic X since 2pm, consumer group Y shows 3 active members but 
  expected 5"

## Notes
- Ran Kafka at scale at his previous company (1M msgs/sec)
- Prefers Confluent Cloud over self-managed Kafka
- Friday afternoons: usually does deep work, don't interrupt unless urgent
- Mentor to Varun (intern)

---
**Tags:** #people #platform-team #kafka #kubernetes
```

---

### 11 Code Review Learnings

**File:** `11 Code Review Learnings/Pattern - Fail Fast Validation.md`
```markdown
# Pattern: Fail Fast Validation

**Source:** Feedback from Amit on my PR #342

## The Pattern
Validate ALL input at the boundary (controller/handler level) BEFORE 
doing any business logic. Don't let invalid data travel deep into the 
system where errors become confusing.

## What I Did Wrong
```java
// BAD: Validation scattered throughout the service
public Order createOrder(OrderRequest request) {
    // ... 50 lines of business logic ...
    if (request.getItems().isEmpty()) {  // Too late!
        throw new ValidationException("Cart is empty");
    }
    // ... more logic that already partially executed ...
}
```

## What I Should Do
```java
// GOOD: All validation upfront, fail fast
public Order createOrder(OrderRequest request) {
    // Validate EVERYTHING first
    validate(request);  // throws if invalid
    
    // Only proceed if all validation passed
    return processOrder(request);
}

private void validate(OrderRequest request) {
    if (request.getItems().isEmpty()) 
        throw new ValidationException("Cart is empty");
    if (request.getUserId() == null) 
        throw new ValidationException("User ID required");
    if (request.getItems().stream().anyMatch(i -> i.getQuantity() <= 0))
        throw new ValidationException("Quantity must be positive");
}
```

## Why It Matters
- Errors are clear and specific (not buried in business logic exceptions)
- No partial state mutation from half-executed operations
- Easier to test — validation is one unit, logic is another
- Consistent error responses for the client

## Lesson
Every service method's first section should be validation. If it passes, 
the rest of the method can assume valid inputs. This eliminates an entire 
class of bugs.

---
**Related:** [[API Design Principles]] | [[Defensive Programming]]
**Tags:** #code-review #pattern #validation #java
```

---

### 12 Weekly Log

**File:** `12 Weekly Log/2026-W11 - Mar 10-14.md`
```markdown
# Week 11: March 10–14, 2026

## What I Shipped
- Fixed memory leak in notification-service (P2 → P0 fix)
  → See [[Debug - Memory leak in notification-service]]
- Wrote ADR for cache strategy → [[ADR-002 - Redis Cache Strategy]]
- Reviewed 4 PRs (Priya's order-status refactor was excellent)

## What I Learned
- ObjectMapper creation in hot loops = memory leak (Java)
  → Created note: [[Java Memory Management]] 
- Discriminated union types in TypeScript — much cleaner than optional fields
  → Created note: [[Discriminated Union Types]]
- Cache-aside vs write-through: trade-offs clearer now after architecture review

## Impact / Wins
- Memory leak fix saved ~3 pod restarts/day = improved notification reliability
- ADR writing → Amit mentioned this is the kind of senior-level contribution 
  he wants to see more of

## What Was Hard
- Debugging the memory leak — first suspect (template cache) was wrong. 
  Reminder: verify hypotheses with data, don't stop at first plausible answer
- Balancing sprint work with tech debt investigation

## Blockers / Concerns
- Cache implementation needs Redis cluster sizing — waiting on Raj's input
- Sprint velocity: 80% capacity but 100% commitment. Need to push back.

## Next Week
- [ ] Start cache-aside implementation in product-service
- [ ] Prepare for architecture review (present cache invalidation strategy)
- [ ] 1-on-1 with Amit: discuss senior engineer promotion timeline

---
**Tags:** #weekly-review
```

---

## 5. How to Write Engineering Notes That Actually Help

### The "Future Me at 2am" Test

Before saving any note, ask: **"If I'm paged at 2am in 6 months, will this note help me?"** If the answer is no, make it more specific.

Bad: "Fixed the caching issue"
Good: "Redis cache returns stale data because TTL resets on GET — solution: use GETEX with explicit TTL, or switch to cache-aside with fixed expiry"

### The Atomic Note Rule

One note = one concept. If you're writing about circuit breakers AND retries, make two notes and link them. Atomic notes are:
- Easier to find (the title IS the concept)
- Easier to link (other notes reference one specific idea)
- Easier to update (change one thing without touching unrelated content)

### Code Examples Are Non-Negotiable

For any technical concept, include a code example. Ideally from YOUR codebase — this anchors abstract concepts to concrete reality.

### The "Explain to a Junior" Standard

Write every note as if you're explaining it to a smart junior engineer. This:
- Forces you to truly understand (you can't explain what you don't understand)
- Makes the note useful for onboarding
- Creates a teaching resource you can share

---

## 6. Linking Strategy for Engineering

### Link Everything to Systems

Every debugging note, ADR, incident, and code review learning should link to the relevant system in `03 Systems & Services/`. This creates a complete picture per system.

### Link Patterns Across Systems

If you see the circuit breaker pattern in payment-service AND notification-service, both notes should link to `[[Circuit Breaker Pattern]]`. This reveals which patterns your team uses most.

### Map Links

| Note Type | Link To |
|---|---|
| Debugging Journal entry | System it affected + Engineering Knowledge concepts |
| ADR | Systems involved + related ADRs + Eng Knowledge patterns |
| Incident Log | Systems involved + Debugging notes + Runbooks |
| Code Review Learning | Engineering Knowledge concepts + System |
| 1-on-1 Note | Career goals, related feedback themes |
| Runbook | System + related incidents |

---

## 7. Tags Strategy

### System Tags
```
#order-service  #payment-service  #notification-service  
#product-service  #analytics-service  #api-gateway
```

### Category Tags
```
#design-pattern  #database  #performance  #security
#microservices  #resilience  #testing  #devops
#java  #typescript  #python  #sql  #kubernetes  #kafka  #redis
```

### Type Tags
```
#debugging  #adr  #incident  #runbook  #code-review
#meeting  #1-on-1  #project  #weekly-review
```

### Severity Tags (for incidents / bugs)
```
#p1  #p2  #p3
```

**Rule:** 2-3 tags per note. Don't over-tag. Links matter more than tags.

---

## 8. Templates Setup & Usage

### How to Set Up

1. Create `Templates/` folder in your Engineering vault
2. **Settings → Core Plugins → Templates** → Enable
3. Set "Template folder location" → `Templates`
4. Assign hotkey: `Alt+T` → "Insert template"

### Template List

```
Templates/
├── Engineering Concept.md
├── Architecture Decision Record.md
├── System Documentation.md
├── Debugging Journal Entry.md
├── Incident Post-Mortem.md
├── Meeting Note.md
├── 1-on-1 Note.md
├── Project Note.md
├── Runbook.md
├── Person Note.md
├── Code Review Learning.md
├── Weekly Engineering Review.md
```

---

## 9. Essential Plugins

### Day 1: Zero Plugins
Use Obsidian vanilla for 2-3 weeks. Learn the core.

### Week 3+: Tier 1

| Plugin | Why |
|---|---|
| **Calendar** | Click a date → open daily/weekly log |
| **Templater** | Auto-fill dates, create notes in correct folders |
| **Dataview** | Query your vault: "all open incidents," "all ADRs for order-service," "unprocessed inbox notes" |

**Useful Dataview queries for engineers:**

```dataview
// All debugging entries, most recent first
TABLE date as "Date", severity as "Severity"
FROM "04 Debugging Journal"
SORT date DESC
```

```dataview
// All ADRs for a specific service
TABLE status as "Status", date as "Date"
FROM "02 Architecture Decisions"
WHERE contains(file.outlinks, [[order-service]])
```

```dataview
// Inbox notes older than 3 days
LIST
FROM "00 Inbox"
WHERE file.cday < date(today) - dur(3 days)
```

```dataview
// All incidents by severity
TABLE date as "Date", duration as "Duration"
FROM "05 Incident Log"
SORT date DESC
```

### Month 2+: Tier 2

| Plugin | Why |
|---|---|
| **Excalidraw** | Draw architecture diagrams inline in your system notes |
| **Obsidian Git** | Auto-backup vault to a private Git repo |
| **Kanban** | Track project tasks visually |
| **Quick Add** | One-click note creation with pre-filled template + folder |

---

## 10. Daily Engineering Workflow

### Morning (3 min)
1. Open Engineering vault
2. Quick scan of `00 Inbox/` — anything urgent from yesterday?
3. Open today's Weekly Log entry — note today's planned focus

### During Work (capture as you go)
- **Solved a bug?** → Quick note in `00 Inbox/`: symptoms + fix (process later)
- **Made or heard a decision?** → Quick note: what was decided, by whom
- **Learned something from code review?** → Quick note: the pattern + why
- **Had a meaningful conversation?** → Quick note: who, what, key insight

**Capture takes 30 seconds. Processing happens later.**

### End of Day (5-10 min)
1. Process `00 Inbox/` — move notes to proper folders, rewrite into proper format
2. Update any system notes with new knowledge
3. Add links to new notes
4. If you debugged something non-trivial → write it up properly in Debugging Journal

---

## 11. Weekly Engineering Review

**Every Friday, 15-20 minutes:**

### Process Inbox (5 min)
- Everything in `00 Inbox/` gets processed or deleted
- Nothing carries over more than 1 week

### Write Weekly Log (10 min)
- What you shipped
- What you learned
- What was hard
- Impact and wins
- Next week's priorities

### Vault Maintenance (5 min)
- Open Graph View — any orphan notes?
- Any system notes that need updating?
- Any debugging entries that should link to engineering knowledge?
- Check `07 1-on-1 Notes/` — any follow-ups due?

---

## 12. Retention System — How to Actually Remember

Writing notes is step 1. REMEMBERING them is step 2. Here's how:

### 1. Active Recall During Writing
When you create a note, close the source material and write from memory first. Then check. This is retrieval practice (Section 2 of your Mastery System).

### 2. Link Aggressively
Every link is a retrieval cue. When you open `[[Circuit Breaker Pattern]]` from a debugging note, you're doing lightweight spaced repetition on that concept.

### 3. The "Before I Google" Rule
Before googling something, search your vault first (`Ctrl+Shift+F`). If you wrote about it, reading your OWN explanation reinforces the memory. If you can't find it, that's a signal to write it after you look it up.

### 4. Teach from Your Notes
When a colleague asks how something works, open the relevant note and explain from it. Teaching = the strongest form of retention.

### 5. Weekly Review = Spaced Repetition
Your Friday weekly log forces you to recall what you learned. This is a natural spaced repetition cycle.

### 6. The Feynman Bridge
For any complex concept, try explaining it WITHOUT opening the note. Grade yourself:
- **Nailed it:** You own this concept
- **Mostly:** Good — the note is working
- **Struggled:** Re-read the note, add better examples
- **No idea:** Rewrite the note from scratch — it wasn't clear enough

---

## 13. Becoming the Go-To Engineer

This vault system creates a compounding advantage. Here's how it makes you the person people rely on:

### Month 1: Foundation
- 20+ engineering knowledge notes
- 5+ debugging journal entries
- System documentation for your team's services
- People start noticing you remember things others don't

### Month 3: Reputation
- 60+ linked engineering notes
- 15+ debugging entries — you solve bugs faster because you've seen patterns before
- ADRs that other engineers reference in design discussions
- When someone asks "why did we build it this way?" — you pull up the ADR in 10 seconds

### Month 6: Authority
- 150+ interconnected notes
- Your system documentation is the team's onboarding resource
- Your debugging journal is a training resource for junior engineers
- You write the most useful ADRs on the team
- In architecture reviews, you reference past decisions and patterns fluently
- People come to you because you always seem to know the answer

### Month 12: The Go-To Person
- 300+ notes forming a dense knowledge graph
- You're the person who remembers every decision, every incident, every pattern
- Performance reviews are easy — your weekly logs are 52 weeks of documented impact
- You've contributed more to organizational knowledge than anyone
- New team members are told: "Ask [your name], they know everything about our systems"

### The Secret
You don't actually know more than your peers. You just CAPTURE and RETRIEVE better. The vault is an intellectual cheat code — it multiplies your effective memory by 10x.

---

## 14. Keyboard Shortcuts

| Shortcut | Action |
|---|---|
| `Ctrl+N` | New note |
| `Ctrl+O` | Quick open (search any note by name) |
| `Ctrl+P` | Command palette |
| `Ctrl+Shift+F` | Search across entire vault |
| `Ctrl+G` | Graph view |
| `Ctrl+E` | Toggle edit/preview |
| `[[` | Link to existing note |
| `Alt+T` | Insert template |
| `Ctrl+Click` | Open linked note |
| `Ctrl+,` | Settings |

---

## 15. Common Mistakes

### Mistake 1: Not Capturing During Debugging
You're 2 hours deep in a bug. You find the fix. You close the laptop. **WRONG.** Take 5 minutes to write it up. The debugging journal is only valuable if you feed it.

### Mistake 2: Copy-Pasting Stack Overflow Answers
**Wrong:** Copy the code snippet and close the tab.
**Right:** Write WHY it works in your own words. Link to the concept. The explanation sticks; the code snippet doesn't.

### Mistake 3: Treating This as Documentation for Others
This is YOUR vault. Write for yourself. If others benefit, great — but optimize for YOUR retrieval, not team-wide documentation standards.

### Mistake 4: Over-Documenting Meetings
Not every meeting deserves notes. Only capture meetings where DECISIONS were made or significant CONTEXT was shared. Skip standup notes — they have no long-term value.

### Mistake 5: Waiting for "Enough Time" to Write Properly
A rough note that exists beats a perfect note you never wrote. Capture now, refine later. The Inbox exists for exactly this reason.

### Mistake 6: Abandoning the System After Week 2
The vault compounds. Week 1 feels like overhead. Month 3 feels like a superpower. Push through the boring phase. (Same principle as compounding in your Mastery System.)

---

## 16. Day 1 Settings

### Settings to Change

| Setting | Location | Change To |
|---|---|---|
| Default location for new notes | Files & Links | `00 Inbox` |
| New link format | Files & Links | Shortest path when possible |
| Use Wikilinks | Files & Links | ON |
| Spell check | Editor | ON |
| Readable line length | Editor | ON |
| Confirm deletion | Files & Links | ON |

### Core Plugins to Enable

| Plugin | Why |
|---|---|
| **Backlinks** | Shows what links TO a note — essential |
| **Graph view** | Visual knowledge network |
| **Search** | Full-text search |
| **Templates** | Note templates → set folder to `Templates/` |
| **Quick switcher** | `Ctrl+O` to jump to any note instantly |
| **Outline** | Heading structure in sidebar |
| **Tags** | Tag search panel |

### Core Plugins to Disable

| Plugin | Why Off |
|---|---|
| Slides | Not needed |
| Publish | Not needed |
| Audio recorder | Not needed |

---

## Quick Start Checklist

```
☐ Created "Engineering" vault in cloud-synced folder
☐ Created all 13 folders (00 Inbox through Templates)
☐ Changed Day 1 settings
☐ Enabled/disabled core plugins
☐ Copied template files into Templates/ folder
☐ Copied this guide into vault root
☐ Created first note: document ONE system your team owns
☐ Created second note: write up the LAST bug you solved
☐ Linked both notes to each other (or to a concept)
☐ START. Capture something every work day. Process every Friday.
```

---

> **Remember:** The engineer who writes things down will always outperform the engineer who tries to remember everything. This vault is not extra work — it's a force multiplier. Every note you write today saves you 30 minutes six months from now. Start capturing. Start linking. Become the person who always has the answer.
