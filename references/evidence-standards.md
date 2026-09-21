# Evidence Standards

## Evidence hierarchy

Prefer evidence in this order when making project-specific claims:

1. Direct measurements from the current project under controlled conditions.
2. Repeated controlled experiments or matched-budget ablations in the current project.
3. Reproducible implementation evidence from the current repository.
4. Closely matched peer-reviewed studies with compatible task, model, data, and metric.
5. Broader transferable peer-reviewed evidence.
6. Mechanistic reasoning grounded in verified model behavior.
7. Intuition or analogy.

Never present levels 6–7 as if they were levels 1–3.

## Claim discipline

For every important claim, classify it as one of:

- measured;
- reproduced;
- supported by literature;
- plausible but unverified;
- contradicted;
- unknown.

Use measured/reproduced evidence for strong conclusions. Use weaker wording for weaker evidence.

## Causality

A performance difference alone does not establish mechanism. A mechanism claim requires evidence that distinguishes it from plausible alternatives.

## Matched comparison

A clean comparison should keep relevant conditions matched, including as applicable:

- dataset and split;
- preprocessing and augmentation;
- resolution;
- pretrained initialization;
- training epochs/steps and schedule;
- effective batch size;
- optimizer;
- checkpoint-selection rule;
- evaluation code and thresholds;
- test-time procedures;
- tuning/search budget.

If these are not matched, treat causal attribution cautiously.

## Negative evidence

A controlled negative result reduces the plausibility of the tested hypothesis. Do not discard it merely because it is inconvenient.
