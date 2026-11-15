---
status: draft
implements: [SRS-BE]
---

# Technology responsibilities — target architecture

**Rust is the core; Python performs experiments; TypeScript enables integrations.** This is the intended stack, not shipped code.

| Layer | Primary responsibilities | Non-responsibilities |
|---|---|---|
| Rust core | Versioned typed experiment/metric/artifact contracts, deterministic comparison and gating, reproducibility/provenance checks, result persistence and small CLI | Tensor training frameworks, agent scheduling, second domain evaluator |
| Python experiment | Scientific data adapters, model execution, hooks/probing, fine-tuning, statistics and benchmarks; call existing `dna-eval`, Captum/PyG/NNsight or target-specific tools when appropriate | System Work/Attempt state, duplicate central artifact definitions |
| TypeScript | Optional System capability/plugin adapter, developer experience and future lightweight UI; transport the same contracts | BioEvolve-owned scheduler or truth evaluator |

## Protocol

Use small, versioned, language-neutral JSON artifacts/contracts with pinned hashes. Rust is the reference implementation of validation and acceptance logic; Python and TypeScript consume/generate matching schemas, with cross-language contract tests before claiming compatibility. Define source-of-truth semantics **once**; no duplicated scoring algorithms per language.

## MVP priorities

1. Define SIL state transitions and metric contract, independent of storage or GUI.
2. Implement a minimal Rust comparator/gate against recorded (mock/synthetic) evaluator outputs, with explicit incomparable/failure states.
3. Add a Python experiment adapter to invoke **existing** evaluators with fixed inputs and budgets.
4. Add TypeScript only when a concrete System integration or UI use case requires it.

A SQLite ledger, parallel runner, distributed queue or dashboard is deferred until measured need. Keep science engines external and avoid replacing proven upstream tooling.
