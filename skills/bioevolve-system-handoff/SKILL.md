---
name: bioevolve-system-handoff
description: Bridge BioEvolve scientific skills and artifacts to a System repo worker without recreating System Work, Attempt, worker scheduling or verification; use when integrating with System.
---

# bioevolve-system-handoff

## Required input
An authorized, pinned external target or artifact, relevant evidence, and a defined scientific question. Use only approved data and evaluator.

## Procedure
1. Read real System plugin, Work/Attempt/Artifact contracts of the target installed version; never assume API compatibility.
2. Translate a scoped BioEvolve skill request into System's existing capability/Work conventions, without owning scheduling or worker lifecycle.
3. Return immutable artifact refs, evaluator evidence, provenance and scientific disposition using supported System interfaces.
4. System verifier determines Attempt status; the target's domain evaluator independently determines scientific validity.
5. If interface is missing, return explicit integration gap; never fabricate success or create parallel Work IDs.

## Output contract
Return structured, evidence-linked artifacts as specified in [BioEvolve contracts](../../docs/reference/artifacts.md). Include blockers and uncertainties explicitly; do not claim unexecuted work.
