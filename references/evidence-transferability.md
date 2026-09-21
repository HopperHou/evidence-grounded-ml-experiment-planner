# Evidence Transferability

Classify literature support before using it in confidence judgments.

## Level A — Direct evidence

Very close match in task, model family, modality/data characteristics, and metric. Example: a YOLO-family chest X-ray detector using a modification tested on comparable abnormality-detection data.

## Level B — Strong transferable evidence

Close match on task and mechanism with some domain difference, or close architecture match with a well-supported mechanism expected to transfer.

## Level C — Architecture-level evidence

Evidence from the same or closely related model family but a materially different task/domain.

## Level D — Mechanistic analogy

Evidence supports a mechanism in a related setting but transfer to the current task is uncertain.

## Level E — Weak analogy

Superficial similarity only. Do not use weak analogy as the primary basis for a high-confidence recommendation.

## Rule

Several Level C/D papers do not automatically equal one Level A paper. Quality and closeness matter, not just count.
