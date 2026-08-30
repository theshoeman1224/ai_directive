# Decision records

Decision records preserve choices whose rationale and consequences should remain understandable after the surrounding discussion is gone. They may cover organizational, procedural, technical, or governance decisions.

Use [the decision template](../templates/decision.md). Keep each record concise and link it to affected plans, directives, communications, issues, or pull requests.

## IDs

Real records use monotonically increasing IDs: `DEC-001`, `DEC-002`, and so on. Search this directory, select the next number after the highest allocated ID, and never reuse or renumber an ID. Resolve duplicate IDs created on concurrent branches before merge. `DEC-000` is reserved for the example and is not an allocated decision.

Use filenames such as:

```text
DEC-001-require-review-for-generated-code.md
```

## Statuses

* `Proposed`: under consideration and not authoritative.
* `Approved`: accepted and authoritative from the recorded approval.
* `Rejected`: considered but not accepted.
* `Superseded`: replaced by a later decision.

Approval requires explicit metadata. Do not infer it from a merge or discussion. For a rejected proposal, add `Rejected By` and `Rejection Date`, and record why it was rejected without erasing the original proposal. Use `TBD` for any unknown fact.

## Supersession

Retain superseded decisions. Set the old record to `Superseded`, fill in `Superseded By`, and name the old record under `Supersedes` in the replacement. Preserve the original context, decision, rationale, alternatives, and consequences.

[EXAMPLE-decision.md](EXAMPLE-decision.md) is fictional and not authoritative.
