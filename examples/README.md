# Sample run

Everything in this folder is made-up sample data. The companies and people are fictional. It exists to show how the workflow works and where it stops. It contains no real results.

## Before the send

- `sample-signals.csv`: seven leads as they would arrive from a signal source, each with its source and a link to the evidence. The links are fictional.
- `sample-output.csv`: what the workflow does with each one.

What to look at:

- Five leads pass every check and get a tier, a one-line personalisation and a sequence.
- Redfern Cloud is dropped at the ICP check, because its estimated ARR is above the $10M ceiling.
- Fieldstone AI stops at enrichment, because it has no signal detail or source. No signal means no sequence.
- Northwind Metrics has two signals that tell one story: a Head of Marketing role and a founder post saying they still run sales.

## After the send

- `followup-schedule.csv`: the day, channel and angle for every touch, by tier.
- `followup-templates.md`: skeletons for the first email, the new-angle follow-up, the close and the LinkedIn touches.
- `sample-replies.csv`: seven fictional replies with the full email text, the label Claude would return, the extracted fields and the action taken.
- `reply-templates.md`: drafted responses for each label.
- `weekly-report-sample.md`: the weekly report built from the sample run. Rates are left uncalculated on purpose, because 8 sends is below the 100-send minimum.

What to look at in `sample-replies.csv`:

- Reply r5 is an out-of-office whose footer contains the word "unsubscribe". The auto-reply header is checked first, so it is labelled `auto_reply` and not `unsubscribe`.
- Reply r6 has confidence 0.55, below the 0.7 threshold, so it goes to a person.
- Reply r7 is a real unsubscribe, which is suppressed within the hour.
