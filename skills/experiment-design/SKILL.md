---
name: experiment-design
description: Design a small reversible controlled code, algorithm or model change with fixed compute budget and prespecified success/falsification tests. Use after a hypothesis and frozen evaluation criteria exist.
---

# Experiment Design

## Inputs
Obtain an authorized pinned target or evidence reference, an explicit scientific question and the existing domain evaluator when required. Do not invent missing ground truth or permissions.

## Procedure
1. Require pinned hypothesis, approved/frozen metric contract, target baseline, evaluator/data identity and time/cost ceiling.
2. Select smallest isolated intervention; specify allowed mutable paths/checkpoint, controls, expected per-class effect, failure and timeout conditions.
3. Keep evaluator, metrics and ground truth read-only; do not modify target scientific truth for a candidate.
4. Return bounded experiment plan and artifact refs for existing implementation worker, not a new scheduler. Next step: `experiment-evaluation`.

## Output
Return an evidence-linked artifact as proposed in [BioEvolve artifact contracts](../../docs/reference/artifacts.md) and report any blocker/uncertainty honestly. When evaluation is relevant, honor the [metric policy](../../docs/reference/metrics.md). Instructions are not proof of executed work.
