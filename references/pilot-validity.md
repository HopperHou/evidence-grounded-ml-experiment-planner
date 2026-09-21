# Pilot Validity

A pilot is useful only if it preserves enough of the mechanism relevant to full training.

Before interpreting a pilot, assess:

- whether the same bottleneck exists in the pilot setting;
- whether the reduced dataset keeps the relevant class/data distribution;
- whether reduced resolution changes the phenomenon being tested;
- whether shorter training preserves the ranking of candidate methods;
- whether frozen components remove the mechanism of interest;
- whether optimization behavior is qualitatively comparable;
- whether the metric is stable enough at pilot scale.

## Examples of invalid proxies

- low-resolution pilot for a small-object method when the target objects disappear or change scale materially;
- frozen-backbone pilot for a method whose effect depends on representation learning;
- extremely short training when candidate methods have substantially different convergence speed.

## Decision

Label pilot validity as High / Medium / Low and explain why.

A positive low-validity pilot must not be treated as sufficient evidence for full training.
