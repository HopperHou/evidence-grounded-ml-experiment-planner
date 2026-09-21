# Experiment Planning

## Candidate evidence chain

Every candidate must identify:

1. target bottleneck;
2. project evidence;
3. relevant papers;
4. transferability level;
5. implementation source;
6. testable mechanism/hypothesis;
7. exact modification;
8. compute requirement;
9. success criterion;
10. failure interpretation;
11. rollback plan;
12. confidence assessment.

## Option A — Minimum-cost, highest-confidence

Choose the strongest directly supported experiment under tight resources:

- minimum necessary code change;
- minimum scientifically valid compute;
- low implementation risk;
- easy rollback;
- strong probability of improving the user-defined target.

Prefer CPU-only changes/analyses where they can genuinely improve or validate the target, but do not substitute an invalid CPU proxy for necessary training.

## Option B — Reasonable-resource, highest-confidence

Choose the strongest directly supported experiment under reasonable project resources:

- may use a more substantial but controlled modification;
- may require GPU pilot/training;
- should still have strong literature and project evidence;
- should remain reproducible and compatible with the current system.

## Tie-breaking

Performance-improvement likelihood is primary.

When two candidates have similar evidence-supported likelihood of improvement, prefer the one with higher information value: the result should more clearly confirm or falsify an important hypothesis.

## One major factor at a time

Prefer isolating one scientifically meaningful factor. Multiple coordinated changes are allowed only when the interaction itself is the hypothesis or a faithful implementation requires them together.
