---
name: supervise
description: Plan and supervise a long-running authorized build, batch, backfill, or data job with measured progress, a deadline, failure detection, and a bounded fallback when supported by the runtime.
---

# Supervise a long job

A long job borrows the user's attention. Return that attention with a clear
budget, visible progress, and an outcome for every ending.

## Before launch

State the expected duration from a prior measurement or a representative
sample. Include the hard deadline and the fallback already covered by the
user's authorization. If no pace has been measured, say the estimate is unknown
and measure a small initial chunk.

Illustrative declaration:

> The sample completed twenty items in one minute. At that pace, the remaining
> work should take about ten minutes. At the fifteen-minute limit, stop this
> job and preserve a labeled partial result.

A declaration does not grant permission to publish, spend, delete, or change
other systems. A fallback must stay within the task's existing authorization.

## Use the runtime that actually exists

Check whether the available job tool survives the calling turn, how long it
can run, and whether it delivers completion or timeout events.

Use a supported durable job runner when needed and authorized. Do not assume
a tool named "background" survives its timeout, or that a detached shell
process survives the host session. Do not detach a job to bypass an execution
limit or approval.

Record the exact job identifier, log or checkpoint location, and output path.
Confirm the launch produced a running job or a terminal result.

## Watch progress and every ending

Prefer structured job status and exit codes. Use documented log markers as
additional evidence, not an unqualified search for the word "error."

Distinguish:

- **Success:** completion plus the expected output.
- **Failure:** a nonzero exit or a reported failure.
- **Disappearance:** the job is gone with no recorded outcome.
- **Stall:** no meaningful progress beyond the longest expected step.
- **Deadline:** the agreed budget is exhausted.

Liveness is not progress. Measure completed items, checkpoints, or another
signal that represents work. A quiet log alone does not prove a stall if a
healthy step is expected to be quiet.

If a watcher expires before the job can finish, arrange a supported renewal
or an external supervisor at launch. Perform the renewal when needed; saying
it will happen does not renew anything.

## Prepare the fallback

Before it is needed, identify how to stop only this job, preserve recoverable
work, and label any partial result. Use its recorded identifier rather than
a broad process-name match.

At the deadline, execute the authorized fallback and report the outcome. If
the fallback would require a new action outside the authorized scope, stop
at that boundary and identify the decision needed.

## Report from evidence

Use completion events when available. If the environment only supports
polling, keep checks bounded and proportional to the job; state that it has
no durable notification path. Never promise an ended agent session will wake
itself.

When asked for an ETA, read progress once, recompute the remaining time from
measured pace, and correct the estimate if it moved.

On completion or cutoff, report what finished, what output was checked, what
remains, and whether any job is still running. Launching successfully is not
finishing successfully.
