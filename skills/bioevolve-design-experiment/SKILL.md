---
name: bioevolve-design-experiment
description: Design falsifiable controlled experiments and reversible targeted interventions for tool or model failures with evaluator, budget, expected effect and stop conditions; use before modifying a target.
---

# bioevolve-design-experiment

## Required input
An authorized, pinned external target or artifact, relevant evidence, and a defined scientific question. Use only approved data and evaluator.

## Procedure
1. Accept one documented failure, baseline and agreed evaluator/compute budget.
2. Write causal hypothesis, alternatives, explicit falsification criterion, predicted metrics and negative controls.
3. Select smallest reversible change: repair/reuse before rewrite; probe/edit before expensive retraining when appropriate.
4. Predefine development/holdout policies, regression categories and stopping thresholds.
5. Return hypothesis and intervention plan to the target's existing worker, then bioevolve-evaluate.
6. Stop if interventions are unauthorized, destructive or scientifically untestable.

## Output contract
Return structured, evidence-linked artifacts as specified in [BioEvolve contracts](../../docs/reference/artifacts.md). Include blockers and uncertainties explicitly; do not claim unexecuted work.
