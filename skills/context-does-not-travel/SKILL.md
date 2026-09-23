---
name: context-does-not-travel
description: Make authorized agent handoffs self-contained and verifiable when delegating tasks, separating parallel work, combining results, or diagnosing instructions that depend on observations an agent lacks.
---

# Context does not travel

A handoff is a message to another process. Do not assume that process has the
conversation, tools, files, or observations you have.

Some runtimes inherit conversation history, share a filesystem, or support
messages between agents. Check the actual contract. Inherited history still
does not tell a worker what another worker just changed.

Use this skill when delegation is already appropriate and authorized. It does
not make a small task a reason to start a team.

## Four consequences

**1. An instruction needs an observation.** Before emphasizing an instruction
that keeps failing, ask what the agent must see to follow it.

For example, deciding whether a reminder is overdue requires the due time,
the current time, and the relevant time zone. "Mark overdue reminders"
cannot supply those observations.

**2. Parallel work needs an owner and a combine rule.** Assign bounded scopes
and identify overlapping files or decisions before dispatch. Shared storage
makes edits visible; it does not reconcile competing edits.

Choose how results will be joined, deduplicated, and checked. The coordinator
owns that step.

**3. Agreement is not independent evidence.** Identical prompts and evidence
can produce correlated errors. When independent review matters, vary the
review lens or evidence and ask reviewers to challenge the claim. Distinguish
supported, contradicted, and unresolved findings. Uncertainty is neither a
vote for the claim nor proof against it.

**4. A fluent return can still be a failure.** Require an outcome that can be
checked: findings, supporting evidence, artifacts changed, validation performed,
and unresolved gaps. Treat an empty or failed return explicitly rather than
counting it as agreement.

## Write the handoff

Include the information needed for this task, without dumping unrelated context:

- The concrete objective and the condition that ends the task.
- The inputs and decisions the worker must rely on.
- The working location, permitted files, and ownership boundaries.
- The tools or observations the task needs, with availability confirmed.
- Existing limits on side effects, spending, and further delegation.
- The expected return and how the coordinator will validate it.

Use explicit paths or attached inputs where the environment supports them.
Replace "as discussed" with the actual decision.

If a backchannel exists, state how to report a blocker. If it does not, define
what an incomplete return should contain. Do not promise a capability merely
because the parent process has it.

## Combine results

Check the returned artifacts and supporting evidence. Resolve overlap and
contradiction before presenting a conclusion. Investigate disagreement at its
source; do not average incompatible claims.

A well-formed report is a starting point for validation, not proof that the
work is correct. Preserve the distinction between a worker's claim and an
outcome you independently checked.
