---
name: complete-review-before-reporting
description: Complete the available code-review scope before reporting findings. Continue reviewing after finding issues, collect findings throughout the review, and present them together once the review work is complete.
---

# Complete Review Before Reporting

Use this skill when performing a code review whose findings should be delivered as a consolidated result.

## Purpose

Complete the review work for the current review unit before reporting its findings.

This skill governs review sequencing and reporting timing.
The surrounding review task continues to determine what to inspect, which review criteria to apply, and which findings are worth reporting.

## Core rule

For each review unit, inspect the full review scope that can reasonably be reviewed before presenting findings.

Continue reviewing after finding the first issue and after accumulating multiple issues.
Collect findings throughout the review, then present the collected findings together in one review result after the review work is complete.

## Review scope

Use the scope established by the user's request and the surrounding review task.

A full-repository scan applies when the review task itself calls for one.
A narrower review remains narrow when that is the requested or established scope.

The review is complete when the executable review work for that scope has been performed.

When part of the scope cannot be reviewed because required information, access, tooling, or execution is unavailable, identify that portion in the final result.

## Reporting

During the review, retain individual findings until the review work is complete.

Progress updates may describe review status or remaining work while keeping individual findings for the consolidated review result.

Once the executable review work is complete:

- present the findings from that review unit together;
- include any portion of the intended scope that could not be reviewed;
- treat the report as the completed result for that review unit.

## Subsequent reviews

A user-requested re-review after changes is a new review unit.
Apply the same completion-before-reporting process to that new unit.

An explicit user request for incremental findings takes precedence over consolidated reporting.

## Final check

Before reporting code-review findings, confirm:

- the established review scope has been examined as fully as the available context and tools allow;
- review continued after earlier findings were discovered;
- the executable review work for the current review unit is complete;
- the findings are collected into one consolidated review result;
- any portion that could not be reviewed is identified.
