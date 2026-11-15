---
status: draft
implements: [SRS-BE]
---

# Evaluation and metrics design — proposed canonical contract

**Purpose:** Tell the feedback loop *what to optimize* and *what must never regress*. BioEvolve does not assign a universal accuracy score to heterogeneous scientific systems. The `metric-design` skill produces a proposed contract; the target owner/evaluator validates and freezes it **before** candidate results exist.

## Metric selection process

1. Identify the **scientific task** and unit of analysis (base, locus, variant, trace, sample, batch, molecule, graph). Preserve the target's real labels, abstention/review classes and known error costs.
2. Define an **optimization objective** in plain language (e.g., decrease human review load **without increasing undetected wrong calls**).
3. Recommend one **primary outcome metric** with direction, minimum meaningful improvement and denominator. If no reliable single primary exists, explicitly declare ordered/pareto objectives instead.
4. Define **hard validity/safety gates**, including allowed regression tolerances, scientifically unacceptable errors, data coverage and input/output compatibility. A failed gate **cannot be traded off** for speed or average accuracy.
5. Define **diagnostic metrics** by relevant failure class, geography/biological context, coverage/sequence type, batch, assay and distribution-shift slices. Prefer paired sample-level changes and error counts.
6. Specify **resource metrics** (end-to-end wall time, CPU/GPU-hours, peak RAM/VRAM, throughput, energy/cost if measured), compute budget and expected deployment environment.
7. Define **uncertainty and evidence**: confidence intervals or exact counts where appropriate, low-frequency-event sample power, independent ground truth, matched baseline, negative controls and abstention handling.
8. **Freeze** evaluator URI/version/config hash, dataset manifest/split hashes, metric definitions, thresholds and tie-breaker before a candidate run. If scientific metrics cannot be justified, mark the loop `blocked` or `investigate`.

The skill must propose metrics **with rationale and limitations**, not blindly declare that a generic score such as accuracy, F1 or AUC is adequate. Target scientist/reviewer may reject the proposal.

## Evaluation categories

| Role | Question | Acceptance semantics |
|---|---|---|
| Hard gate | Is the change scientifically valid and safe? | Must pass before any improvement decision |
| Primary | Did the user-valued scientific/engineering target improve? | Prespecified direction and minimum effect |
| Diagnostic | Which failure classes improved or worsened, and why? | Always report, investigate costly new errors |
| Resource | What does the improvement cost to train/compute/use? | Compare against declared budget, constraints or tie-breaks |
| Interpretability/causal | Did a claimed mechanism survive interventions and controls? | Require this only if mechanistic understanding is claimed |

## Candidate suggestions (never universal defaults)

| Domain/task | Primary metric candidates | Critical gates and slices |
|---|---|---|
| Sanger base/variant analysis (DNA) | Correct automatic-pass fraction; reduction in review workload at fixed error bound | Wrong-auto-pass count/rate; exact variant concordance, missed allele/heteroplasmy, locus/tract/batch/strand; use `dna-eval` rules and existing holdout policy |
| STR signal/allele interpretation | Review workload with verified allele correctness | False calls, stutter/pull-up, mixed signal, locus and sample profile; validated laboratory truth |
| Sequence/classification CNN | Class-specific recall at fixed precision/FPR; PR-AUC for imbalanced labels; macro F1 where suitable | False-negative groups, calibration (ECE/Brier), OOD shifts, GC-content and motif controls |
| Molecular GNN regression/ranking | Task-appropriate MAE/RMSE, rank correlation or PR-AUC | Scaffold/target/time splits, activity cliffs, per-scaffold errors, calibration/uncertainty |
| Genomic language/foundation model | Task-specific held-out likelihood or downstream performance | Functional biological tasks, OOD sequences, memorization/leakage, training/inference budget |
| Model mechanism investigation | Reproducible causal intervention effect and specificity | Matched negative intervention, stability across seeds/inputs, absence of unrelated behavioral regression |
| Pure software performance | End-to-end time/throughput, peak memory | Byte-/call-equivalent outputs or explicit scientifically approved tolerance; CPU, energy or deployment constraints |

Metric proposals are *hypotheses about good measurement*, not claims these metrics can all be computed for every dataset. Select from real available labels and adjudication policy.

## Keep/discard rule

1. If provenance, metric contract, data or evaluator are **incomparable**: `blocked`, not a score.
2. If run failed, timed out or produced incomplete outputs: `failed`, not `score=0`.
3. If **any hard gate fails**: `regressed`, regardless of primary improvement.
4. If primary meets the prespecified minimum change **and** evidence/uncertainty standard: `improved` on development data (still not released).
5. If measured effect is indistinguishable from noise or contradictory: `inconclusive` (or `neutral` under a frozen equivalence/simplicity rule).
6. When two feasible changes trade off primary and compute, use **declared Pareto/lexicographic comparison**; do not select weights or thresholds after seeing scores.

For rare safety events, `0 observed new errors` is not proof of `0 true error rate`; report denominator and a justified confidence bound. If statistical power is inadequate, return `inconclusive`.

## Separating optimization and scientific confirmation

Development runs drive feedback; **independent holdout** establishes out-of-sample evidence under access policy. A new metric idea motivated by seeing results is allowed as *research* but requires a new metric-contract version and fresh unbiased evaluation before promotion.

See [SIL flow](../architecture/loop.md), [artifact format](artifacts.md) and [validation gates](../validation/gates.md).
