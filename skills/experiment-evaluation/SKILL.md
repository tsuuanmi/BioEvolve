---
name: experiment-evaluation
description: Evaluate a scientific software or biological-model candidate against a pinned baseline using approved frozen metrics, immutable evaluator and scientifically meaningful regression/safety gates. Use after any controlled SIL experiment.
---

# Experiment Evaluation

## Inputs
Obtain an authorized pinned target or evidence reference, an explicit scientific question and the existing domain evaluator when required. Do not invent missing ground truth or permissions.

## Procedure
1. Verify baseline/candidate revision, dataset digests, evaluator hash, hardware/budget, metric-contract freeze and provenance. Incomparable inputs → blocked.
2. Invoke target's actual evaluator (e.g. DNA `dna-eval`) under matched development conditions; capture logs, exit code, elapsed time and resource use. Crash/OOM/timeout → failed, never fake numeric zero score.
3. Compare primary metric and effect size, independent hard gates, per-class regressions and uncertainty; assess power for rare error groups.
4. Apply frozen keep/discard rules: hard-gate violation always regressed; improvement must exceed prespecified threshold; uncertain effect is inconclusive.
5. Return `evaluation` artifact and diagnostic evidence, not an independent scientific release approval. Handoff to `feedback-loop`; do not repeatedly peek at holdout.

## Output
Return an evidence-linked artifact as proposed in [BioEvolve artifact contracts](../../docs/reference/artifacts.md) and report any blocker/uncertainty honestly. When evaluation is relevant, honor the [metric policy](../../docs/reference/metrics.md). Instructions are not proof of executed work.
