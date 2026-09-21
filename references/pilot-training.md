# Pilot Training and Supplementary Measurement

## Authorization gate

Before any supplementary CPU experiment or analysis that consumes project compute, tell the user:

- exact measurements to collect;
- why they are needed;
- competing hypotheses they distinguish;
- expected resource demand;
- number of new measured metrics added to the 50-metric budget.

Wait for explicit approval.

If GPU becomes necessary, make a new request. CPU authorization never implies GPU authorization.

## GPU pilot proposal

Before GPU pilot, include:

- exact pilot configuration;
- scientific question;
- why CPU cannot answer it;
- expected GPU and VRAM demand when estimable;
- expected number of new metrics;
- validity limitations;
- predeclared positive/inconclusive/negative criteria.

Wait for explicit approval.

## Metric budget

Track cumulative supplementary measured metrics before the first full-training decision.

A metric is one newly measured quantitative output used for decision-making. Examples: mAP50-95, recall, per-class AP, latency, calibration error, graph degree statistic.

Multiple metrics from one run each count toward the budget if they are newly collected for the supplementary evidence process.

Hard ceiling: 50.

Do not collect metrics merely because they are easy to obtain. Prefer those with the highest decision value.
