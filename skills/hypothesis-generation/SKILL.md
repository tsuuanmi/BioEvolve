---
name: hypothesis-generation
description: Turn a bioinformatics improvement idea, known limitation, literature observation or error class into a falsifiable scientific/engineering hypothesis. Use at the start of the Scientific Improvement Loop, including before a failure is proven.
---

# Hypothesis Generation

## Inputs
Obtain an authorized pinned target or evidence reference, an explicit scientific question and the existing domain evaluator when required. Do not invent missing ground truth or permissions.

## Procedure
1. Accept an idea, target revision, goal, current evidence and prior negative experiments; do not presume every idea is already a proven bug.
2. State mechanism or specific improvement principle, plausible alternatives, predicted effect, affected data class and explicit falsification observation.
3. Request additional `tool-inspection`, `model-inspection` or `failure-analysis` only when needed. Rank hypotheses by expected scientific value, testability and bounded cost.
4. Return hypothesis artifact with evidence level, predicted primary metric direction and controls. Do **not** freeze metrics here; hand off to `metric-design`.

## Output
Return an evidence-linked artifact as proposed in [BioEvolve artifact contracts](../../docs/reference/artifacts.md) and report any blocker/uncertainty honestly. When evaluation is relevant, honor the [metric policy](../../docs/reference/metrics.md). Instructions are not proof of executed work.
