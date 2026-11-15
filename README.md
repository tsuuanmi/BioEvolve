# BioEvolve

**Inspectable scientific improvement workflows for existing bioinformatics tools and neural networks.**

BioEvolve is a portable **skill-first** toolkit, not a paper, variant caller, model-training framework, or another agent orchestrator.

**Loop:** Target → Inspect → Baseline → Analyze failure → Hypothesize → Intervene → Evaluate → Feedback.

**Software track:** inspect source, algorithms, intermediate evidence and recurring errors; reuse, patch or rewrite only when justified.

**Model track:** inspect architecture, weights, activations and causal mechanisms of CNNs, GNNs, Transformers and other biological models; test targeted changes before costly retraining.

**System integration:** System (when used) owns Work/Attempt, workers, scheduling, retries and verification; BioEvolve supplies skills/workflows and scientific experiment artifacts. External target repos own source, checkpoints, evaluation data and scientific validation.

**PR #1 is documentation and skill instructions only**, not a running execution engine or validated System plugin. See [docs](docs/README.md), [skills](skills/README.md), [MVP proposal](docs/proposals/PROP-0001-mvp.md).
