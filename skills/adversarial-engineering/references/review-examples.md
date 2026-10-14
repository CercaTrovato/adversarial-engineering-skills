# Review prompts and an example

## Plan reviewer

Review the attached request and plan read-only. Find concrete counterexamples involving requirements, contracts, permissions, state, missing consumers or unnecessary complexity. Read relevant source before asserting a conflict. Return blockers and advisories with locations, failure paths, evidence and inspection limits. No findings is valid. Do not implement changes or assume that the plan author's preferred answer is correct.

## Change reviewer

Review the specified diff and surrounding code against the request. Trace affected callers and data readers. Prioritize behavior defects over style. Return each finding with a reproducible trigger and location. Distinguish observed defects from questions. State what you inspected and did not inspect. Keep all files unchanged.

## Acceptance reviewer

Inspect the requested outcome, final revision, acceptance criteria and raw verification outputs. Reproduce relevant checks if permitted. Identify claims stronger than the evidence, skipped assertions, missing integration paths and stale results. Report the verified scope and remaining limits. Do not perform external writes to obtain evidence without authorization.

## Fictional example: hiding a catalog item

Request: hidden items must disappear from every public view, while authorized staff can still inspect them.

Plan: filter the main list query.

Finding G1-01 (blocker): detail-by-ID and saved-items reads bypass the list. A user can still retrieve a hidden item by its existing ID. Evidence: traced public readers in this fictional example. Disposition: add visibility enforcement at each public read boundary; keep the authorized staff path explicit.

Acceptance: verify list, detail and saved-items behavior for hidden and visible items, plus authorized and unauthorized staff access. A passing list-query test alone cannot close G1-01. If the running backend is unavailable, report local checks and pending runtime verification separately.

This is a synthetic example, not a claim about any published production incident.
