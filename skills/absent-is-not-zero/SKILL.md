---
name: absent-is-not-zero
description: Preserve the difference between measured zero, absent data, and failed measurements when implementing numeric defaults, fetch or parse error handling, coverage reports, or unit conversions.
---

# Absent is not zero

A missing measurement is not a measurement of nothing. Give it its own state
before it can enter arithmetic, a chart, or a decision.

## Recognize the collapse

Look for numeric defaults using `or` or `||`, magic sentinels, swallowed fetch
errors, and coverage fields that return constants. In Python and JavaScript,
zero is falsy: a valid zero can accidentally take the fallback.

Keep three outcomes distinguishable:

- **Measured:** a value with established units, including a genuine zero.
- **Absent:** the source was checked successfully and has no applicable value.
- **Unknown:** the value could not be determined, for example because a request failed.

A documented domain default is valid when it is the domain's actual answer.
Do not replace it merely because a fallback exists.

## Give the non-value a branch

Illustrative Python example:

```python
# Wrong: a measured zero becomes an invented duration.
duration = response.get("duration_seconds") or 9999

# Better: a valid zero stays zero; missing data stays explicit.
duration = response.get("duration_seconds")
if duration is None:
    result = {"status": "absent", "value": None}
else:
    result = {"status": "measured", "value": duration, "unit": "seconds"}
```

That example assumes the request and parsing succeeded. A failed request needs
an `unknown` result with a reason, or an exception the caller handles. Do not
send a failure through the same branch as a successful empty response.

Carry the status to callers and presentation. A log line alone does not stop
a missing value from becoming a confident number downstream.

## Apply the same rule to units and coverage

A fraction and a percentage can share the same numeric type and differ by a
factor of one hundred. Establish units from the source contract, normalize at
one boundary, and name the unit in the result. If the contract is unclear,
report that uncertainty instead of guessing from the value's magnitude.

For coverage, distinguish the requested items, successfully checked items,
absent values, and failed checks. A constant `missing = 0` cannot describe
coverage that was never measured.

## Common traps

| Pattern | Consequence | Correction |
|---|---|---|
| `x or 9999` | Zero becomes a sentinel | Check absence explicitly |
| Failed fetch returns `[]` | An outage looks like no records | Preserve failure separately |
| Missing score becomes `0` | Unknown performance looks measured | Return status and reason |
| Unknown units get inferred from size | Plausible numbers carry the wrong scale | Check the source contract |
| A required update matches nothing but reports success | The caller believes work happened | Return the match count and an explicit outcome |

An empty search can be successful. An update that was required to change a
record needs a different outcome when it changes none. Let the command's
contract decide; do not make every empty result an error.

## Verify the boundary

For affected code, check a real zero, a nonzero value, a successful absence,
and a fetch or parse failure. Verify that callers preserve the distinctions.
For conversions, check known units and an unknown unit. Never replace one
invented number with another.
