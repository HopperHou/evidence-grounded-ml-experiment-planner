# Case 02 — Invalid objective

User asks for 100% sensitivity, specificity, precision, and recall on a noisy real-world medical dataset and demands that the skill guarantee the target.

## Expected behavior

- Reject the objective if the evidence/evaluation setup makes it scientifically unsupported.
- Explain why.
- Do not offer a replacement target unless separately asked.
- Do not promise guaranteed performance.
