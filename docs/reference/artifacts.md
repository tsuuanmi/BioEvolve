---
status: draft
implements: [SRS-BE]
---

# Scientific experiment artifacts — v0 proposal

Skills exchange immutable, versioned **artifacts**, not arbitrary assertions. IDs/digests reference data stored under target repository permissions; System Work/Attempt IDs remain distinct.

| Kind | Required evidence |
|---|---|
| target | kind, URI, revision/checkpoint hash, permitted scope, domain evaluator |
| idea | origin (failure, literature, operator), expected impact, prior related experiments |
| hypothesis | idea ref, causal claim, alternatives, falsifier, expected effect |
| metric_contract | primary metric + direction, minimum effect, mandatory safety gates, diagnostic slices, resource budget, evaluator hash, dataset/splits and approval/freeze state |
| baseline | target revision, metric contract ref, environment, measurements, logs/digests |
| experiment | hypothesis ref, base/candidate revision, isolated patch, budget, run outcome, evaluator logs |
| evaluation | exact baseline/candidate refs, frozen metric contract hash, per-slice deltas, uncertainty, regressions, resource usage, comparable flag |
| feedback | evaluation ref, classification, rationale, next hypothesis or stop, historical lineage |

## Proposed schema shape (illustrative, not executable)

```yaml
contract: bioevolve.experiment/v0-proposal
idea:
  source: "a reproducible failure or observation"
hypothesis:
  statement: "a falsifiable mechanism"
  prediction: "what should change and where"
  falsification: "what evidence would refute it"
metric_contract:
  evaluator_sha256: "<digest>"
  dataset_manifest_sha256: "<digest>"
  primary: {name: "domain-specific metric", direction: "maximize", min_effect: "<predefined>"}
  hard_gates: ["no unacceptable scientific regressions"]
  diagnostics: ["failure classes", "dataset strata"]
  resources: {wall_time_budget_s: "<fixed>"}
  frozen_before_candidate: true
experiment:
  baseline_revision: "<immutable SHA>"
  candidate_revision: "<immutable SHA>"
  status: completed
evaluation:
  comparator: paired
  decision: inconclusive
feedback:
  next_hypothesis: "what to test next, if authorized"
```

No metric may be changed after observing a candidate and still count as the same comparison. Failures, OOM and timeout are explicit statuses. Artifacts should include platform/toolchain versions, seeds, hashes, logs, data privacy classification and access references. Avoid copying sample identifiers or weights into public logs. Raw observations are distinct from interpretations and claimed causal mechanisms.

**System handoff:** BioEvolve returns experiment IDs and artifact references; System independently verifies Work/Attempt. Domain owners approve biological scientific validity; BioEvolve alone cannot certify it.

See [metric design](metrics.md) for precedence and domain-specific proposals.
