# Result Audit

Audit existing evidence before proposing model changes.

## Comparability checklist

Check, when applicable:

### Training budget
- epochs;
- optimization steps;
- early stopping;
- learning-rate schedule;
- effective batch size;
- optimizer and weight decay.

### Data budget
- dataset version;
- train/validation/test split;
- added or removed data;
- augmentation;
- preprocessing;
- image resolution.

### Model/input budget
- parameter count;
- backbone;
- pretrained weights;
- initialization;
- feature resolution.

### Evaluation
- checkpoint-selection policy;
- confidence threshold;
- NMS/post-processing;
- test-time augmentation;
- metric implementation;
- per-class aggregation;
- calibration or threshold fitting.

### Search/tuning budget
- number of configurations tried for baseline;
- number tried for candidate;
- whether only the best run was reported;
- seed-selection behavior.

## Confounded comparison example

Baseline: 100 epochs, mAP50-95 0.412.
Candidate: 120 epochs, mAP50-95 0.419.

Observation: candidate is +0.007.

Conclusion that is not justified: architecture improved performance by +0.007.

Reason: training budget changed. A matched-budget comparison is needed before attributing the gain to architecture.

## Output

For each result mark:

- reliable;
- usable with caveat;
- confounded;
- invalid;
- missing required context.
