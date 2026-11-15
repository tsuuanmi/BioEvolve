---
status: draft
implements: [SRS-BE]
---

# Portable skill-first architecture

BioEvolve may be consumed as (1) independent skills, (2) compositions of skills/workflows, or (3) optional plugin/capability adapter to System.

| Owner | Responsible for | Does not own |
|---|---|---|
| BioEvolve skill | Inspect, diagnose, propose, evaluate, explain, export evidence | Worker lifecycle |
| BioEvolve workflow | Order of scientific investigation and artifact handoff | Global scheduling |
| System (optional) | Work/Attempt, dispatch, retry, verification | Biological scientific truth |
| External target repository | Source/checkpoint, tests, domain evaluator, release policy | BioEvolve generic conventions |

```text
System Work / local agent / human
            |
       BioEvolve Skill
            |
 external target + reusable external analysis tools
            |
     experiment artifacts
            |
 target-owned scientific validation
            |
 optional System Artifact handoff
```

Software inspection includes code, algorithm, intermediate states and performance; model inspection includes architecture, weights, activations and causal probes. Rewriting in Rust or editing weights is an **intervention option**, not a default or guaranteed improvement. There is no BioEvolve executor or System plugin implemented in this PR.

Use the [reference contracts](../reference/artifacts.md) for outputs and [validation gates](../validation/gates.md) for scientific safeguards.
