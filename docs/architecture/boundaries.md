---
status: draft
implements: [SRS-BE]
---

# Skill-first and System boundaries

BioEvolve is reusable as standalone **skills**, a composed **SIL workflow**, or an optional System **capability/plugin**. Skills have plain canonical names, not a project prefix.

| Owner | Does | Does not |
|---|---|---|
| BioEvolve SIL | Ideation, hypothesis, metric proposal, experiment planning, result comparison, feedback artifacts | Schedule workers or decide biological release |
| Rust core (planned) | Typed contracts, gating/comparison and evidence integrity | Train models or replace domain evaluators |
| Python (planned) | Scientific/model experiments and upstream tool adapters | Own agent orchestration |
| TypeScript (planned) | System plugin/UI adapter | Create another scheduler/Work state |
| System (optional) | Work/Attempt, spawn/retry/cancel, verify artifact integrity | Certify domain-specific scientific accuracy |
| Target repo | Code/weights, datasets, scientific ground truth, evaluation and approval | BioEvolve global workflow |

```text
Local agent / System Worker
           |
  BioEvolve improvement-loop skill
     |                   |
 idea/hypothesis      metric contract (frozen)
     |                   |
  isolated candidate + external evaluator
           |
    Rust result comparison (planned)
           |
   feedback + evidence artifacts
           |
 System verification (optional) + domain science gate
```

BioEvolve uses **existing target evaluation** (e.g. DNA's `dna-eval`) and does not reimplement it. Model interpretability is a supporting analysis path, not required in every experiment. Rewriting a tool or editing weights is a possible outcome, not the default. System verifies delivery/contract; the domain evaluator verifies scientific claims.

See [loop](loop.md), [stack](tech-stack.md), [metrics](../reference/metrics.md).
