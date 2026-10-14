---
name: adversarial-engineering
description: Use evidence-backed adversarial review gates to manage non-trivial engineering changes from plan through diff review to acceptance. Use for multi-file changes, migrations, permission-sensitive work, or explicit adversarial review requests; scale the review to the actual risk.
license: MIT
metadata:
  author: CercaTrovato
  version: "1.0.0"
---

# Adversarial Engineering

Find the counterexample before it becomes a release defect. Separate building, challenging, and proving; close findings with evidence rather than reviewer agreement.

## Scope and authority

Follow the user's scope, repository instructions, and execution permissions. This skill grants no permission to deploy, publish, send messages, expose data, or change production. Do not import one project's architecture, model choices, approval rules, or incidents into another project.

For a typo or similarly low-risk edit, use a brief relevant check. Do not create plans, tests, agents, or process documents merely to satisfy ceremony. Stronger local gates still apply. For an explicit review-only request, report findings; do not start implementing fixes without authorization.

## Set the review boundary

Identify the requested outcome, constraints, affected consumers, acceptance criteria, and the exact artifact or revision being reviewed. State unknowns as unknowns. Choose checks that could disprove the proposed result.

For substantial work, use an independent reviewer when available and permitted. Give the reviewer the request, constraints, plan or diff, relevant contracts, and raw evidence—not the answer you want. Ask for counterexamples and inspection limits. Keep review read-only by default; the primary agent owns integration and finding disposition.

For cross-component changes, migrations, or sensitive permissions, use two distinct perspectives when available: (1) correctness, contracts, permissions and state; (2) missing consumers, migration, regressions and unnecessary complexity. Split implementation into independently verifiable batches. Assign non-overlapping files to parallel writers and review the integrated result.

Select models using the host's available models and the user's cost/tier policy; do not hard-code model names or invent capabilities. With no independent reviewer, label the work **self-review**. Where local policy requires independent review, self-review cannot satisfy it: report that gate as blocked and continue only work that does not depend on it. Otherwise a gate may pass through self-review with adequate evidence and explicit limits; missing delegation alone is not a blocker.

## Gate 1 — Challenge the plan

Before finalizing a substantive design or starting its implementation, inspect:

- Product, safety, compliance and scope constraints: what prohibited outcome could this introduce?
- Architecture, API and data contracts: which callers, readers, writers or versions would disagree?
- Permissions, privacy and state transitions: who can trigger each transition, and what happens on retries, partial failure or concurrent execution?
- Coverage of change: which UI, export, background task, migration, rollback or old-data path is missing?
- Complexity: is there a smaller solution that meets the same requirements? Is any abstraction or migration speculative?

Require concrete failure paths, not a generic checklist of possibilities. Resolve blockers before the dependent implementation. If the request is only to audit an existing diff, mark this gate not applicable instead of fabricating a retrospective plan review.

## Gate 2 — Challenge the change

After a coherent implementation batch and before merging it, review the actual diff plus necessary surrounding code. Check behavior against the accepted requirements and contracts. Trace affected consumers, error paths, boundaries and permission checks. Add a focused security perspective when authentication, privacy, injection or trust boundaries change.

Use a host-provided code/security review capability if available; otherwise perform that review directly. No named plugin is required. For a new package, review all shipped files as the initial diff. Do not use a generic approval, syntax check, or green unit suite as a substitute for examining behavior.

## Gate 3 — Prove the bounded claim

Before saying complete, fixed, verified or passed, tie each important acceptance claim to current evidence:

- Executable changes: run relevant tests or reproduce the behavior. Record the command, scope, result and revision; check that assertions actually ran. A zero exit code alone may be an empty test run.
- Runtime, integration or UI claims: inspect the relevant running path when feasible. Static checks do not prove deployment, database effects or platform-specific behavior. For writes, verify authoritative readback when authorized.
- Documentation or skill packages: inspect delivered artifacts, links, discovery and realistic usage where applicable. Structural validation alone does not establish behavioral quality.

Record what was not checked, why, and the smallest remaining verification step. Never turn unavailable evidence into a pass. A green suite proves only the behavior it covers. When an independent acceptance reviewer is used, they must inspect raw evidence or reproduce checks, rather than echo the builder's summary.

## Close findings and stop

Use two severities: **blocker** (a concrete requirement violation, defect or unresolved acceptance-critical uncertainty) and **advisory** (a non-blocking improvement). A hypothetical concern without support is an investigation question, not a proven defect. Track only useful fields:

`ID | gate | severity | location | failure path/evidence | disposition | verification`

Disposition is **fixed**, **rejected with evidence**, or **unresolved**. Rejection must address the failure path; confidence or a vote is not evidence. Advisory deferrals include a reason. Unresolved blockers prevent the dependent gate from passing. If a decision requires the owner, ask only for that decision and continue independent work.

Run one initial review and a focused follow-up for changed findings. If a blocker remains, report it as unresolved; do not loop until a reviewer says yes or relabel it as a pass. Further cycles require new evidence or a materially revised fix. Reopen other checks only when changes, failures or stale evidence justify them. Do not expand into unrelated cleanup or repeatedly run already valid checks to manufacture progress.

Report gate status (**passed**, **blocked**, **not applicable**, or **not run**) separately from review mode (**independent review** or **self-review**). Include the inspected revision/scope, resolved and unresolved findings, evidence and limits. Completion requires all applicable gates to pass under the local policy; describe partial progress precisely otherwise.

For sample reviewer prompts and a worked finding, read [references/review-examples.md](references/review-examples.md) when useful.
