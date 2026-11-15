---
name: bioevolve-evaluate
description: Compare pinned baseline and candidate bioinformatics tools or neural models with matched approved evaluators; measure regressions, performance, uncertainty and reproducibility.
---

# bioevolve-evaluate

## Required input
An authorized, pinned external target or artifact, relevant evidence, and a defined scientific question. Use only approved data and evaluator.

## Procedure
1. Check immutable baseline/candidate IDs and identical evaluator/data/conditions; fail closed on mismatch.
2. Invoke the target's authorized evaluator (DNA: reuse dna-eval); record genuine run logs and dataset digests.
3. Use development subset to filter, full development benchmark to rank, and holdout only with explicit approval.
4. Quantify gains, class regressions, uncertainty, latency, RAM, compute and compatibility. Separate engineering from scientific improvements.
5. Return evaluation artifact and hand off to bioevolve-feedback-loop. Never invent scores or self-approve.

## Output contract
Return structured, evidence-linked artifacts as specified in [BioEvolve contracts](../../docs/reference/artifacts.md). Include blockers and uncertainties explicitly; do not claim unexecuted work.
