# Confidence Assessment

## Purpose

Estimate how strongly the available evidence supports the expectation that a proposed experiment will improve the user-defined target.

The reported percentage is an evidence-grounded research judgment unless the system has been explicitly calibrated against historical outcomes. Do not imply formal statistical calibration when none exists.

## Required dimensions

For every candidate report:

- **Estimated confidence of improvement: X%**
- **Evidence quality:** Low / Medium / High
- **Task similarity:** Low / Medium / High
- **Architecture similarity:** Low / Medium / High
- **Independent paper support:** count and quality summary
- **Official implementation:** Yes / No / Partial
- **Project-specific evidence:** Weak / Moderate / Strong
- **Pilot evidence:** None / Negative / Inconclusive / Positive
- **Implementation risk:** Low / Medium / High
- **Main uncertainty:** concise statement
- **Why confidence is X%:** explicit reasoning

## Inputs to judgment

Consider:

- directness and quality of literature evidence;
- consistency across independent papers;
- size and reliability of reported gains;
- quality of ablations;
- transferability level;
- current-project diagnostic evidence;
- matchedness of the current baseline;
- official-code availability and reproducibility;
- implementation surface area;
- contradictory/negative evidence;
- pilot evidence and pilot validity;
- hidden-selection/search effects;
- unresolved confounders.

## Calibration discipline

Try to find candidates that genuinely approach ~90% confidence when evidence supports them. Do not raise confidence merely because the user prefers high-confidence options.

If evidence supports 68%, report 68%.

If the evidence is too incomplete to make a meaningful numeric judgment, explicitly say that confidence cannot yet be responsibly quantified and identify the missing evidence.

## Very-high-confidence threshold

Confidence near or above 90% should normally require several of the following:

- strong direct project evidence for the targeted bottleneck;
- multiple independent, closely matched papers;
- consistent effects across relevant settings;
- a trustworthy compatible implementation;
- low implementation risk;
- little contradictory evidence;
- a positive, valid pilot on the current project.
