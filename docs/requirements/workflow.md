---
status: draft
---

# BioEvolve target requirements — SIL first

- **SRS-BE-001:** Accept authorized pinned external tool/model targets without taking ownership of their source or scientific truth.
- **SRS-BE-002:** Provide discoverable, **canonical unprefixed** skills and a composed bounded `improvement-loop` usable by local agents or System workers.
- **SRS-BE-003:** Support idea → hypothesis → frozen metric plan → isolated test → comparison → feedback and iterated update, even when no pre-existing failure class is known.
- **SRS-BE-004:** Establish unchanged reproducible baseline, external evaluator and immutable experiment provenance.
- **SRS-BE-005:** Recommend task-specific primary metrics, scientific hard gates, diagnostic slices, uncertainty and budget **before** candidate results; record domain-owner approval/freeze.
- **SRS-BE-006:** Compare candidates only on comparable data and evaluator versions; prioritize mandatory safety gates over global-score improvements.
- **SRS-BE-007:** Preserve positive, negative, failed, blocked and inconclusive attempts with explicit reasons, next hypothesis and bounded retry/stop.
- **SRS-BE-008:** Use **Rust core, Python experiments, TypeScript integration** with language-neutral versioned contracts.
- **SRS-BE-009:** System remains owner of Work/Attempt, scheduler/retry and artifact verification; target owners retain scientific approval.
- **SRS-BE-010:** Reuse existing target evaluation and model tooling; avoid building another scientific model engine or workflow scheduler.
- **SRS-BE-011:** Protect independent holdouts, licensed weights, raw/private data and unmodified source/checkpoints.
- **SRS-BE-012:** Optional tool/model inspection must distinguish raw observation from interpretation and causal evidence.
- **SRS-BE-013:** Bound attempts by time/cost/compute and make every experiment reproducible and interruptible.
