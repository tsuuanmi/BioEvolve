---
type: proposal
id: PROP-0001
status: proposed
created: 2026-11-15
summary: Bootstrap skill-first, System-compatible BioEvolve scientific improvement workflows.
---

# PROP-0001 — Portable BioEvolve MVP

## PR #1 scope

Document the two tracks (traditional scientific tools and neural models), shared Scientific Improvement Loop, target vs System boundaries, artifact and validation contracts, reuse-first decisions and modular SKILL.md entrypoints. Copy System's portable documentation architecture standard. **Docs and instructions only; no functioning plugin, engine or model editor.**

## Later, separate PRs

1. Port/reuse portable System docs checker; verify level 1 and CI before claiming conformance.
2. Implement manifest/artifact validation and a synthetic baseline→candidate→feedback workflow with an existing evaluator.
3. Integrate DNA `dna-eval` as a read-only tool pilot, respecting dataset holdout and release restrictions.
4. Integrate a small licensed CNN/GNN pilot using upstream model tooling, probing activations and causal controls.
5. Inspect current System Work/Attempt/Artifact interfaces; implement only a capability adapter (not a dispatcher).

## Acceptance criteria

Each skill must state trigger, input, output, stop and handoff. Negative experiments stay queryable; validation is independent. No silent failures, holdout leakage, overwrite of original code/weights, fabricated SOTA results or new System work state.
