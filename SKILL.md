---
name: signal-led-outbound
description: Signal-led outbound playbook for B2B SaaS. Use when building, reviewing, or running a Clay-to-Instantly outbound sequence — including signal selection, enrichment logic, Claude personalisation prompts, and CRM pipeline setup. Calibrated for SaaS tools targeting founders and operators at $1M–$10M ARR companies.
---

# Signal-Led Outbound

> 9x higher reply rate vs standard Clay personalisation · 17% positive reply rate (top-quartile) · 3.4x more meetings booked vs problem-hook emails

---

## 1. What this skill covers

End-to-end signal-led outbound for B2B SaaS: from signal source through Clay enrichment, Claude personalisation, CRM entry, and Instantly delivery. Not a generic cold email playbook. Everything here is built around timing — reaching the right person when the problem is most acute, not just when the list is ready.

---

## 2. ICP

- **Company type:** B2B SaaS, product-led or sales-assisted
- **ARR range:** $1M–$10M
- **Headcount:** 10–80
- **Buyer:** Founder still owning GTM, or first marketing hire without outbound infrastructure
- **Disqualify if:** Enterprise sales motion, B2C, no outbound budget, or already running a mature SDR team

---

## 3. Signal tiers

**Tier 1 — act immediately**
→ Hiring for Head of Marketing, VP Marketing, Growth Lead, or SDR/BDR role → scaling GTM without in-house capability yet. Highest intent signal.
→ Series A or B funding announced in last 90 days → board pressure to grow, budget just unlocked

**Tier 2 — act within the week**
→ 3+ GTM roles posted simultaneously → growth mode, budget confirmed
→ Founder or CMO posting on LinkedIn about pipeline, outbound, or AI growth topics → already thinking about the problem

**Tier 3 — opportunistic**
→ Tech stack signal via BuiltWith: HubSpot + no outbound tooling → CRM exists, no pipeline engine
→ Job description mentions Clay, Apollo, or Instantly but no one owns it yet → they know the gap exists

---

## 4. Clay workflow — 5 steps

**Step 1 — Signal import**
Pull from Apollo (job postings + funding announcements), LinkedIn (activity signals), BuiltWith (tech stack). Filter to ICP before enrichment. Do not enrich leads that don't meet ARR range and buyer title criteria.

**Step 2 — Enrichment**
Required fields before any message is generated: company name, ARR range (estimated), tech stack, signal type, signal detail, buyer name, buyer title. If signal detail is missing → stop. A vague signal produces a vague email.

**Step 3 — Claude personalisation**
Generate one personalisation line per lead from the signal. Rules:
- Not a compliment
- Not a LinkedIn summary
- A specific observation that connects their situation to the problem this product solves
- Max 1 sentence
- Written as if the sender already knows the context

Bad: "I love what you're building."
Good: "Posting a Growth Lead role while still owning pipeline yourself is a specific kind of pressure."

**Step 4 — CRM entry**
Log: contact, company, signal type, signal date, sequence assigned. Status: Outbound — Active. Never push to CRM without signal type logged.

**Step 5 — Instantly delivery**
Assign sequence by signal tier:
- Tier 1 → 5-step sequence (3 email + 2 LinkedIn touchpoints)
- Tier 2 → 3-step email only
- Tier 3 → 2-step email only

---

## 5. Personalisation prompt — paste into Claude

```
You are writing one personalisation line for a cold outbound email or LinkedIn message.

Signal: [insert signal type and detail]
Company: [company name]
Buyer: [first name], [title]
Product: [one-line description of what's being sold]

Rules:
— One sentence, max 20 words
— Open with the observation, not "I noticed" or "I saw"
— Connect the signal to the pressure the buyer is feeling right now
— Do not name the product
— Do not compliment them
— British English
```

---

## 6. Hard rules

→ No signal = no sequence. Full stop.
→ No LinkedIn compliments as personalisation lines — reads as AI immediately
→ Never push to CRM before signal type is logged
→ Email 1 is one problem, one proof, one ask — not a product pitch
→ Never exceed 5 total touches per contact across email + LinkedIn combined
→ Never invent ARR, funding, or headcount data — pull from Apollo or leave blank
