# Sample run

Everything in this folder is made-up sample data. The companies and people are fictional. It exists to show the workflow and its stop rules, not real results.

- `sample-signals.csv`: seven leads as they would arrive from a signal source.
- `sample-output.csv`: what the workflow does with each one.

What to look at:

- Five leads pass every check and get a tier, a one-line personalisation and a sequence.
- Redfern Cloud is dropped at the ICP check, because its estimated ARR is above the $10M ceiling.
- Fieldstone AI stops at enrichment, because it has no signal detail. No signal means no sequence.
