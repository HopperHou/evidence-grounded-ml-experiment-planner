# Project Understanding

Before literature search or experiment planning, establish:

- user-defined optimization target;
- task and output type;
- model family and major architecture components;
- modality and input representation;
- dataset(s), split strategy, and dataset size;
- primary and secondary metrics;
- current baseline and best-known configuration;
- compute environment;
- prior modifications already tested;
- known failure modes;
- deployment constraints if relevant.

## Dynamic field construction

Build a domain map from multiple dimensions rather than one label.

Example:

- task: chest disease detection;
- model: YOLO-family detector;
- modality: chest X-ray;
- objective: detection/localization;
- observed issue: poor small-lesion recall.

Possible search domains:

- object detection;
- medical object detection;
- chest X-ray abnormality detection;
- YOLO optimization;
- small-object detection;
- multi-scale feature fusion;
- localization loss;
- medical-image augmentation;
- class imbalance;
- label noise.

The final search scope may contain more than two domains.

## Objective validity

Reject the requested target when the evidence shows that it is scientifically invalid, contradictory, unsupported by the evaluation design, or not meaningfully addressable in the relevant field. Explain the reason for rejection. Do not automatically propose a substitute target.
