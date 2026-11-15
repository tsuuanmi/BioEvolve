---
name: bioevolve-inspect-model
description: Inspect biological CNN, GNN or Transformer checkpoints, architecture, weights and activations and identify testable feature/mechanism hypotheses; use before model intervention or retraining.
---

# bioevolve-inspect-model

## Required input
An authorized, pinned external target or artifact, relevant evidence, and a defined scientific question. Use only approved data and evaluator.

## Procedure
1. Verify checkpoint digest, license, safe loading method, framework, architecture and evaluator.
2. Inventory layers/shapes/weights, but do not infer biological meaning from weight magnitude.
3. Probe activations with consented development data; reuse upstream hooks, Captum, NNsight or PyG where appropriate.
4. For CNN examine receptive fields/motifs; for GNN message passing/topology; for Transformer feature/attention circuits.
5. Add matched negative controls, distinguish correlation from causation and propose interventions without editing original weights.
6. Return target and observation artifacts, caveats and candidate failure classes. Stop if weight/data provenance unsafe.

## Output contract
Return structured, evidence-linked artifacts as specified in [BioEvolve contracts](../../docs/reference/artifacts.md). Include blockers and uncertainties explicitly; do not claim unexecuted work.
