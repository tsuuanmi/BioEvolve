---
name: bioevolve-inspect-tool
description: Inspect existing bioinformatics software or a deterministic scientific algorithm to map input/output, source logic, intermediate evidence, performance, tests and limitations; use to diagnose a black-box tool or plan a targeted repair.
---

# bioevolve-inspect-tool

## Required input
An authorized, pinned external target or artifact, relevant evidence, and a defined scientific question. Use only approved data and evaluator.

## Procedure
1. Confirm target URI, pinned revision, license and allowed data. Work read-only.
2. Trace input → stages/algorithm → output, internal invariants, error paths and known limitations. Inspect source, tests and existing upstream tools; assess reuse before rewrite.
3. Mark observations separately from inferred explanations and unverified claims.
4. Return target and observation artifact with evidence, source links, limitations, unknowns and recommended reproducer.
5. Handoff to bioevolve-analyze-failure. Stop if unauthorized, unpinned or data-sensitive.

## Output contract
Return structured, evidence-linked artifacts as specified in [BioEvolve contracts](../../docs/reference/artifacts.md). Include blockers and uncertainties explicitly; do not claim unexecuted work.
