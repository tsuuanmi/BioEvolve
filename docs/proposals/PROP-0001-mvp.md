---
type: proposal
id: PROP-0001
status: proposed
created: 2026-11-15
summary: Prioritize metric-aware Scientific Improvement Loops with Rust core, Python experiments, TypeScript integrations and portable skills.
---

# PROP-0001 — SIL-first BioEvolve MVP

## Decision framing

The first product is a **fast, safe, evidence-driven Scientific Improvement Loop**, not a universal black-box interpreter, autonomous scheduler, paper, or new biology model.

`Idea → Falsifiable hypothesis → Metric proposal/freeze → Test → Evaluate → Feedback → Next idea`

Borrow [autoresearch's](../research/RES-0002-autoresearch.md) tight mutation scope, fixed budget/evaluator, baseline, experiment log and keep/discard feedback. Diverge by adding scientific safety gates, metric recommendation, multiple target-dependent objectives, explicit failed/inconclusive states and independent holdout promotion.

## Technology plan

- **Rust core:** state and artifact contracts, evidence/provenance check, deterministic comparison/gates, CLI (planned).
- **Python experiment:** scientific/model adapters, tests and training experiments using upstream tools and existing target evaluators (planned).
- **TypeScript integration:** optional System skill/plugin adapter or UI, only after real API review (planned).

Avoid early database, large microservice architecture or duplicate agent scheduling. Versioned JSON is the portability boundary.

## PR #1 only

Update docs, skill names and instruction entrypoints, SIL semantics, metric/evaluation contract, autoresearch adaptation research and stack ownership. **Documentation and SKILL.md only**: no tested runtime, installed System plugin or scientific benchmark success.

## Phased follow-on PRs

1. **SIL proof:** minimum Rust metric/evidence comparator and Python synthetic evaluator adapter; strict fixed metric contract, crash/timeout states and JSON artifacts. Test one improvement, one regression, one inconclusive result, one failed run; demonstrate bounded feedback.
2. **DNA pilot:** call existing `dna-eval`; propose scientific metrics from its current rules, apply wrong-auto-pass gates and compare changes on authorized development panels without using holdout as tuning.
3. **Mechanism pilots:** use optional source tracing/CNN/GNN probing **only when needed for a specific failure hypothesis**, not as a prerequisite for any optimization.
4. **System integration:** read live Work/Attempt/Artifact interface, add minimal TypeScript adapter; System owns scheduling and verification.
5. **Docs checks:** adopt tested portable documentation checker and CI, update level claims only when passing. This may proceed in parallel.

## Acceptance criteria for initial runnable proof

- An agent can submit an idea, obtain a falsifiable hypothesis and a **suggested metric contract with explicit domain approval**, and run an unchanged evaluator under the same budget for baseline and candidate.
- A safety regression vetoes improvement; feedback states are explicit; failures are not encoded as scores.
- Results include measured effect, per-slice changes, cost, uncertainty, provenance, and a bounded next idea.
- All candidates are isolated; negative experiments preserved; no secret/holdout leakage.
- No scientific production merge without independent domain evaluation.
