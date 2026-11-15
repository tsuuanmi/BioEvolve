---
status: draft
---

# Scientific improvement evaluation gates (proposed)

- **G0 — Objective freeze:** `metric-design` recommends and a domain owner freezes task unit, primary metric/direction/minimum effect, non-negotiable scientific hard gates, diagnostics, budget, evaluator identity/config, dataset manifest/splits, uncertainty rule and tie-breaker **before** test results.
- **G1 — Baseline / provenance:** reproduce unchanged baseline with pinned source/checkpoint, data, software/hardware versions, seeds where relevant and an evaluator outside the candidate change scope.
- **G2 — Falsifiable hypothesis:** document mechanism, expected effect, alternatives, negative controls and a stopping criterion. Distinguish causal evidence from attribution.
- **G3 — Controlled development:** identical evaluator and scientific truth for candidate and baseline; paired comparisons, slice regressions, resource measurements, confidence/low-frequency constraints. Use fast subset only as a filter; full development data is needed for improvement claims.
- **G4 — Explicit feedback:** report `improved/regressed/neutral/inconclusive/failed/blocked`; preserve rejected candidates and logs, update hypothesis history, propose bounded next action. No silent failures and no fake zero score for crashes.
- **G5 — Independent promotion:** authorized untouched holdout, distribution shift and independent domain approval before shipping; no self-approval by System's code CI or agent.

Reuse **target's evaluator**, especially DNA's existing `dna-eval` and its exact wrong-pass/review rules. Never substitute a generic BioEvolve score for a scientific safety gate. If throughput improves but false positive variants increase beyond tolerance, candidate fails. If sample power cannot establish a safety threshold, result is inconclusive. Distinguish engineering, scientific and mechanistic gains.

Changing evaluation criteria after inspecting results is a **new protocol version** and requires new unbiased validation.
