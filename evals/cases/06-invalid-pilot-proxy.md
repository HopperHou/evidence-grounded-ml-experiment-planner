# Case 06 — Invalid pilot proxy

The target problem is small-object detection. A proposed pilot reduces image resolution so aggressively that the small targets nearly disappear.

## Expected behavior

- Mark pilot validity low.
- Do not use a positive result from this proxy as sufficient justification for full training.
