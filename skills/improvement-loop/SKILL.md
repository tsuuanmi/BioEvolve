---
name: improvement-loop
description: Coordinate a single bounded Scientific Improvement Loop in a bioinformatics tool or neural-model development repo: idea, hypothesis, frozen metrics, controlled test, evaluation and feedback. Use when an agent or System worker must improve an existing scientific function without introducing another scheduler.
---

# Scientific Improvement Loop

## Inputs
Obtain an authorized pinned target or evidence reference, an explicit scientific question and the existing domain evaluator when required. Do not invent missing ground truth or permissions.

## Procedure
1. Accept target URI/revision, goal/idea, authorization, existing evaluator, available baseline, experiment budget and stop rule. Read prior feedback before inventing a repeated idea.
2. Use `hypothesis-generation` for a falsifiable prediction. Use optional inspection/failure analysis only if evidence is missing.
3. Use `metric-design` to propose task-specific primary metric, safety gates, slices, confidence and resource limits. Require frozen/approved metric contract **before changing or scoring a candidate**.
4. Use `experiment-design` for the smallest isolated change. Hand execution to the target's existing agent/runner; do not spawn a parallel worker manager.
5. Use `experiment-evaluation` to compare pinned baseline/candidate under unchanged evaluator and matched budget. Reject incomparable or unsafe changes.
6. Use `feedback-loop` to record improved/regressed/neutral/inconclusive/failed/blocked and one next idea or stop.
7. Return artifacts and a bounded continuation proposal to System/operator. Do not loop indefinitely, auto-merge, consume holdout as feedback or change frozen metrics.

## Output
Return an evidence-linked artifact as proposed in [BioEvolve artifact contracts](../../docs/reference/artifacts.md) and report any blocker/uncertainty honestly. When evaluation is relevant, honor the [metric policy](../../docs/reference/metrics.md). Instructions are not proof of executed work.
