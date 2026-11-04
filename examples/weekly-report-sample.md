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

Rates are calculated for reporting purposes, but samples below the review threshold should not be treated as evidence of segment performance. This sample run has 8 delivered emails, well under the 100-send review threshold.

| Metric | Formula | Observed result | Interpretation |
|---|---|---|---|
| Delivered emails | sent minus bounced | 8 | Very small sample |
| Delivered rate | (sent minus bounced) / sent | 100% | Descriptive only |
| Reply rate | replies excluding auto_reply / delivered | 75% (6 of 8) | Descriptive only |
| Positive replies | count of `positive` | 1 | Observed result |
| Positive response rate | positive / delivered | 12.5% (1 of 8) | Descriptive only |
| Meetings requested | count | 1 | Requires further validation |
| Qualified opportunities | count | 0 | No qualified opportunities yet |

Every figure here comes from the fictional sample data.

## Segments to review once the sample is large enough

- By signal type: hiring, funding, LinkedIn activity, tech stack.
- By tier and by touch number: which touch earned the reply.
- By angle or template version, one variable at a time.

## Decisions this report would drive

- Cut rule: under 0.5% positive reply rate after 200 delivered sends, check signal quality, ICP fit, contact data, delivery and the message first. Then fix it, drop a tier or pause the signal type.
- Scale rule: segments showing consistently stronger performance across sufficiently sized, comparable cohorts can receive more volume. Check signal quality, ICP fit, delivery performance and qualified-opportunity conversion first.
- Manual review: relabel anything in the queue and add it to the classifier test set.
