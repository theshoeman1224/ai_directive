# AI agent instructions

These instructions govern OpenCode, ChatGPT, Codex, and similar assistants working in this public planning and governance repository.

## Required reading

Before substantial work, read in this order:

1. `AGENTS.md`
2. `README.md`
3. `CURRENT_STATE.md`
4. `PLAN.md`

Then inspect the decisions and directives relevant to the requested change. Search before creating a record.

## Source of truth

Chat conversations, meetings, brainstorming, and temporary notes are working context. Repository content on the primary branch is the durable record.

Treat `notes/` as non-authoritative. A discussion does not become approved policy by being recorded. Do not silently reinterpret an approved decision or directive. When current intent conflicts with an existing approved record, preserve the old record and create or update the proper replacement and lifecycle links.

## Public-data boundary

This repository is PUBLIC. Before creating or modifying any file, inspect all supplied context for information that may be proprietary, identifying, contractual, program-specific, export-controlled, classified, or otherwise inappropriate to publish.

Replace a necessary private value with a descriptive placeholder. Prefer removing unnecessary specificity entirely. Never invent a sanitized replacement and never assume that prompt content is safe to commit. Prompt visibility and repository visibility are different security boundaries. When uncertain, sanitize.

Examples:

Original:

```text
The <actual named program> has 327 engineers.
```

Repository version:

```text
<program_name> has approximately <engineer_count> engineers.
```

Original:

```text
Jane Smith and John Doe will approve submissions.
```

Repository version:

```text
<poc_1> and <poc_2> will approve submissions.
```

Original:

```text
The contract is worth $1.2 billion.
```

Repository version:

```text
The contract is valued at approximately <contract_value>.
```

Use descriptive snake_case placeholders inside angle brackets.

Good:

* `<program_name>`
* `<team_name>`
* `<poc_name>`
* `<contract_value>`

Bad:

* `REDACTED`
* `SECRET`
* `COMPANY_A`
* `John_Doe`

The placeholder should tell a private author what to insert later without exposing part of the value.

## Historical integrity

* Preserve every existing `DEC` and `DIR` ID.
* Never reuse or renumber an allocated ID.
* Retain superseded records.
* Update both `Superseded By` and `Supersedes` relationships.
* Preserve meaningful rationale instead of rewriting history to match the current position.
* Maintain links among plans, decisions, directives, communications, issues, and pull requests.
* Resolve duplicate IDs introduced by concurrent branches before merge.

Do not delete an old decision or directive because it is no longer active.

## Approval integrity

Never invent approvers, approval dates, effective dates, worker names, decision outcomes, or historical actions. Use `TBD` or an appropriate placeholder when a value is unknown.

An assistant may create a directive with `Status: DRAFT` or a decision with `Status: Proposed`. It may change a decision to `Approved`, a directive or communication to `APPROVED`, or a directive to `ACTIVE` only when the user clearly supplies the approval outcome and required metadata. A merged pull request alone is not approval.

## Editing workflow

When asked to modify a plan:

1. Determine whether the request affects only `PLAN.md` or also needs a decision, directive, `CURRENT_STATE.md` update, or communication.
2. Search existing decisions and directives before creating a new one.
3. Keep each fact in one authoritative place and link to it elsewhere.
4. Sanitize content before writing.
5. Preserve IDs, rationale, lifecycle metadata, and related links.
6. Leave every unknown field as `TBD` or a descriptive placeholder.
7. Check that draft material cannot be mistaken for an active instruction.
8. Run link validation when links or Markdown files change.
9. Summarize meaningful edits and remaining `TBD` fields.

Optimize Markdown for humans first. Use the existing templates and plain document structure. Keep process proportional to the change. This repository does not need custom parsers, databases, large schemas, complicated metadata, or generators.

## Directives and communications

Directives are the source of truth for approved operational instructions to workers. Only `ACTIVE` directives apply. Keep action language explicit, scope clear, and completion criteria testable.

`AGENTS.md` and `CONTRIBUTING.md` govern contributors and assistants maintaining this repository. They apply even when no operational directive is active and do not create organizational policy outside repository maintenance.

Assistants may draft communications, but `communications/` should retain only the canonical final approved wording. Do not create a file for every minor draft revision. If the underlying directive changes substantially, update the directive, decision, and communication relationships. A communication does not replace the directive or decision it announces.

## Public research

When requested research informs repository content:

* Prefer authoritative, publicly accessible sources.
* Use descriptive Markdown link text.
* Keep links that materially support claims.
* Use `<internal_source_reference>` for a necessary private source and do not reveal its name.
* Confirm links are suitable for automated checking where practical.

Never replace an unavailable internal source with an unrelated public URL.

## Completion check

Before reporting work complete, confirm that:

* no added detail appears unsafe for public release,
* approval and activity states match verified facts,
* no example or draft can be mistaken for an active directive,
* current-state and related links reflect the change,
* historical records remain available,
* changed links pass the repository check or have a documented narrow exclusion.
