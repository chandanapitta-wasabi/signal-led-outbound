---
name: signal-led-outbound
description: Signal-led outbound playbook for B2B SaaS. Use when building, reviewing, or running a Clay-to-Instantly outbound sequence, including signal selection, enrichment logic, Claude personalisation prompts, reply handling and CRM pipeline setup. Calibrated for SaaS tools targeting founders and operators at $1M to $10M ARR companies.
---

# Signal-Led Outbound

> 17% positive reply rate on about 4,000 delivered emails, across 1,000 target accounts

---

## 1. What this skill covers

End-to-end signal-led outbound for B2B SaaS: from signal source through Clay enrichment, Claude personalisation, CRM entry and Instantly delivery, then reply handling, follow-up logic, sending infrastructure, measurement, the CRM data model and failure modes (sections 7 to 12). Not a generic cold email playbook. Everything here is built around timing. The aim is to reach the right person when there is a reason to talk, not just when the list is ready.

This is a method, not a running system. It says what to check and what to do at each step. It does not connect to Clay, Attio or Instantly by itself.

---

## 2. ICP

- **Company type:** B2B SaaS, product-led or sales-assisted
- **ARR range:** $1M to $10M
- **Headcount:** 10 to 80
- **Buyer:** Founder still owning GTM, or first marketing hire without outbound infrastructure. Check who signs off. A first marketing hire may run the work while the founder owns the budget.
- **Disqualify if:** Enterprise sales motion, B2C, no outbound budget, or already running a mature SDR team

**Fit is not timing.** A company can match every line above and still have no reason to hear from you. ICP fit decides who you could contact. A signal decides whether you contact them now.

**When ARR is unknown.** Data tools often have no ARR figure. Use three outcomes:

- **Pass:** ARR is published or well supported, and inside the range.
- **Review:** no ARR figure, but headcount, funding and buyer all fit. A person decides.
- **Fail:** clearly outside the range. Drop it.

Never fill a missing ARR with a guess.

---

## 3. Signal tiers

A signal is something you can see: a job post, a raise, a LinkedIn post, a tool in the stack. What it means for the buyer is a guess until you check it. Each line below says what the signal suggests, not what it proves.

**Tier 1, act immediately**
- Hiring for Head of Marketing, VP Marketing, Growth Lead, or an SDR/BDR role. Suggests they are scaling GTM before the capability is in house.
- Series A or B announced in the last 90 days. Suggests growth targets and money to spend. It does not prove there is budget for what you sell.

**Tier 2, act within the week**
- 3+ GTM roles posted at once. Suggests a push on growth.
- Founder or CMO posting on LinkedIn about pipeline, outbound or AI growth. Suggests the problem is on their mind. Use what they said, not what you think they meant.

**Tier 3, opportunistic**
- BuiltWith shows HubSpot and no outbound tooling. Suggests a CRM with no pipeline engine. The tooling may just be hidden.
- A job description names Clay, Apollo or Instantly but no one owns them yet. Suggests they know the gap exists.

**Signals that stack.** Two or three signals that point to the same need make a stronger case than one. A Series A, three GTM roles and a founder post about pipeline tell one story. A stack is still not proof of budget, and signals that point to different needs do not stack.

**Record the evidence.** Log every signal with its source, a link, the date it was published and the date it was last checked. A signal you cannot link to does not go into a sequence.

---

## 4. Clay workflow, 5 steps

**Step 1. Signal import**
Pull from Apollo (job postings and funding announcements), LinkedIn (activity signals) and BuiltWith (tech stack). Capture the source link and the published date with each signal, not just the type. Run the ICP check from section 2 before enrichment. Do not enrich a lead that fails.

**Step 2. Enrichment**
Required fields before any message is generated: company name, ARR range (estimated, or marked unknown), tech stack, signal type, signal detail, signal source link, signal date, buyer name, buyer title and a verified work email.

| Missing | What happens |
|---|---|
| Signal detail | Stop. A vague signal produces a vague email. |
| Signal source link | Stop. An unchecked signal does not get a sequence. |
| ARR | Manual review, as in section 2 |
| Buyer | Keep researching. Never guess a contact. |
| Verified email | No email steps. Hold the lead or use LinkedIn only. |

**Step 3. Claude personalisation**
Generate one personalisation line per lead from the signal. Rules:
- Not a compliment
- Not a LinkedIn summary
- A specific observation that connects the signal to the problem this product solves
- Only facts from the lead's record. A guess about their situation is never written as fact.
- Max 1 sentence
- Written as if the sender already knows the context

Bad: "I love what you're building."
Good: "Posting a Growth Lead role while still owning pipeline yourself is a specific kind of pressure."

The good line only works when the record shows the founder still owns pipeline, for example from their own post. Without that fact, write about the role, not the founder.

**Step 4. CRM entry**
Log: contact, company, signal type, signal detail, signal source link, signal date, sequence assigned. Status: Outbound, Active. Check the suppression list and any active contacts at the same company first. Never push to CRM without the signal type logged.

**Step 5. Delivery**
Assign sequence by signal tier:
- Tier 1: 5 touches (3 emails and 2 LinkedIn touches)
- Tier 2: 3 emails
- Tier 3: 2 emails

Instantly sends the emails. The LinkedIn touches are separate tasks, sent by hand or through a LinkedIn tool, and logged against the same contact. Both channels count toward the same 5-touch cap, and a reply on either one stops both.

---

## 5. Personalisation prompt, paste into Claude

```
You are writing one personalisation line for a cold outbound email or LinkedIn message.

Signal: [insert signal type and detail]
Source: [where the signal was found, and the date]
Company: [company name]
Buyer: [first name], [title]
Product: [one-line description of what's being sold]

Rules:
- One sentence, max 20 words
- Open with the observation, not "I noticed" or "I saw"
- Connect the signal to the problem it usually points to
- Use only the facts above. Do not invent numbers, plans or problems
- Never state a guess about their situation as fact
- Do not name the product
- Do not compliment them
- British English
- If the signal is too thin to write a true line, return INSUFFICIENT SIGNAL
```

A lead that returns INSUFFICIENT SIGNAL goes to a person, who finds a better signal or drops the lead.

---

## 6. Hard rules

- No signal means no sequence. Full stop.
- No LinkedIn compliments as personalisation lines. They read as AI immediately.
- Never push to CRM before the signal type and source are logged.
- Never state a guess about the buyer's situation as fact.
- Email 1 is one problem, one proof, one ask. It is not a product pitch.
- Never exceed 5 total touches per contact across email and LinkedIn combined.
- Never invent ARR, funding, headcount or who owns what. Pull it from Apollo or leave it blank.
- Verify every email address before it enters a sequence.
- Never auto-send a reply to a positive or referral. A person approves it. Only an unsubscribe confirmation may send automatically.
- Add an unsubscribe to the global suppression list within the hour, across every campaign.
- Re-check any Tier 1 signal older than its window before the first touch. The default is 14 days for hiring signals (section 8.3).
- Auto-replies and bounces never count as replies in any metric.

---

## 7. After the send: reply handling

The loop is: send, reply arrives, classify, act, log, stop or continue. Replies are where most outbound workflows break, so every reply gets exactly one label, one action and one log entry.

### 7.1 Ingest

- **Source:** the Instantly reply webhook, or an inbox trigger (Gmail or Outlook) for threads that live outside Instantly.
- **Capture:** `message_id`, `thread_id`, lead email, `campaign_id`, step number, `received_at`, reply body.
- **Clean before classifying:** strip quoted history and the signature. Dedupe on `message_id`.
- **Match** the reply to the CRM contact by email, then by `thread_id`. If nothing matches, send it to the manual review queue. Never create a contact from an unmatched reply.

### 7.2 Classify

Seven labels: `positive`, `not_now`, `referral`, `not_interested`, `unsubscribe`, `auto_reply`, `unclear`.

Apply the rules in this order:

0. **Check headers first.** A delivery failure notice (from a mailer-daemon or postmaster address) is a bounce, not a reply. Do not classify it. Send it to bounce handling in 7.3. `Auto-Submitted: auto-replied` or `X-Autoreply` means `auto_reply`. This must run before anything else, because auto-reply footers often contain the word "unsubscribe".
1. Any unsubscribe language in the human-written text (stop, remove me, unsubscribe, do not contact) is `unsubscribe`, even if the same message says something else.
2. A reply that points you to another person is `referral`: it names someone and says they own this, introduces them, or forwards you on. Just mentioning a name is not enough.
3. A request for time, pricing, a call or more detail is `positive`. A meeting booked straight from the link counts as positive too (7.5).
4. A timing objection with a future date or period is `not_now`.
5. A clear no is `not_interested`.
6. Anything else, or any confidence below 0.7, is `unclear` and goes to a person.

Classification prompt for Claude. Return JSON only and validate it against the schema before acting on it:

```
You are classifying a reply to a cold outbound email.

Original email (first 3 lines): [first_lines]
Reply: [reply_body]

Return JSON only, matching this schema:
{
  "label": "positive | not_now | referral | not_interested | unsubscribe | auto_reply | unclear",
  "confidence": 0.0 to 1.0,
  "reason": "one sentence",
  "referral_name": string or null,
  "referral_email": string or null,
  "return_date": "YYYY-MM-DD" or null,
  "snooze_days": integer or null
}

Rules:
- Any request to stop contact is "unsubscribe", even if the reply also says something else.
- Out-of-office notices are "auto_reply". Include return_date if one is given.
- If you are unsure, use "unclear" and a confidence below 0.7.
- Do not write a reply. Do not guess names or dates that are not in the text.
```

Use the cheapest model that holds accuracy on your own labelled replies. Classification is a short, structured task, so test a small model first.

### 7.3 Actions by label

| Label | CRM stage after | Sequence | Next action | Target response time |
|---|---|---|---|---|
| `positive` | Meeting requested | Stop for this contact and pause the rest of the company | Draft a reply with the booking link. A person approves and sends. | 1 business hour |
| `not_now` | Nurture, snoozed | Stop | Set `snooze_until` to the stated date, or 75 days if none. Log the reason. | Same day |
| `referral` | Referred | Stop for the original contact | Create the new contact with signal type `referral` and `referred_by`. Enrol in the 2-email referral sequence. Thank the original contact. | Same day |
| `not_interested` | Closed, not interested | Stop all | Tag the reason: budget, in-house, timing, competitor or no need. Suppress for 12 months. | Same day |
| `unsubscribe` | Suppressed | Stop all for this contact | Add to the global suppression list within the hour. Send a one-line confirmation. Never re-add. This suppresses the person, not the company. | 1 hour |
| `auto_reply` | No change | Pause until `return_date` plus 1 business day, or resume the next step | Not counted as a reply | None |
| `unclear` | Review | Pause | A person reads it and relabels it | 1 business day |

**Bounces** are not a label. Mark the address invalid, stop email steps for that contact and never retry the same address. Keep the contact and company open, so you can find a correct address or switch to LinkedIn. A bounce does not pause anyone else at the company.

### 7.4 The approval gate

Claude classifies and drafts. A person approves every reply that goes to a `positive` or `referral`. These are the replies where tone and timing decide whether the meeting happens, and a wrong auto-reply costs more than a slow one. The only message that may send without approval is the unsubscribe confirmation.

### 7.5 Meeting booked

A calendar booking event (or a manual update) moves the contact to `Meeting booked`, stops every sequence for that company, writes `meeting_booked_at`, and copies `signal_type`, `tier` and `sequence_id` onto the meeting record. That copy is what makes attribution possible later.

---

## 8. Follow-up logic

### 8.1 Cadence by tier

Day 0 is the first send. The 5-touch cap from section 6 applies across email and LinkedIn together.

| Tier | Touch | Day | Channel | Angle |
|---|---|---|---|---|
| 1 | 1 | 0 | Email | The signal, the problem, one proof, one ask |
| 1 | 2 | 3 | LinkedIn | Connection request, no pitch |
| 1 | 3 | 6 | Email | A new angle: how a similar company handled it |
| 1 | 4 | 9 | LinkedIn | One short question about the problem |
| 1 | 5 | 13 | Email | A permission-based close |
| 2 | 1 | 0 | Email | The signal, the problem, one proof, one ask |
| 2 | 2 | 4 | Email | A new angle |
| 2 | 3 | 9 | Email | A permission-based close |
| 3 | 1 | 0 | Email | The signal, the problem, one proof, one ask |
| 3 | 2 | 6 | Email | A new angle and a smaller ask |

These day offsets are starting defaults. Change them against your own reply timing data.

### 8.2 Rules

- Every follow-up adds one new thing: a new observation, a new proof point or a smaller ask. "Just checking in" and "bumping this" are not allowed.
- A human reply stops the sequence. An `auto_reply` pauses it until the return date plus 1 business day. A bounce stops email to that address (7.3).
- No more than one touch per contact in any 3-day window, across channels.
- Send Tuesday to Thursday, 8:00 to 11:00 in the recipient's local time, as a starting window.
- If anyone at a company replies, pause every other contact at that company for 7 days. This stops two people at the same company receiving different follow-ups. A referred contact is the exception and gets their own sequence. An auto-reply or a bounce does not trigger the pause.
- Before any touch, check the company's other active contacts.

### 8.3 Signal re-check

A signal decays, and not at the same speed. A job post can close in two weeks, while a funding round stays relevant for months. 14 days is the default for hiring signals. Set the window by signal type. Before touch 1, re-check any Tier 1 signal older than its window. If the role has been filled or closed, drop the lead. Before touch 3, re-check that the signal still holds. If it changed (new funding, a new hire), regenerate the personalisation line from the new fact.

---

## 9. Sending infrastructure

All figures here are starting defaults. Adjust them against your own inbox placement tests.

- **Domains:** send from secondary domains, not the primary company domain. Two or three mailboxes per domain. This lowers the risk to your main domain. It does not guarantee inbox placement.
- **Authentication:** SPF, DKIM and DMARC on every sending domain. Use a custom tracking domain.
- **Warm-up:** warm each mailbox before sending cold email. Start at 20 or fewer new-contact emails per mailbox per day and ramp over several weeks. Cap steady-state sending at 30 to 40 a day per mailbox. Your email provider's own limits come first.
- **Content:** plain text, no images, one link at most. Turn open tracking off, because tracking pixels can hurt placement.
- **Verification:** verify every address before it enters a sequence. Aim for a bounce rate under 2%.
- **Circuit breakers:** pause a mailbox if its bounce rate passes 3% or spam complaints pass 0.1%. These are internal defaults, not provider rules.
- **Placement testing:** send to seed addresses on Gmail and Outlook before launching a campaign. Check inbox, promotions and spam placement. Test each recipient's mail provider (Google, Microsoft or a security gateway) because gateways such as Proofpoint, Mimecast and Barracuda can quarantine mail while your sending tool still reports it as delivered. For gateway-protected contacts, decide by hand whether LinkedIn or phone is the better channel.
- **Compliance:** before launch, check that your data sourcing, email outreach and LinkedIn activity follow the laws and platform rules where your prospects are.

---

## 10. Measurement

### 10.1 Definitions

| Metric | Formula |
|---|---|
| Delivered rate | (sent minus bounced) / sent |
| Reply rate | replies, excluding `auto_reply` / delivered |
| Positive reply rate | `positive` replies / delivered. Positive means a request for time, pricing, a call or more detail, or a meeting booked from the link. Report unique contacts separately if you count them |
| Positive share of replies | `positive` / all replies |
| Meetings per 100 delivered | meetings booked / delivered x 100 |
| Positive to meeting | meetings booked / `positive` replies |
| Meeting to qualified opportunity | qualified opportunities / meetings booked |
| Pipeline per 100 delivered | attributed pipeline value / delivered x 100 |
| Time to first touch | days from `signal_date` to the first send. Target for Tier 1: 2 days or less |
| Stop reasons | counts of leads dropped at the ICP check, stopped for no signal, and suppressed |

The last three rows need opportunity data in the CRM. Track them once you have it. Replies are not the goal. A segment with good replies and no qualified meetings is not working.

### 10.2 Segments

Cut every metric by signal type, tier, touch number (which touch got the reply), buyer title, ARR band and angle or template version. The aim is to find which signal type earns its keep, not to report one blended number.

### 10.3 Review cadence and decision rules

- **Weekly:** pipeline counts, bounce and complaint rates, reply labels, the manual review queue.
- **Monthly:** scale, hold or cut each segment.
- **Minimum sample:** do not judge a segment until it has at least 100 delivered sends. Below that, reply rates are noise. 100 is the first review point, not proof. Results above it are still directional.
- **Cut rule:** a signal type with under 0.5% positive reply rate after 200 delivered sends gets checked first: signal quality, ICP fit, contact data, delivery and the message. Then fix it, drop it a tier or pause it.
- **Scale rule:** a segment well above your baseline after 100 or more sends gets more volume.
- **One variable at a time:** test the angle, the subject or the ask separately, with at least 100 per arm.

### 10.4 Attribution

Because `signal_type`, `signal_date` and `tier` are written at CRM entry (section 4, step 4) and copied to the meeting record (section 7.5), every meeting traces back to the signal that caused it.

---

## 11. CRM data model

| Field | Purpose |
|---|---|
| `contact_id`, `company`, `buyer_name`, `buyer_title` | Identity |
| `signal_type`, `signal_detail`, `signal_date` | Why this lead, and when the signal fired |
| `signal_source`, `signal_source_url` | Where the signal came from, with a link to the evidence |
| `signal_checked_at` | The last time someone confirmed the signal still holds |
| `icp_fit`, `arr_range_estimated`, `headcount` | The ICP check and its inputs |
| `tier`, `sequence_id` | Which cadence applies |
| `personalisation_line` | The line used in touch 1 |
| `status`, `last_touch_at`, `touch_count` | Where the lead is in the sequence |
| `reply_label`, `reply_confidence`, `reply_at` | The classification result |
| `snooze_until`, `referred_by` | Handling for `not_now` and `referral` |
| `email_status` | Verified, invalid or unknown. Only verified addresses enter email steps |
| `suppressed`, `suppression_reason` | Do-not-contact flag for this person, and why: unsubscribe or not interested, with the date |
| `meeting_booked_at` | The outcome, used for attribution |

---

## 12. Failure modes

- **Stale signals.** A hiring signal from three weeks ago may already be filled. Re-check before the first touch.
- **The same angle in every touch.** If touch 3 says what touch 1 said, the lead hears one message three times.
- **Auto-replies counted as replies.** This inflates the reply rate and hides the real number. Filter on headers first.
- **"Unsubscribe" in a footer.** An out-of-office footer is not an opt-out. Header check comes before keyword matching.
- **Two contacts at one company.** Without the company-level pause, two people receive different follow-ups on the same day.
- **Judging too early.** A reply rate on 30 sends tells you nothing. Wait for the minimum sample.
- **A signal read as intent.** A raise or a job post is a fact. That they need what you sell is a guess. Check it before writing as if it is true.
- **Invented personalisation.** The line names a problem the record does not support. This is why the prompt can return INSUFFICIENT SIGNAL.
- **The wrong person.** The contact runs the work but does not own the decision. Check who signs off.
- **Bounces treated as auto-replies.** An out-of-office needs a pause. A bounce needs a new address.
- **Delivered is not inboxed.** Delivery means the server accepted the email. It says nothing about whether the person saw it.
