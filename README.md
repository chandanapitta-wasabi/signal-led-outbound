# Signal-Led Outbound — Claude Skill

A Claude skill that builds signal-triggered outbound sequences for B2B SaaS tools targeting founders at $1M–$10M ARR.

Most outbound fails not because the copy is bad — but because it's sent at the wrong moment. This skill teaches Claude to trigger sequences from buying signals, not static list pulls.

---

## Results

| Metric | Standard Clay Personalisation | Signal-Led |
|--------|-------------------------------|------------|
| Positive reply rate | 2–3% | 17% (top quartile) |
| Reply rate multiplier | 1x | 9x |
| Meetings booked | baseline | 3.4x more |

---

## What's inside

- **ICP definition** — who to target and who to disqualify
- **Signal tiers** — Tier 1 (act today), Tier 2 (this week), Tier 3 (opportunistic)
- **Clay workflow** — 5-step enrichment and sequencing logic
- **Claude personalisation prompt** — paste directly into your Clay table
- **Hard rules** — what never to do

---

## Stack

```
Clay → Claude → Attio → Instantly
```

- **Clay** — signal import, enrichment, personalisation via Claude column
- **Claude** — generates one signal-based personalisation line per lead
- **Attio** — CRM pipeline entry and signal logging
- **Instantly** — sequence delivery by tier

---

## How to use

1. Copy `SKILL.md` into your Claude skills folder
2. In Clay, reference the personalisation prompt from Section 5 in your Claude column
3. Map your signal source to the correct tier (Section 3)
4. Follow the workflow steps in order (Section 4)
5. Never skip the hard rules (Section 6)

---

## Who this is for

B2B SaaS founders and operators who are already running Clay outbound but stuck under 3% reply rates. This is not a beginner's guide to cold email — it assumes you have the stack and want to upgrade the logic.

---

Built by [Chandana](https://www.linkedin.com/in/chandana) · Feel free to use, adapt, and share.
