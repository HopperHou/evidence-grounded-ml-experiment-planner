# evidence-grounded-ml-experiment-planner

An open Agent Skill for evidence-grounded machine-learning experiment planning.

Its goal is not to generate fashionable model ideas. It is to help an agent decide **what experiment should be run next** using audited project results, high-quality recent literature, trustworthy implementation evidence, controlled pilots, and explicit user-controlled compute authorization.

## Design principles

- Evidence before intuition.
- Observation is not explanation.
- Baselines must be comparable.
- Recent literature first, seminal work when necessary.
- Approximately 20–30 strong papers, not a quota of weak papers.
- Direct evidence is stronger than architectural analogy.
- Official code is preferred but still audited.
- Confidence must be explained and honest.
- Aim for high-confidence recommendations when evidence supports them; never inflate to reach ~90%.
- Supplementary CPU work, GPU pilots, and full training each require explicit user authorization.
- At most 50 newly measured supplementary metrics before the first full-training decision.
- Pilot training must precede full training and the pilot itself must be a valid proxy.
- Failed/neutral trials remain visible.
- Success criteria are defined before results are known.
- The skill may conclude that the model should not currently be changed.
- Innovation is explored only after a validated improvement.

## Repository layout

```text
evidence-grounded-ml-experiment-planner/
├── SKILL.md
├── README.md
├── LICENSE
├── CHANGELOG.md
├── references/
│   ├── evidence-standards.md
│   ├── project-understanding.md
│   ├── result-audit.md
│   ├── literature-review.md
│   ├── evidence-transferability.md
│   ├── search-bias-and-negative-evidence.md
│   ├── confidence-assessment.md
│   ├── experiment-planning.md
│   ├── pilot-validity.md
│   ├── pilot-training.md
│   ├── full-training.md
│   ├── stopping-and-success-criteria.md
│   └── innovation-exploration.md
├── evals/
│   ├── rubric.md
│   └── cases/
└── examples/
    └── chest-disease-detection.md
```

## Installation into a project

After development/evaluation, copy or clone the folder into a skills-compatible project's skill location. For Codex-style project-local usage this is typically:

```text
<project-root>/.agents/skills/evidence-grounded-ml-experiment-planner/
```

Keep development and production copies versioned so you can reproduce which skill version influenced an experiment decision.

## Validation

The Agent Skills specification supports validating a skill with:

```bash
skills-ref validate ./evidence-grounded-ml-experiment-planner
```

## Current status

`v0.1.0` is an initial methodology and evaluation release. It should be treated as **unvalidated until tested against adversarial cases and historical ML experiments**.

The skill does not claim that using it will improve model performance. Its aim is to improve the rigor, traceability, and evidence quality of experiment selection.

## License

Apache-2.0.
