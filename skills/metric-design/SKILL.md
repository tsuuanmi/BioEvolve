---
name: metric-design
description: Recommend scientifically valid evaluation criteria, primary objective, mandatory safety guardrails, diagnostics and budgets for a bioinformatics software or neural model experiment. Use before training, benchmarking or accepting a change in a Scientific Improvement Loop.
---

# Metric Design

## Inputs
Obtain an authorized pinned target or evidence reference, an explicit scientific question and the existing domain evaluator when required. Do not invent missing ground truth or permissions.

## Procedure
1. Identify scientific task, evaluation unit (base/locus/read/sample/batch/molecule/graph), dataset labels and asymmetry of error cost.
2. Propose **one primary metric** with direction and meaningful minimum effect, or explicit ranked/pareto objectives if one score is inappropriate. State numerator/denominator and metric computation method.
3. Propose **hard gates** based on domain policy (e.g. wrong auto-pass or missed allele must not increase beyond agreed threshold); never trade them for speed. Add slice-wise diagnostics, calibration/uncertainty and coverage/abstention metrics.
4. Add resource cost (wall time, memory, GPU/CPU-hours) and experimental budget, reproducibility hashes and matched-comparator requirements.
5. Require target owner/evaluator to approve and freeze metric definitions, thresholds, data partitions and evaluator version **before candidate results**. If missing trustworthy truth, return blocked/investigate.
6. Return `metric_contract` including metric rationale, limitations, scientific safety constraints and approval state. Read [metric policy](../../docs/reference/metrics.md). Handoff to `experiment-design`.

## Output
Return an evidence-linked artifact as proposed in [BioEvolve artifact contracts](../../docs/reference/artifacts.md) and report any blocker/uncertainty honestly. When evaluation is relevant, honor the [metric policy](../../docs/reference/metrics.md). Instructions are not proof of executed work.
