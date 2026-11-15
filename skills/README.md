# Modular skills

Each folder is an independent `SKILL.md` entrypoint. They can be invoked standalone, composed by an agent, or delegated through System via a future adapter. These are **instructions**, not executable implementations.

| Skill | Input → Output |
|---|---|
| [inspect-tool](bioevolve-inspect-tool/SKILL.md) | repository/binary → source observation |
| [inspect-model](bioevolve-inspect-model/SKILL.md) | checkpoint/architecture → model observation |
| [analyze-failure](bioevolve-analyze-failure/SKILL.md) | observation + baseline → failure |
| [design-experiment](bioevolve-design-experiment/SKILL.md) | failure → falsifiable hypothesis |
| [evaluate](bioevolve-evaluate/SKILL.md) | baseline + candidate → evaluation |
| [feedback-loop](bioevolve-feedback-loop/SKILL.md) | evaluation → feedback/next hypothesis |
| [system-handoff](bioevolve-system-handoff/SKILL.md) | artifacts → System-compatible handoff after API inspection |

Composition: inspect (tool **or** model) → failure → experiment → target's existing coding/model worker → evaluate → feedback. System handoff can wrap any stage. See [artifact contracts](../docs/reference/artifacts.md).
