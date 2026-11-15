# Portable scientific improvement skills

Names are short, lower-case **canonical task names** with no `bioevolve-` prefix. These are `SKILL.md` instruction entrypoints (plus metadata), **not an installed/validated executable engine**. A local agent can use one skill; System can delegate a bounded `improvement-loop` Work and consume artifacts without BioEvolve managing workers.

## Core SIL — first priority

| Skill | Task | Produces |
|---|---|---|
| [improvement-loop](improvement-loop/SKILL.md) | Coordinate **one bounded cycle**, not a daemon | Loop state and evidence refs |
| [hypothesis-generation](hypothesis-generation/SKILL.md) | Idea → falsifiable hypothesis | Hypothesis + controls |
| [metric-design](metric-design/SKILL.md) | Propose/freeze scientifically correct evaluation objectives | Metric contract |
| [experiment-design](experiment-design/SKILL.md) | Small controlled test under fixed budget | Experiment plan |
| [experiment-evaluation](experiment-evaluation/SKILL.md) | Matched baseline/candidate comparison, hard gates | Evaluation |
| [feedback-loop](feedback-loop/SKILL.md) | Keep/discard/investigate and update next idea | Feedback |

## Supporting skills — optional

| Skill | Task | Produces |
|---|---|---|
| [tool-inspection](tool-inspection/SKILL.md) | Trace deterministic scientific code/algorithm | Observations |
| [model-inspection](model-inspection/SKILL.md) | Inspect weights, activations, probes | Observations |
| [failure-analysis](failure-analysis/SKILL.md) | Reproduce/stratify an error or limitation | Failure report |
| [system-integration](system-integration/SKILL.md) | Map artifacts to real System interfaces | Handoff |

Suggested handoff:

```text
idea + existing context
  → hypothesis-generation
  → metric-design  [freeze before testing]
  → experiment-design
  → target repo's existing worker/runner
  → experiment-evaluation [domain evaluator unchanged]
  → feedback-loop → next bounded cycle or stop
```

`tool-inspection`, `model-inspection`, `failure-analysis` are invoked selectively if they increase diagnostic value. [Canonical metric rules](../docs/reference/metrics.md) and [artifact contract](../docs/reference/artifacts.md) govern all stages.
