# Directives

Directives contain approved instructions that workers may be expected to follow. The status line is the first authority check: only `ACTIVE` directives apply.

Use [the directive template](../templates/directive.md). State required actions without ambiguity, define scope, and provide completion or compliance criteria. Keep private organizational details behind descriptive placeholders.

## IDs

Real directives use monotonically increasing IDs: `DIR-001`, `DIR-002`, and so on. Search this directory, select the next number after the highest allocated ID, and never reuse or renumber an ID. Resolve duplicate IDs created on concurrent branches before merge. `DIR-000` is reserved for the example and is not an allocated directive.

## Lifecycle

* `DRAFT`: being written; no instruction is in force.
* `UNDER REVIEW`: submitted for review; no instruction is in force.
* `APPROVED`: approved but not yet effective.
* `ACTIVE`: effective and applicable within its stated scope.
* `SUPERSEDED`: replaced by another directive.
* `RETIRED`: withdrawn without a replacement.

An assistant must not infer `APPROVED` or `ACTIVE`. Those states require verified approval and effective-date information.

## Current records

The following directives are drafts. They are under review and impose no requirements:

* [DIR-001: Code generation for customer deliverables](DIR-001-code-generation-customer-deliverables.md)
* [DIR-002: Program-level AI code-generation use-case approval](DIR-002-program-level-ai-use-case-approval.md)

When a directive is retired, add `Retired By`, `Retirement Date`, and a short `Retirement Rationale`. Use `TBD` for any unknown fact rather than inventing lifecycle history.

## Supersession

Retain superseded directives. Mark the old record `SUPERSEDED`, fill in `Superseded By`, and name it under `Supersedes` in the replacement. Preserve its original purpose and instructions except for lifecycle metadata and links needed to show the relationship.

[EXAMPLE-directive.md](EXAMPLE-directive.md) is fictional, not active, and imposes no requirements.
