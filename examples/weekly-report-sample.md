# Weekly report template

This report is built from the fictional sample run. Every number below is sample data, not a result.

## Counts

| Item | Count |
|---|---|
| Leads in | 7 |
| Dropped at the ICP check (ARR above the ceiling) | 1 |
| Stopped for no signal detail | 1 |
| Sequenced | 5 |
| Referral contact added | 1 |
| Emails sent | 8 |
| LinkedIn touches sent | 1 |
| Bounced | 0 |
| Replies (all labels) | 7 |
| Auto-replies (excluded from reply rate) | 1 |
| Real replies | 6 |
| Meetings requested | 1 |
| Suppressed | 1 |
| In the manual review queue | 1 |

## Replies by label

| Label | Count |
|---|---|
| auto_reply | 1 |
| not_interested | 1 |
| not_now | 1 |
| positive | 1 |
| referral | 1 |
| unclear | 1 |
| unsubscribe | 1 |

## Rates

Not calculated. This sample run has 8 sends, and the rule is that no segment is judged before 100 delivered sends. At that size a rate would be noise. The template for the real run:

| Metric | Formula | Value |
|---|---|---|
| Delivered rate | (sent minus bounced) / sent | n/a below 100 |
| Reply rate | replies excluding auto_reply / delivered | n/a below 100 |
| Positive reply rate | positive / delivered | n/a below 100 |
| Meetings per 100 delivered | meetings booked / delivered x 100 | n/a below 100 |

## Segments to review once the sample is large enough

- By signal type: hiring, funding, LinkedIn activity, tech stack.
- By tier and by touch number: which touch earned the reply.
- By angle or template version, one variable at a time.

## Decisions this report would drive

- Cut rule: under 0.5% positive reply rate after 200 delivered sends, drop a tier or pause the signal type.
- Scale rule: well above baseline after 100 or more sends, add volume.
- Manual review: relabel anything in the queue and add it to the classifier test set.
