---
name: complete-review-before-reporting
description: Complete the available review scope before reporting findings and drive repeated reviews toward convergence. Apply to code, documents, and other reviewable artifacts, including related canonical sources needed to judge correctness.
---

# Complete Review Before Reporting

Use this skill when reviewing code, documents, or other artifacts whose findings should be delivered as a consolidated result.

## Purpose

Complete the review work for the current review cycle before reporting its findings, and make repeated review-after-fix cycles converge instead of surfacing pre-existing issues a few at a time.

This skill governs review sequencing, reporting timing, the minimum scope expansion needed to judge correctness, and convergence behavior.
The surrounding review task continues to determine the starting target, the review criteria to apply, and which findings are worth reporting.

## Core rule

For each review cycle, inspect the full review scope that can reasonably be reviewed before presenting findings.

Continue reviewing after finding the first issue and after accumulating multiple issues.
Collect findings throughout the review, then present the collected findings together after the executable review work for that cycle is complete.

On the earliest review cycle for a target state, make a reasonable effort to identify all material issues that are discoverable from the available information and tools within the required review scope.
Do not intentionally defer discoverable issues to later re-reviews.

## Review scope

Start from the scope established by the user's request and the surrounding review task.
Keep unrelated scope narrow, but do not treat the immediate diff or named artifact as the entire review scope when its correctness depends on other authoritative material.

Include related canonical sources that are needed to judge the target's correctness, consistency, or intended behavior.
Follow those dependencies only as far as needed to make that judgment.
A full-repository scan is required only when the review task calls for one or when correctness cannot reasonably be determined without it.

The review cycle is complete when the executable review work for that effective scope has been performed.

When part of the scope cannot be reviewed because required information, access, tooling, or execution is unavailable, identify that portion in the final result.

## Initial-review completeness

Treat a problem found only in a later review as a prior-review miss when all of the following were already true during the earlier review:

- the problem already existed in the earlier target state;
- it fell within the effective review scope required by this skill; and
- it was reasonably discoverable from the information, access, and tools available at that time.

Do not classify a problem as a prior-review miss when it was introduced by later changes, became reviewable only after later changes, or depends on information that was not previously available.

This rule requires reasonable completeness, not perfect defect detection.

## Reporting

During a review cycle, retain individual findings until the executable review work for that cycle is complete.

Progress updates may describe review status or remaining work while keeping individual findings for the consolidated review result.

Once the executable review work is complete:

- present the findings from that review cycle together;
- include any portion of the intended scope that could not be reviewed; and
- make clear whether the review sequence has converged or further fixes and re-review are required.

## Subsequent reviews and convergence

A user-requested re-review after changes to the same target is part of the same convergence sequence unless the user materially changes the review target or criteria.

For each re-review:

- verify that previously reported findings were addressed;
- inspect the changes for regressions or newly introduced problems;
- re-check enough of the effective review scope to determine whether relevant pre-existing problems remain; and
- complete that review cycle before reporting its findings.

The review sequence has converged when previously reported findings are resolved and a completed re-review finds no additional reportable issues within the executable review scope.

An explicit user request for incremental findings takes precedence over consolidated reporting.

## Final check

Before reporting review findings, confirm:

- the effective review scope, including required related canonical sources, has been examined as fully as the available context and tools allow;
- review continued after earlier findings were discovered;
- reasonably discoverable issues were not intentionally deferred to a later review cycle;
- the executable review work for the current cycle is complete;
- the findings are collected into one consolidated review result;
- any portion that could not be reviewed is identified; and
- for a re-review, convergence has been assessed and any newly found pre-existing issue has been considered against the prior-review-miss rule.
