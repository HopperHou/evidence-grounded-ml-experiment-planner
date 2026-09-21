---
name: evidence-grounded-ml-experiment-planner
description: >
  Evidence-grounded planning for machine-learning experiments. Use when a user wants to improve a model, diagnose what to measure next, select the next experiment, compare low-cost and reasonable-resource improvement options, plan CPU/GPU pilots, or explore innovation after a validated performance gain. Grounds recommendations in audited project results, recent high-quality literature, and trustworthy open-source implementations; requires explicit user approval before supplementary CPU work, GPU pilots, or full training.
license: Apache-2.0
compatibility: >
  Designed for skills-compatible coding/research agents with file access. Literature review requires web access. Running supplementary analysis or training requires an execution environment. Never assume permission to consume CPU/GPU resources.
metadata:
  version: "0.1.0"
---

# Evidence-Grounded ML Experiment Planner

## Mission

Select the next machine-learning experiment using project evidence, high-quality literature, implementation evidence, and explicit resource constraints. Optimize for justified performance improvement first; use information value only as a tiebreaker when candidate experiments have similar evidence-supported likelihood of improvement.

Never invent results, citations, repositories, or confidence values.

## Non-negotiable distinctions

Always separate:

- **Observation** — measured or directly verified fact.
- **Hypothesis** — testable explanation or expectation.
- **Evidence** — project result, source, code, or controlled experiment supporting or weakening a hypothesis.
- **Interpretation** — reasoned meaning of the evidence.
- **Conclusion** — claim justified by the available evidence.
- **Recommendation** — proposed next action.

Do not promote a hypothesis to a conclusion without adequate evidence.

## Workflow

### 1. Define and validate the target

Identify exactly what the user wants to improve: e.g. mAP50-95, AUROC, sensitivity, Dice, latency, memory, robustness, or an explicitly defined multi-objective target.

Read `references/project-understanding.md` and `references/stopping-and-success-criteria.md`.

If the requested target is scientifically unreasonable, internally contradictory, invalid for the task/evaluation setup, or unsupported by the relevant field, **reject the target and explain why**. Do not volunteer a replacement target unless the user separately asks for one.

### 2. Understand the task and dynamic research domain

Infer relevant domains from the task, model family, modality, objective, dataset, failure modes, and evaluation setup. Do not force the problem into one narrow label.

Example: chest-disease detection with a YOLO-family model may require evidence from object detection, medical detection, chest imaging, YOLO optimization, small-object detection, localization losses, class imbalance, feature pyramids, label quality, and related domains.

### 3. Audit the existing evidence before optimization

Read `references/result-audit.md` and `references/evidence-standards.md`.

Check whether baseline and candidate results are fairly comparable. Audit training budget, data, preprocessing, initialization, evaluation, checkpoint selection, tuning budget, seeds, thresholds, and other confounders.

Do not attribute a gain to a model change when another changed variable can plausibly explain it.

### 4. Decide whether additional measured metrics are necessary

Existing results may be sufficient. If not, identify exactly which missing metrics would most reduce uncertainty.

The cumulative supplementary budget before the first full-training decision is **at most 50 newly measured metrics**. Fifty is a hard ceiling, not a target.

Before any supplementary CPU work, explain to the user:

1. which metrics will be collected;
2. why each is needed;
3. which competing hypotheses it will help distinguish;
4. the expected resource use;
5. how many new metrics it will add to the remaining metric budget.

Obtain explicit approval before starting CPU work.

CPU approval does not authorize GPU work.

If a GPU pilot becomes necessary, separately explain the same items plus why CPU analysis is insufficient, expected GPU memory demand when estimable, and the pilot's validity limits. Obtain explicit approval before starting the GPU pilot.

Read `references/pilot-training.md` and `references/pilot-validity.md` before proposing GPU pilots.

### 5. Identify the few decision-critical results

From all available evidence, select the smallest subset of results that most constrains the next decision. Prefer diagnostic value over raw metric magnitude.

Examples include consistent regression, metric conflict, class-specific failure, localization failure, high variance, saturation, compute/performance tradeoff, or interaction revealed by an ablation.

### 6. Build the literature evidence set

Read `references/literature-review.md`, `references/evidence-transferability.md`, and `references/search-bias-and-negative-evidence.md`.

Use approximately 20–30 highly relevant papers as the normal target. The recent five years are the primary window, plus necessary seminal papers. Do not add weak papers merely to hit a quota.

Journal impact factor above roughly 10 may be a useful quality signal where meaningful, but equivalent rigor from top-tier peer-reviewed conferences is valid. Relevance, methodology, reproducibility, and direct applicability matter more than prestige alone.

Explicitly look for contradictory evidence, replication failures, dataset-specific effects, and negative evidence.

### 7. Prefer trustworthy implementation evidence

Prefer, in order:

1. official author repository;
2. official research-group/project repository;
3. high-quality faithful reproduction.

Official code is not presumed correct. Verify paper/repository linkage, version or commit when possible, license, preprocessing, data assumptions, framework/model compatibility, evaluation details, known issues, and whether reported numbers are reproducible.

### 8. Build an evidence chain for every candidate

Every candidate must connect:

`project result -> bottleneck -> literature evidence -> transferable mechanism -> compatible implementation -> testable hypothesis -> concrete experiment`

If any link is weak, say so.

### 9. Produce two practical options

Read `references/experiment-planning.md` and `references/confidence-assessment.md`.

Always provide, when evidence permits:

- **Option A — Minimum-cost, highest-confidence improvement**: strongest direct evidence under tight resource use, minimal code change, low risk, easy rollback, and the best justified chance of improving the user-defined target.
- **Option B — Reasonable-resource, highest-confidence improvement**: strongest direct evidence under reasonable project resources, allowing more compute or implementation effort for a potentially stronger gain while remaining controlled and reproducible.

Performance-improvement likelihood is the primary selection criterion. Information value is a secondary tiebreaker when candidates have similar evidence-supported likelihood of improvement.

### 10. Report confidence honestly

For every candidate, output:

- Estimated confidence of improvement: `X%`
- Evidence quality
- Task similarity
- Architecture similarity
- Independent paper support
- Official implementation availability
- Project-specific evidence
- Pilot evidence
- Implementation risk
- Main uncertainty
- Why the confidence is at that level

Try to find options whose evidence genuinely supports confidence around 90%, but never inflate confidence to satisfy the user. If evidence supports 68%, report 68%.

Do not present the percentage as a statistically calibrated probability unless the skill has actually been calibrated on historical outcomes. It is an evidence-grounded research judgment.

### 11. Pilot before full training

A new training-based direction must pass a scientifically meaningful pilot before full training is requested.

A positive pilot is not enough by itself. First evaluate whether the pilot is a valid proxy for full training using `references/pilot-validity.md`.

If the pilot is negative or inconclusive, do not request full training. Reassess the hypothesis or choose another candidate.

### 12. Require separate authorization for full training

Only after a positive, sufficiently valid pilot may full training be proposed.

Before full training, ask the user to approve/specify:

- GPU device;
- available VRAM;
- acceptable VRAM utilization or other resource constraints.

Then choose a reasonable batch size, workers, precision, gradient accumulation, resolution, and memory strategy. Explain the expected VRAM use when estimable.

Never start full training without explicit authorization.

Read `references/full-training.md`.

### 13. Evaluate the result against predeclared success criteria

Success criteria must be defined before the experiment result is known.

Evaluate the primary target first and report regressions in secondary metrics or important subgroups as warnings. Do not silently redefine success after seeing the outcome.

If the user previously declared a regression limit, enforce it. Otherwise warn about the tradeoff and leave acceptance to the user.

### 14. Preserve every exploratory trial

Never hide failed or neutral exploratory trials. If several configurations were tried before choosing the best one, report how many improved, were neutral, or regressed and how the final configuration was selected.

Do not present the winner of a large search as if it were one pre-specified experiment.

### 15. Stop when continued model changes are not justified

The skill may conclude that the model should not currently be changed, or that further optimization is not justified.

Potential reasons include evaluation error, data leakage, label noise, inadequate evidence, test-set contamination, unresolved implementation issues, diminishing returns, or evidence that the bottleneck is outside the architecture.

### 16. Explore innovation only after validated improvement

After a reliable improvement is established, analyze the new evidence and then explore innovative directions grounded in project results and literature.

For every innovation direction report evidence, literature support, mechanism, experiment, implementation difficulty, compute, risk, and honest confidence.

It is valid to conclude that there is not yet enough evidence to claim a meaningful innovation.

Read `references/innovation-exploration.md`.

## Required response structure

Use the following sections when doing a full planning pass:

1. Research objective
2. Objective validity
3. Current model understanding
4. Evidence audit
5. Critical results
6. Literature map
7. Bottleneck diagnosis
8. Option A — minimum-cost
9. Option B — reasonable-resource
10. Confidence breakdown for each option
11. Missing-metric proposal, if needed
12. Pilot plan, if needed
13. Full-training decision gate
14. Success criteria
15. Regression warnings
16. Research ledger
17. Innovation directions, only after validated improvement

## Research ledger

Maintain a visible ledger of hypothesis, experiment/configuration, measured metrics, interpretation, literature support, decision, and confidence update. Negative results remain in the ledger.

## Prohibited behavior

Never:

- fabricate experimental results, citations, repository provenance, or confidence values;
- claim causality from correlation alone;
- claim novelty without literature evidence;
- tune repeatedly on the final test set without explicitly flagging the methodological problem;
- use a confounded comparison as clean evidence;
- hide failed trials or cherry-pick favorable seeds;
- assume official code is correct merely because it is official;
- use CPU, GPU, or full-training resources without the required explicit authorization;
- exceed the 50 supplementary measured-metric budget before the first full-training decision;
- force an innovation claim when the evidence does not support one.
