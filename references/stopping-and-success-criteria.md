# Stopping and Success Criteria

## Predeclare success

Before running the experiment, define what counts as success using the user's chosen objective.

A criterion may include:

- minimum primary-metric improvement;
- maximum allowed regression in a secondary metric;
- compute or latency budget;
- subgroup/class constraint;
- replication requirement.

Do not redefine success after seeing the result.

## Regression handling

If an undeclared secondary metric or important subgroup regresses, warn the user clearly. Do not automatically reject the experiment unless a predeclared acceptance rule was violated.

## When to stop changing the model

It is valid to conclude that architecture/model changes are not currently justified when evidence indicates:

- baseline/evaluation cannot be trusted;
- data leakage;
- label noise or annotation problems dominate;
- inadequate or contaminated validation/test procedure;
- unresolved implementation bugs;
- repeated high-quality attempts yield no meaningful improvement;
- observed gains are below noise/uncertainty or not worth the compute cost;
- the main bottleneck lies outside the model architecture.

Explain the evidence behind the stopping decision.
