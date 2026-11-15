---
name: system-integration
description: Connect BioEvolve Scientific Improvement Loop skills, metrics and experiment artifacts to an existing System worker or repo development workflow. Use when System should run bounded scientific experiments without duplicating Work/Attempt or verification.
---

# System Integration

## Inputs
Obtain an authorized pinned target or evidence reference, an explicit scientific question and the existing domain evaluator when required. Do not invent missing ground truth or permissions.

## Procedure
1. Inspect live target version of System Work/Attempt/Artifact/worker plugin contracts before writing adapter assumptions.
2. Pass authorized target, idea/hypothesis, frozen metric contract, evaluator version, budget and expected output artifacts into System work.
3. Receive artifact/provenance refs and scientific disposition from BioEvolve. System verifies workflow artifacts; target domain evaluator certifies scientific validity.
4. Map cancellation, timeouts and blocked outcomes explicitly; do not create second worker dispatch/retry loop.
5. Return handoff contract or integration gap report; do not fabricate System compatibility.

## Output
Return an evidence-linked artifact as proposed in [BioEvolve artifact contracts](../../docs/reference/artifacts.md) and report any blocker/uncertainty honestly. When evaluation is relevant, honor the [metric policy](../../docs/reference/metrics.md). Instructions are not proof of executed work.
