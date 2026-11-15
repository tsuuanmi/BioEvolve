---
type: research
id: RES-0001
status: active
summary: Evaluate reuse opportunities for scientific analysis, model interpretation and feedback.
---

# RES-0001 — Reuse assessment shortlist

- [autoresearch](https://github.com/karpathy/autoresearch): study baseline, immutable evaluator, fixed compute budget, experiment log and keep/discard decisions; [detailed adaptation](RES-0002-autoresearch.md).
- [Captum](https://github.com/pytorch/captum): PyTorch attribution/ablation.
- [NNsight](https://github.com/ndif-team/nnsight): neural activation tracing/interventions; verify architecture support.
- [PyTorch Geometric](https://github.com/pyg-team/pytorch_geometric): graph data/model and explanation utilities.
- [OpenEvolve](https://github.com/algorithmicsuperintelligence/openevolve): study evaluator/search mechanics, not System scheduling.
- [DNA](https://github.com/tsuuanmi/DNA): reuse `dna-eval`, scientific ground truth and existing quality gates.
- [System](https://github.com/tsuuanmi/System): work orchestration and artifact verification.

For each candidate check license, maintenance, exact API, domain fit, overhead, reproducibility and integration boundary. None is a PR #1 dependency. First deliver the SIL protocol/evaluator before heavy inspection libraries.
