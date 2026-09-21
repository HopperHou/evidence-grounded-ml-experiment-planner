# Example — Chest Disease Detection

This example illustrates intended behavior; numbers are hypothetical and must never be reused as real evidence.

## Project

Task: detect/localize chest abnormalities.
Model: YOLO-family detector.
Primary metric: mAP50-95.
Observed issue: low recall for small lesions.

## Domain map

Relevant evidence may span:

- chest X-ray abnormality detection;
- YOLO-family object detection;
- medical object detection;
- small-object detection;
- multi-scale feature fusion;
- localization loss;
- class imbalance;
- medical-image augmentation.

## Critical-result logic

If aggregate mAP is known but per-size/per-class metrics are absent, the skill should not jump directly to adding an attention block.

It should first decide whether missing metrics such as small-object AP, per-class recall, lesion-size distribution, or confidence/IoU distributions are necessary. If so, it must explain the exact supplementary metrics, their decision value, the CPU/GPU cost, and ask for permission before collecting them.

## Literature logic

The evidence set should prioritize recent, rigorous papers directly addressing the task/problem, then use architecture-level YOLO evidence and mechanistic analogies with clearly lower transferability weight.

## Candidate logic

Option A should be the minimum-cost, strongest-evidence path.
Option B may use more reasonable compute for a potentially stronger gain.
Both must include transparent confidence breakdowns and predeclared success criteria.
