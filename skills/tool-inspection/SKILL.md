---
name: tool-inspection
description: Inspect an existing bioinformatics program or scientific algorithm, trace source and intermediate evidence, and identify candidate bottlenecks or failure mechanisms. Use when a tool's behavior is opaque before a targeted improvement experiment.
---

# Tool Inspection

## Inputs
Obtain an authorized pinned target or evidence reference, an explicit scientific question and the existing domain evaluator when required. Do not invent missing ground truth or permissions.

## Procedure
1. Verify authorized target code/binary, pinned revision, source license and approved datasets. Read-only inspection first.
2. Map input → stage invariants/heuristics → intermediate evidence → output, known limitations, tests, time/space hotspots and domain evaluator.
3. Find prior upstream fixes and components to reuse before advocating a Rust rewrite. Separate observation, hypothesis and proven flaw.
4. Return a source observation artifact with evidence, uncertainty and possible ideas; send to `hypothesis-generation` or `failure-analysis`. Never change evaluator or source during inspection.

## Output
Return an evidence-linked artifact as proposed in [BioEvolve artifact contracts](../../docs/reference/artifacts.md) and report any blocker/uncertainty honestly. When evaluation is relevant, honor the [metric policy](../../docs/reference/metrics.md). Instructions are not proof of executed work.
