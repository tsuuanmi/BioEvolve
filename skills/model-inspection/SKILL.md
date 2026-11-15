---
name: model-inspection
description: Inspect biological neural network architectures and licensed checkpoints (CNN, GNN, Transformer) using weights plus activation/causal evidence. Use when a targeted model-improvement hypothesis requires mechanistic investigation.
---

# Model Inspection

## Inputs
Obtain an authorized pinned target or evidence reference, an explicit scientific question and the existing domain evaluator when required. Do not invent missing ground truth or permissions.

## Procedure
1. Check checkpoint hash/license, safe loading, model inputs, allowed data and domain evaluator.
2. Inventory architecture and parameters, then collect activation/feature probes and matched controls with upstream hooks/Captum/PyG/NNsight if supported.
3. For CNN inspect receptive fields/motifs; for GNN message passing/topology; for Transformers features/circuits. Weight magnitude alone is not a biological explanation.
4. Recommend minimal causal intervention(s) and record limitations in observation artifacts. Do not edit original weights or assert causality from attribution alone.

## Output
Return an evidence-linked artifact as proposed in [BioEvolve artifact contracts](../../docs/reference/artifacts.md) and report any blocker/uncertainty honestly. When evaluation is relevant, honor the [metric policy](../../docs/reference/metrics.md). Instructions are not proof of executed work.
