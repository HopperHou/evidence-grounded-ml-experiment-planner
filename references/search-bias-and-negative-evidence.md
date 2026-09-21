# Search Bias and Negative Evidence

Published literature overrepresents positive findings. Do not interpret many positive papers as a direct estimate of success probability.

Actively look for:

- contradictory studies;
- replication failures;
- methods that work only on one dataset;
- gains tied to a particular backbone;
- weak/unfair baselines;
- missing ablations;
- negative or null results;
- issue-tracker reports that implementation does not reproduce the paper;
- follow-up papers that narrow the original claim.

## Search-bias note

For each major candidate, state whether the available evidence appears one-sided because of publication or reporting bias.

## No hidden trial selection

All project experiments used to search for improvement must be recorded. Report total configurations tried and how many improved, were neutral, or regressed. Selection after a broad search should reduce confidence in an apparently exceptional winner unless it is independently replicated.
