# Agent routing and SIL invariants

Read README.md → docs/README.md → docs/architecture/loop.md → docs/reference/metrics.md and docs/reference/artifacts.md → specific skills/<name>/SKILL.md → target repository evaluator/source/tests.

BioEvolve is **SIL-first**. The primary workflow is idea → falsifiable hypothesis → frozen evaluation plan → isolated experiment → independent evaluation → explicit feedback. Never modify evaluator, scientific ground truth, protected data, budget or acceptance thresholds to make a candidate win. Prefer narrow reversible diffs to broad rewrites; preserve rejected experiments.

Use Rust for core types/comparison/integrity, Python for scientific experiments and analysis, and TypeScript for optional System integration. Do not recreate System workers, Work/Attempt, scheduling or verification. Follow the portable documentation standard and repository profile. Treat proposals and research as unimplemented. No runtime or CI claims until executed.

Require: target revision, baseline, evaluator hash, data/partition manifest hash, metric contract (primary, hard gates, guards, diagnostics, cost), intervention, run log, regression analysis, disposition and next step. Failure/timeout/invalid is a *status*, never a fake numeric metric.

Respect private samples, checkpoint licenses, bounded resources, independent holdout access and domain release approval. A green System Attempt is not proof of biological correctness. Reject silent failures and endless retry loops.
