# complete-review-before-reporting

`complete-review-before-reporting` is a lightweight review skill for producing consolidated findings and driving review-after-fix cycles toward convergence.
It applies to code, documents, and other reviewable artifacts.

## Core rule

Complete the executable review work for the current review cycle before reporting findings.

The reviewer continues through the effective scope after finding issues, collects findings during the review, and presents them together once that cycle is complete.
On the earliest review of a target state, the reviewer also makes a reasonable effort to surface all material issues that are already discoverable instead of deferring them to later re-reviews.

## Review scope

The user's request and surrounding review task establish the starting target and review criteria.
The effective review scope also includes related canonical sources that are needed to judge the target's correctness, consistency, or intended behavior.

This does not imply an unconditional repository-wide scan.
Dependencies are followed only as far as needed for the review judgment, with a full-repository scan reserved for tasks or correctness questions that require one.

## What this skill controls

The skill controls:

- review sequencing and consolidated reporting timing;
- minimum scope expansion needed to inspect relevant canonical sources;
- completeness expectations for issues reasonably discoverable during the earliest review cycle; and
- convergence behavior across review, fix, and re-review cycles.

The surrounding review task remains responsible for choosing the review criteria and deciding which findings are worth reporting.

## Progress updates

Progress updates may describe review status or remaining work.
Individual findings are reserved for the consolidated review result unless the user explicitly requests incremental reporting.

## Pull request reviews

For a GitHub pull request review, post the consolidated outcome to the PR as a review submission or comment, including a clear result when no reportable findings are found.
Confirm the publication succeeded before declaring the PR review complete. If posting fails or is unavailable, report the review result and keep PR publication pending.

## Incomplete coverage

When some intended scope cannot be reviewed because required information, access, tooling, or execution is unavailable, the final review identifies that portion.

## Re-review and convergence

A requested re-review after changes to the same target remains part of the same convergence sequence unless the target or review criteria materially change.
The re-review verifies prior fixes, checks for regressions, and re-checks enough of the effective scope to determine whether relevant pre-existing issues remain.

A problem first reported later is treated as a prior-review miss when it already existed, was within the earlier effective scope, and was reasonably discoverable with the information and tools available at that time.
Problems introduced by later changes or made discoverable only by later information are valid new findings instead.

The sequence converges when prior findings are resolved and a completed re-review finds no additional reportable issues within the executable scope.

## Installation

Place `SKILL.md` where the target skill system loads skills from, or use the repository/package according to that system's installation method.
