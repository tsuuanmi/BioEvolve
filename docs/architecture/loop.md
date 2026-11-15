---
status: draft
implements: [SRS-BE]
---

# Scientific Improvement Loop (SIL) — first product priority

SIL is **a bounded experiment protocol, not a worker scheduler**. Inspired by [autoresearch](../research/RES-0002-autoresearch.md), it makes a scientific agent repeat *idea → hypothesis → test → evaluation → update* while keeping the evaluator and acceptance criteria out of the candidate's mutation scope.

## One loop

1. **Idea:** Read target context, domain requirements, available failure evidence and previous failed attempts. Generate one concrete improvement idea (may be exploratory; do not assume a known bug).
2. **Hypothesis:** Specify mechanism, expected effect, alternatives and a falsifier. Record where the evidence ends and conjecture begins.
3. **Metrics / plan:** `metric-design` recommends a primary metric, **non-negotiable safety gates**, diagnostic slice metrics, resources and confidence/uncertainty rules. A target owner approves or explicitly freezes this evaluation contract *before* candidate execution. Metrics are not silently redefined mid-loop.
4. **Baseline:** Run or load a matched reference using pinned target, evaluator, datasets and environment; log baseline score and resource cost.
5. **Test:** Execute **one small, reversible change** in isolated code branch/model checkpoint using an existing worker. Use fixed budget and in-scope paths; original evaluation code/data are read-only.
6. **Evaluate:** Run exactly the same frozen development evaluator; compare paired results, per-failure-class regressions and resources. Invalid/crash/timeout are statuses, **not numeric zero scores**. Fast subsets may screen candidates, but cannot independently justify promotion.
7. **Update:** `feedback-loop` records keep-for-next-development / discard / investigate / blocked, the observed mechanism, unexpected failures and one next hypothesis. Rejected attempts are retained as evidence; the candidate working tree can be reverted *without deleting the experiment ledger*.
8. **Promote separately:** Only a distinct, authorized independent holdout and domain-science review can accept a scientific improvement for integration/release.

```text
 Idea → Hypothesis → [Freeze metric contract + baseline]
             |                    |
             v                    v
        Reversible test ——→ Compare & gate
             ^                    |
             |                    v
         Next idea ←—— Structured feedback + history
                                  |
                           Promotion review (separate)
```

## Feedback state machine

| Outcome | Condition | Next action |
|---|---|---|
| `improved` | Valid comparable development result; safety gates pass; prespecified primary objective improves enough | Keep as new *development incumbent*, not scientifically released |
| `regressed` | Safety violation, worse prespecified objective or unacceptable cost | Discard candidate; record responsible slices/hypothesis |
| `neutral` | Valid but no meaningful gain | Discard or investigate simplification, according to frozen rule |
| `inconclusive` | Uncertainty, insufficient power or attribution not causal | Request stronger evidence/control, no promotion |
| `failed` | Crash, timeout, OOM, incomplete execution | Diagnose bounded retry; never treat missing score as improved |
| `blocked` | No authorization, inconsistent provenance, invalid metric contract or holdout leakage risk | Stop and request corrective input |

In a multi-objective case, any candidate violating a **hard gate is rejected regardless of the primary score**. Among feasible candidates, select via a declared objective and resource trade-off; use Pareto comparison or lexicographic priority rather than inventing post-hoc weighted scores. Any change to metrics after seeing results **starts a new evaluation protocol version** and invalidates direct keep/discard comparability.

## Bounded operation, not infinite autonomy

The calling System Work/human sets max attempts, cost, elapsed time, retries and stop criteria. SIL may recommend another cycle but **does not** launch unbounded agents or override cancellation. Require explicit resumption from the last fully recorded artifact, not silently repeated failures.

## Fair comparison and validity

Keep an unchanged evaluator, fixed development partitions and comparable runtime/budget; log seed, hardware, revisions and compiler/interpreter versions. Re-run on full development data before claiming an improvement. Do not use independent holdout as an optimization signal. For DNA, call the existing `dna-eval`, respect its wrong-auto-pass and review-workload constraints; for neural models, use target-specific scientifically relevant metrics.

## First acceptance test

A synthetic baseline with one reproducible failure, a **frozen metric contract**, one improving change, one regressing change and one crash should produce four independently checkable experiment/feedback records and an updated bounded hypothesis queue. Nothing in this PR implements that test yet.
