---
name: research-dev
description: Keep research development and experiments organized, reproducible, purposeful, and efficient. Use when implementing research code, planning or running experiments, evaluating baselines, or maintaining an experimental repository.
---

# Research Development

Follow these principles throughout research implementation and experimentation.

1. **Maintain disciplined Git, code, and documentation management.** Keep the repository organized, make meaningful commits, and keep code, configurations, and documentation consistent. Record experiment goals, implementation choices, relevant settings, and results so work can be understood and traced later.

2. **Minimize randomness before the first complete baseline evaluation.** Before the first end-to-end baseline eval, control avoidable sources of randomness as far as practical: fix and record random seeds, stabilize data splits and sampling, and use deterministic evaluation settings where feasible. Document any remaining nondeterminism. Finish this initial full baseline eval before proposing extra multi-seed validation. Afterwards, when the task, observed results, and available resources justify it, ask the user whether to run additional seeds to estimate the inherent evaluation variability of the current task and environment.

3. **Clean up invalid artifacts and dead code promptly.** Remove outputs from misconfigured, failed, or interrupted runs once they are confirmed invalid or no longer useful. Remove obsolete or one-off code paths and features when they are no longer needed. Retain essential logs or evidence for reproducibility and debugging, and ask before deleting anything whose value is uncertain.

4. **Stay aligned with the research objective and method.** Always keep clear what the current development or experiment aims to establish, how it will be implemented, and how success will be evaluated. If the goal, assumptions, or intended approach are unclear, ask the user rather than guessing or silently changing direction.

5. **Reuse existing work when comparisons remain valid.** Prefer reusable code and historical baseline results when the relevant experimental setup and most configurations are the same or sufficiently comparable. Record material differences and assess their effect on comparability. Do not rerun an otherwise valid baseline merely to enforce superficial “baseline consistency”; rerun only when differences would materially undermine the comparison or when the user explicitly requests it.

6. **Keep code and documentation concise and up to date.** Favor simple, readable code and focused documentation; avoid unnecessary complexity, duplication, and verbosity. Update documentation whenever related code, configurations, or workflows change, and regularly remove outdated explanations, comments, and redundant material without losing information needed for reproducibility.
