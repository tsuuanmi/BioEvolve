---
name: feedback-loop
description: Close a Scientific Improvement Loop experiment by keeping or rejecting a candidate, interpreting failures, preserving negative findings and producing a bounded next hypothesis. Use after a benchmark, timeout, scientific regression or inconclusive result.
---

# Feedback Loop

## Inputs
Obtain an authorized pinned target or evidence reference, an explicit scientific question and the existing domain evaluator when required. Do not invent missing ground truth or permissions.

## Procedure
1. Load frozen hypothesis, metric contract, experiment and evaluation artifacts; check integrity and predicted effects.
2. Classify improved, regressed, neutral, inconclusive, failed or blocked. Hard science gates veto an otherwise attractive metric gain.
3. Compare specific failure classes, unexpected errors, mechanism evidence, uncertainty and compute cost. Do not silently adjust the frozen objective.
4. Keep development incumbent only when permitted; discard candidate without deleting experiment evidence. Persist successful and negative attempts with causes.
5. Generate one next idea with expected information gain or stop because of budget, repeated failure, uncertainty or safety. Emit `feedback` artifact and return bounded continuation to caller. No unbounded scheduling or self-approval.

## Output
Return an evidence-linked artifact as proposed in [BioEvolve artifact contracts](../../docs/reference/artifacts.md) and report any blocker/uncertainty honestly. When evaluation is relevant, honor the [metric policy](../../docs/reference/metrics.md). Instructions are not proof of executed work.
