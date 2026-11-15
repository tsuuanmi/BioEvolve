# BioEvolve

**Scientific Improvement Loops for existing bioinformatics tools and neural networks.**

BioEvolve is a portable collection of **skills, workflows and feedback-loop contracts** for an agent working inside a scientific repository. It is neither a research paper, a replacement bioinformatics pipeline, nor another agent scheduler.

## Core idea: SIL first

`Idea → Hypothesis → Evaluation criteria → Controlled test → Evaluate → Feedback → Updated idea`

The [Scientific Improvement Loop (SIL)](docs/architecture/loop.md) is the first product priority. Its input is an existing tool, algorithm or model; its output is a **traceable sequence of improvement attempts**, including rejected hypotheses and reasons. Agents may inspect source or neural weights/activations as necessary, but inspection frameworks and large-scale rewriting are *supporting capabilities*, not the MVP.

The agent must propose **metrics and scientific guardrails before an experiment**. A candidate that gains throughput but introduces a serious false call is not an improvement. Independent scientific evaluation remains authoritative.

## Stack (target)

- **Rust — core:** typed contracts, artifact/provenance integrity, comparison logic, deterministic evaluation gates and a small CLI.
- **Python — experiments:** scientific adapters, model inspection/probing, benchmark and training/inference experiments, reusing upstream Python scientific tooling.
- **TypeScript — integration:** optional System capability/plugin bridge and future UI or developer integration; not a second orchestrator.

[Technology responsibilities](docs/architecture/tech-stack.md) specify the boundaries. **PR #1 remains documentation + SKILL.md instructions only**: none of the Rust/Python/TypeScript runtime has been implemented.

## Use independently or through System

BioEvolve skills are [short, canonical, unprefixed skills](skills/README.md) such as `improvement-loop`, `metric-design`, `experiment-evaluation` and `feedback-loop`. A local coding agent or System worker can invoke them in an external repo. System owns Work/Attempt, scheduling, retries and artifact verification. The target repo owns source/checkpoints, evaluator, data access and scientific release decisions.

## Inspiration

[Karpathy's autoresearch](https://github.com/karpathy/autoresearch) demonstrates fixed evaluator, fixed experimental budget, restricted mutation scope, logged keep/discard decisions and tight feedback. BioEvolve adapts those ideas to heterogeneous bioinformatics objectives, **with metric design and safety/validity gates rather than a universal single score**. [Adaptation notes](docs/research/RES-0002-autoresearch.md) explain what is reused and what is not.

Start with [docs](docs/README.md), [SIL architecture](docs/architecture/loop.md), [evaluation criteria](docs/reference/metrics.md) and [MVP plan](docs/proposals/PROP-0001-mvp.md).
