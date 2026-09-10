# Planning and governance workspace

This public repository is the durable record for planning and governance work. It holds intended direction, decision rationale, approved instructions, final significant communications, and non-authoritative working notes. Git history and pull requests preserve how that record changed.

This repository contains documentation only. Application code, dashboards, databases, APIs, messaging integrations, workflow engines, and scheduled automation do not belong here. The only automation currently checks links in Markdown files.

## Public repository warning

Everything committed here should be treated as public. This repository is not a safe location for proprietary, identifying, contractual, program-specific, export-controlled, classified, or otherwise restricted information.

Before committing, review the diff for:

* real names and contact details,
* program, project, customer, contract, and system names,
* internal organizational or account identifiers,
* contract values, financial figures, headcounts, and non-public metrics,
* internal URLs, server names, and source references,
* pasted email headers or hidden context carried into generated text.

Replace necessary private values with descriptive placeholders such as `<program_name>`, `<poc_name>`, `<contract_value>`, or `<internal_url>`. Remove unnecessary specificity instead of redacting part of it. Never invent a substitute value.

AI sanitization is an additional safeguard, not a substitute for human review.

## Information architecture

| Artifact | Purpose | Authority |
| --- | --- | --- |
| [PLAN.md](PLAN.md) | Current intended direction, priorities, risks, and open questions | Authoritative for the current plan when its metadata shows the required approval |
| [CURRENT_STATE.md](CURRENT_STATE.md) | Short briefing on active, approved, blocked, and upcoming work | A current snapshot; it points to authoritative records rather than replacing them |
| [decisions/](decisions/) | Durable decisions and the rationale behind them | Approved decision records are authoritative for the decisions they record |
| [directives/](directives/) | Instructions that workers may be expected to follow | Only records marked `ACTIVE` are active instructions |
| [communications/](communications/) | Final approved wording of significant communications | Authoritative for the wording issued, but not a replacement for a related decision or directive |
| [notes/](notes/) | Meeting notes, research, brainstorming, and temporary analysis | Non-authoritative; content may be incomplete, incorrect, or obsolete |
| [templates/](templates/) | Starting points for consistent documents | Reference material only |
| [AGENTS.md](AGENTS.md) and [CONTRIBUTING.md](CONTRIBUTING.md) | Instructions for maintaining this repository | Apply to repository contributors; they are not operational directives for workers |

Approval is explicit. Important documents record `Status`, `Owner`, `Approved By`, `Approval Date`, and, when relevant, `Effective Date`. A merge or discussion alone does not confer approval. Unknown values remain `TBD` or use a descriptive placeholder.

## Working flow

1. Discuss or investigate.
2. Capture rough information under `notes/` if useful.
3. Sanitize all information intended for this public repository.
4. Update `PLAN.md` when intended direction changes.
5. Create a `DEC` record when meaningful rationale should be preserved.
6. Create or update a `DIR` record when workers will be expected to act.
7. Draft the significant communication without storing a file for every revision.
8. Open a pull request.
9. Review the content, links, and public-data safety.
10. Record explicit approval metadata when approval has actually occurred.
11. Merge.
12. Preserve the final approved communication under `communications/`.
13. Mark the communication `SENT` only after it is issued.

For meaningful changes, use a branch, commit, pull request, review, and merge. [CONTRIBUTING.md](CONTRIBUTING.md) describes the lightweight contribution process.

## IDs and history

Decision IDs use `DEC-001`, `DEC-002`, and so on. Directive IDs use `DIR-001`, `DIR-002`, and so on. Choose the next number after the highest ID already present, never reuse or renumber an ID, and resolve duplicate IDs across branches during pull-request review. Files prefixed `EXAMPLE-` use `DEC-000` or `DIR-000`; those examples do not allocate a real ID.

Superseded records remain in place. Use `Superseded` for a decision or `SUPERSEDED` for a directive, fill in `Superseded By`, and set `Supersedes` in the replacement. Preserve the original rationale and update only lifecycle metadata and links needed to describe the new relationship.

## Final communications

The communications directory holds one canonical, final approved version of each significant communication. Pull-request and Git history provide drafting history. Use `APPROVED` before issue and `SENT` only after issue. The related directive or decision remains the authority for policy and required action.

## AI assistants

AI assistants must read [AGENTS.md](AGENTS.md) before substantial work. They must treat prompts and conversations as working context, inspect relevant existing records, sanitize content before writing, preserve historical IDs and rationale, and leave unknown approval facts as `TBD`. An assistant may draft a record but may not infer that it is approved or active.

## Link validation

The [link-check workflow](.github/workflows/link-check.yml) runs [lychee](https://github.com/lycheeverse/lychee) against Markdown files on pull requests and pushes to `main`. It checks relative links and public HTTP or HTTPS links.

Run the same check locally after installing `lychee`:

```sh
lychee --root-dir . --no-progress --max-retries 3 --retry-wait-time 2 './**/*.md'
```

Known false positives belong in [.lycheeignore](.lycheeignore), one narrowly scoped regular expression per line with a comment explaining why. Before adding an exclusion, open the URL manually, confirm the cited content still supports the claim, and determine whether the failure is caused by a dead link, authentication, bot blocking, rate limiting, or a temporary outage. Prefer replacing a poor source over excluding it.

## Tracking scope

Markdown is the initial planning and tracking system. GitHub Issues or Projects may be adopted later if active work becomes hard to track, ownership needs more visibility, cross-team task management becomes necessary, or open actions grow substantially. They are not required now.
