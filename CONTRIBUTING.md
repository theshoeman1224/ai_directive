# Contributing

Contributions must keep this repository useful as a public, durable governance record.

## Before editing

1. Read [AGENTS.md](AGENTS.md), [README.md](README.md), [CURRENT_STATE.md](CURRENT_STATE.md), and [PLAN.md](PLAN.md).
2. Inspect decisions and directives related to the change.
3. Decide which artifact owns the information. Avoid duplicate sources of truth.
4. Remove or replace information that is unsafe for a public repository.

## Make a change

For meaningful planning or governance changes, prefer:

```text
branch -> commit -> pull request -> review -> merge
```

Git history records document evolution. Pull-request discussion records review rationale. Document metadata records explicit approval. Capture meaningful decision rationale in a `DEC` record rather than leaving it only in pull-request comments.

Trivial typo and formatting fixes do not need excessive process. Changes to worker responsibilities, organizational direction, policy, priorities, or approvals require explicit review.

Use the files in [templates/](templates/) for new records. Before allocating an ID, search existing files and choose the next number after the highest ID of that type. Concurrent branches can produce duplicate IDs; resolve them before merge without renumbering records already on the primary branch.

## Approval and lifecycle changes

Do not infer approval from a merge, meeting, message, or request to draft. Record verified approvers and dates. Leave unknown values as `TBD` or a descriptive placeholder.

Never delete a superseded decision or directive. Update both sides of the relationship:

* the old record becomes `Superseded` for a decision or `SUPERSEDED` for a directive and names `Superseded By`,
* the replacement names `Supersedes`,
* related links remain navigable.

Only an approved directive may become `ACTIVE`. Only mark a communication `SENT` after it has actually been issued.

## Public-data review

Review the full diff before opening or merging a pull request. Look for names, identifiers, sensitive numbers, internal URLs, email headers, hidden source details, and private context copied into generated text. Use descriptive snake_case placeholders in angle brackets when a value must be supplied privately later.

Examples:

* `<program_name>`
* `<team_name>`
* `<poc_name>`
* `<internal_metric>`
* `<internal_source_reference>`

The prompt given to an AI assistant is not a public-release authorization.

## Review checklist

* [ ] The change belongs in a planning or governance repository.
* [ ] The diff contains no information inappropriate for public release.
* [ ] Status and approval metadata are accurate and explicit.
* [ ] Active instructions live in a directive, not only in a plan, note, or communication.
* [ ] Related records and links are updated.
* [ ] Historical rationale and superseded records remain intact.
* [ ] New IDs are unique and monotonically increasing.
* [ ] Link validation passes, or any narrow exclusion is justified.

## Link checks

The link-check workflow runs on pull requests and pushes to `main`. To investigate a failure, run the command documented in [README.md](README.md), inspect each failed URL, and replace dead or weak sources. If a valid site consistently blocks automated checks, add a narrow regular expression and explanation to [.lycheeignore](.lycheeignore).
