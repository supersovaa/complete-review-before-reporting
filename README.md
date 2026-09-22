# complete-review-before-reporting

`complete-review-before-reporting` is a lightweight code-review skill for producing one consolidated review result after the review scope has been examined.

## Core rule

Complete the executable review work for the current review unit before reporting findings.

The reviewer continues through the established scope after finding issues, collects findings during the review, and presents them together once the review work is complete.

## What this skill controls

The skill controls review sequencing and reporting timing.

The surrounding review task remains responsible for:

- deciding the review scope;
- choosing review criteria;
- deciding which findings matter;
- determining how deeply related code should be investigated.

This keeps the skill focused on preventing partial review results from being reported as though the review were already complete.

## Progress updates

Progress updates may describe review status or remaining work.
Individual findings are reserved for the consolidated review result unless the user explicitly requests incremental reporting.

## Incomplete coverage

When some intended scope cannot be reviewed because required information, access, tooling, or execution is unavailable, the final review identifies that portion.

## Re-review

A requested re-review after changes starts a new review unit and follows the same completion-before-reporting process.

## Installation

Place `SKILL.md` where the target skill system loads skills from, or use the repository/package according to that system's installation method.
