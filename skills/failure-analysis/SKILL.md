---
name: failure-analysis
description: Reproduce and classify scientific software or biological model failures, using ground truth, data strata and raw evidence. Use when a proposed BioEvolve idea should target a well-defined error mechanism.
---

# Failure Analysis

## Inputs
Obtain an authorized pinned target or evidence reference, an explicit scientific question and the existing domain evaluator when required. Do not invent missing ground truth or permissions.

## Procedure
1. Reproduce observed discrepancies with pinned baseline and existing evaluator on approved development data.
2. Test annotation, preprocessing, domain shift and data artifacts as alternatives to implementation/model defects.
3. Stratify failures by domain-relevant context; capture counts/denominators, paired examples, negative controls and severity.
4. Return reproducible failure artifact and bounded candidate ideas for `hypothesis-generation`. If truth is unreliable, mark investigate rather than inventing labels.

## Output
Return an evidence-linked artifact as proposed in [BioEvolve artifact contracts](../../docs/reference/artifacts.md) and report any blocker/uncertainty honestly. When evaluation is relevant, honor the [metric policy](../../docs/reference/metrics.md). Instructions are not proof of executed work.
