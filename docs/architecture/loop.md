---
status: draft
implements: [SRS-BE]
---

# Scientific Improvement Loop (target workflow)

1. **Select** authorized external target with pinned revision/checkpoint and evaluator.
2. **Inspect** source/algorithm or architecture/weights/activations, keeping raw evidence.
3. **Baseline** with original implementation, dataset digests and measured cost.
4. **Analyze** a reproducible error class, including data/annotation alternatives.
5. **Hypothesize** a falsifiable mechanism with predicted effects and controls.
6. **Intervene** in isolated branch or cloned checkpoint, minimal and reversible.
7. **Evaluate** fast development subset → full development panel → separately authorized holdout; measure regressions and total cost.
8. **Feedback** explicitly classify accepted-for-review, rejected, inconclusive, blocked or retriable. Store failures, evidence and next hypothesis.

This is a closed *scientific learning loop*, **not** an automatic merge loop. System owns agent lifecycle when integrated, and the target evaluator remains authoritative for domain metrics. Never tune repeatedly against an independent holdout. Scientific success is not equivalent to an increase in one global score.

**Example:** For DNA, reuse existing `dna-eval` ground truth, not a new evaluator or caller. OSIRIS has a different STR domain; CNN/GNN checkpoints require model-specific inspection and metrics.

The key efficiency objective is validated improvement per total research effort, not merely faster repeated tests.
