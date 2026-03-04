---
name: base-skills
description: "Foundational software engineering workflow for common repository tasks: scoping requests, inspecting code, implementing minimal changes, validating behavior, and reporting results. Use when Codex handles general coding work that does not require a domain-specific skill, including bug fixes, refactors, feature additions, test updates, and small documentation changes."
---

# Base Skills

## Overview

Apply a reliable default workflow for everyday coding tasks in a local repository. Optimize for correctness, minimal diffs, and clear reporting of what changed and what was verified.

## Workflow

1. Clarify the target outcome and constraints.
- Extract acceptance criteria from the user request.
- Record environment constraints (OS, sandbox, toolchain).
- Prefer reasonable assumptions over blocking questions when risk is low.

2. Gather context quickly.
- Use `rg --files` and targeted `rg` searches before opening large files.
- Read only files required to understand behavior and interfaces.
- Reuse existing patterns in the repository when possible.

3. Implement the minimum effective change.
- Edit the smallest file set that satisfies the request.
- Preserve surrounding style and architecture.
- Add comments only where logic is non-obvious.
- Avoid new dependencies unless they are necessary.

4. Validate results.
- Run the narrowest relevant check first (targeted test/lint/script).
- Expand to broader checks only when needed.
- If validation cannot run, state exactly what is unverified and why.

5. Report clearly.
- Summarize behavior changes and rationale.
- Call out risks, assumptions, and follow-up actions.
- Reference modified files with absolute paths.

## Quality Bar

- Keep behavior backward compatible unless the request requires a break.
- Prefer explicit failure paths over silent fallback behavior.
- Avoid destructive git operations unless explicitly requested.
- Do not revert unrelated user changes.

## Output Pattern

For substantial tasks, use this response structure:
1. Solution summary.
2. Files changed and purpose.
3. Validation performed and outcomes.
4. Remaining risks or assumptions.
