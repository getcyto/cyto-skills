---
name: one-place-to-be-wrong
description: Remove accidental duplication of derived business rules across pipelines, displays, languages, and caches when formulas drift or multiple implementations must stay in sync.
---

# One place to be wrong

Compute a derived value where its inputs are final. Let other surfaces read
that result.

"These two need to stay in sync" often means the architecture has given one
rule two owners. Both implementations can look reasonable in isolation while
showing the user different answers.

## Find the second rule

Trace the displayed claim back to its inputs. Look for:

- A chart and headline computing the same fact separately.
- A browser reimplementing a rule already evaluated by a pipeline.
- Narration generated before the inputs receive their final enrichment.
- A cache whose inputs can change without invalidating it.
- A test that exists only to keep accidental production copies aligned.

One shared module used by multiple runtimes is still one implementation.
An independent reference implementation used to test correctness can also be
valuable. Distinguish those cases from accidental duplication.

## Move derivation downstream

Illustrative pipeline:

```text
Before:
raw observations -> summary computes its own total
raw observations -> corrections -> chart computes another total

After:
raw observations -> corrections -> compute final total once
                                      |-> chart reads total
                                      |-> summary reads total
```

Choose the canonical calculation, move it after the last input transformation,
and pass its result to each consumer. Remove the obsolete calculation once its
consumers have moved. Keep tests that verify the surviving rule against known
outcomes.

The fix is structural: a future edit to the rule should not need a matching
edit in another implementation.

## Make related outputs travel together

When a claim needs a value, unit, baseline, or observation time to make sense,
return them together. Have displays consume the same result rather than
reconstructing the pairing.

For example, a rate and its denominator should come from the same calculation.
If the denominator is unavailable, report the gap instead of constructing a
plausible-looking rate.

## Handle real boundaries deliberately

Measure a suspected performance bottleneck before introducing another source
of derived truth. Reusing the module, precomputing a result, or shipping the
derived data may satisfy the requirement.

If offline operation or another measured constraint requires a separate
implementation, state that constraint. Define versioning and conformance
checks rather than pretending the duplication has disappeared.

A cache is a stored projection. Identify its source version, invalidation rule,
and acceptable staleness. Reading the same raw data is not enough if two
consumers apply different rules.

## Verify the result

Use a changed input and a boundary case that previously exposed disagreement.
Check every affected output, including text. Confirm that they now consume
the canonical result and that obsolete paths have no remaining callers.
