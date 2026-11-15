---
status: draft
implements: [SRS-BE]
---

# Scientific experiment artifact envelope (proposed)

Each skill outputs an immutable artifact reference and a structured disposition, not unverified free-form success. Basic kinds:

| Kind | Required fields |
|---|---|
| target | kind, URI, pinned revision/checkpoint hash, authorization |
| observation | target ref, method, raw evidence ref, limitations |
| failure | baseline ref, dataset digest, error class, reproducer |
| hypothesis | failure ref, cause, expected effect, falsification, controls |
| intervention | base ref, candidate ref, reversible patch/checkpoint |
| evaluation | baseline/candidate refs, evaluator version, dataset hash, metrics, regressions, uncertainty, runtime/cost |
| feedback | evaluation ref, decision, reason, next hypothesis, unresolved risk |

Include timestamp, toolchain and environment, dependency versions, seeds when applicable, checksums and logs. Large private data remain external with access-controlled references. Never compare results from mismatched inputs or evaluator versions.

Illustrative (not an executable schema):
```yaml
contract: bioevolve.experiment/v0-proposal
target: {kind: tool, uri: git+https://github.com/tsuuanmi/DNA, revision: "<SHA>"}
hypothesis: {claim: "<falsifiable>", expected_effect: "<measure>", control: "<negative control>"}
evaluation: {baseline_ref: "<id>", candidate_ref: "<id>", dataset_digest: "<sha256>", regressions: []}
decision: {status: investigate, reason: "Independent validation pending"}
```

**System mapping:** System Work/Attempt IDs and verification status remain System-owned; BioEvolve experiment IDs remain separate. Adapter uses actual System API after inspecting it; do not invent field compatibility. Scientific evaluation is a separate gate.
