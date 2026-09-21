# Full Training

## Preconditions

Do not propose full training unless:

- the candidate has adequate evidence;
- a scientifically meaningful pilot was positive;
- pilot validity is adequate;
- success criteria are predeclared;
- the user explicitly approves full training.

## Resource request

Before launch, ask the user to specify or approve:

- GPU device;
- available VRAM;
- acceptable VRAM utilization or other resource cap.

Then propose:

- batch size;
- gradient accumulation;
- workers;
- precision;
- resolution;
- memory-saving settings;
- expected VRAM usage when estimable.

Do not maximize memory use for its own sake. Optimize for stable, reproducible training within the approved limit.

## Evaluation

Use the same evaluation protocol as the matched baseline.

Report:

- primary target metric;
- predefined secondary metrics;
- subgroup/class regressions;
- compute/training-cost changes;
- inference-cost changes where relevant;
- variance/replication evidence where relevant.
