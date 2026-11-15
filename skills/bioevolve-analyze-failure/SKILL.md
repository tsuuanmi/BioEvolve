---
name: bioevolve-analyze-failure
description: Diagnose reproducible error classes in existing bioinformatics software or neural models from evaluator results and raw evidence; use after inspection to identify a narrow scientific improvement target.
---

# bioevolve-analyze-failure

## Required input
An authorized, pinned external target or artifact, relevant evidence, and a defined scientific question. Use only approved data and evaluator.

## Procedure
1. Verify pinned observation and baseline evaluator; reproduce one discrepancy on allowed data.
2. Stratify by biology and data context; investigate reference truth, annotation, preprocessing and distribution shift alongside algorithm/model failure.
3. Create minimal reproducer, raw evidence links and negative control; prioritize by significance and tractability.
4. Return failure artifact with baseline/dataset digests, class, reproducibility and uncertainty.
5. Hand off to bioevolve-design-experiment. If truth is weak, return investigate, not fabricated labels.

## Output contract
Return structured, evidence-linked artifacts as specified in [BioEvolve contracts](../../docs/reference/artifacts.md). Include blockers and uncertainties explicitly; do not claim unexecuted work.
