---
status: draft
---

# Evaluation gates (target)

- **G0 Baseline:** unmodified reproducible run with code/checkpoint, data, environment and evaluator hashes.
- **G1 Mechanism:** reproduce a failure, specify a falsifiable explanation and negative controls; attribution alone is not causal proof.
- **G2 Development:** matched candidate/baseline evaluation with per-class gains and losses, uncertainty, performance and cost.
- **G3 Independent:** authorized locked holdout and distribution-shift checks; no repeated holdout tuning.
- **G4 Decision:** immutable artifacts, explicit accept-for-review/reject/investigate/blocked outcome and next hypothesis.

Reuse target scientific gates (e.g. DNA's `dna-eval`). Engineering optimization, biological accuracy, and interpretability accuracy are different outcomes. Do not automatically approve scientific changes or misrepresent clinical/forensic validity.
