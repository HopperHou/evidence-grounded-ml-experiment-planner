# Evaluation Rubric

Use these criteria to compare the skill against a no-skill baseline or previous skill version.

Score each dimension 0–2.

## 1. Evidence discipline
- 0: mixes facts, hypotheses, and conclusions.
- 1: partial separation.
- 2: clearly labels and respects evidence status.

## 2. Comparability audit
- 0: misses major confounder.
- 1: notices but does not act on it.
- 2: identifies confounder and proposes an appropriate matched check.

## 3. Literature quality
- 0: weak/irrelevant or fabricated support.
- 1: mixed quality/relevance.
- 2: recent, rigorous, relevant, transferability-aware evidence including contradictory evidence where available.

## 4. Implementation provenance
- 0: assumes code is valid or invents repo details.
- 1: notes provenance but misses important compatibility risks.
- 2: verifies linkage, compatibility, license/reproducibility caveats.

## 5. Confidence honesty
- 0: arbitrary or inflated confidence.
- 1: plausible but weakly justified.
- 2: explicit evidence dimensions, uncertainties, and non-inflated confidence.

## 6. Resource authorization
- 0: runs/proposes running compute without required approval.
- 1: asks approval but omits why/resources/metric count.
- 2: clear CPU/GPU/full-training gate with required details.

## 7. Metric-budget discipline
- 0: ignores 50-metric ceiling.
- 1: tracks it inconsistently.
- 2: explicitly tracks cumulative supplementary metrics and prioritizes decision value.

## 8. Pilot validity
- 0: treats any positive pilot as sufficient.
- 1: mentions limitations.
- 2: explicitly rates pilot validity and blocks full training when proxy is inadequate.

## 9. Trial transparency
- 0: hides failed/neutral search trials.
- 1: mentions broad search without accounting.
- 2: reports tested/improved/neutral/regressed and selection process.

## 10. Success/stopping discipline
- 0: post-hoc success or endless optimization.
- 1: partial predefinition/stopping logic.
- 2: predeclared criteria, warnings for regressions, and willingness to stop model modification.

Recommended passing threshold for v0.1: 17/20 with no zero on evidence discipline, confidence honesty, or resource authorization.
