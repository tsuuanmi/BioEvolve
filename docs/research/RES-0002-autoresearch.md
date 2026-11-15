---
type: research
id: RES-0002
status: active
summary: Extract bounded, evaluator-frozen keep/discard feedback principles from Karpathy's autoresearch and identify bioinformatics-specific changes.
---

# RES-0002 — Learning from karpathy/autoresearch

Reviewed [README](https://github.com/karpathy/autoresearch/blob/master/README.md) and [program.md](https://github.com/karpathy/autoresearch/blob/master/program.md) on 2026-11-15. The source names a simple single-GPU training setup: one editable `train.py`, fixed `prepare.py` containing data/evaluation, agent instructions in `program.md`, a five-minute training budget, validation bits per byte (`val_bpb`) and a tabular keep/discard/crash log. Code changes are committed and kept if `val_bpb` improves; discarded otherwise.

## Principles to adapt

| autoresearch | SIL adaptation |
|---|---|
| One editable training file | Declared *scope of permissible mutation* (single module, small patch or cloned model checkpoint) |
| Non-editable preparation/evaluator | Immutable domain evaluator and data manifests, tracked by hashes and version |
| First run baseline | Baseline always recorded and comparable with candidate |
| Fixed five-minute training | Fixed **declared resource/time/compute budget** per comparable experiment; not universally five minutes |
| Single `val_bpb`, lower is better | Task-specific proposed **primary metric** plus *non-tradable scientific hard gates*, diagnostic slices, cost |
| Git keep/discard | Accept as *development incumbent*, discard or investigate with immutable evidence; separate independent scientific promotion |
| results.tsv experiment history | Typed append-only experiment + feedback artifacts with provenance, controls, failures and next hypothesis |
| Endless autonomous loop | **Bounded, interruptible** run governed by human/System attempt limits; explicit stop reasons |

## Important differences

- A crashed/invalid run is **not a numerical score of zero**. BioEvolve must model failures explicitly, so a "lower is better" objective cannot accidentally reward failure.
- A universal scalar is inappropriate in many genomics tasks: fewer manual checks can be a false win if false negatives or wrong auto-pass increases.
- Avoid repeated holdout peeking; only development panels drive the feedback loop. Holdout is a separate authorized promotion gate.
- Scientific truth and interpretation belong to the **target repo and domain experts**, not SIL's heuristic scorer.
- For model investigations, interpretability and causal controls are *optional evidence-producing tools*; optimizing all models must not require reading every parameter.
- Do **not** copy autoresearch's `train.py` or build another agent scheduler. Reuse its *discipline of experimentation*, not its training implementation.

## MVP hypothesis

A mechanism-aware, metric-contract-first, rapid feedback loop can produce reproducible candidate improvements with lower total research overhead than unstructured agent edits. This is a proposed engineering hypothesis; measure it on synthetic and real target evaluators before making product claims.
