# Repository review findings: 2026-09-04

> NON-AUTHORITATIVE: This working list records review findings and their dispositions. It is not a decision, directive, or current plan.

Status: WORKING DRAFT

Owner: TBD

Review Date: 2026-09-04

Scope: Full-repository review of all committed Markdown content, performed 2026-09-04.

## How to use

Set each item's `Disposition` to `Fix` or `Ignored`. For ignored items, record the reason on the same line, for example `Ignored: <reason>`. Items remain listed either way, so this record shows what was consciously declined as well as what was corrected.

Confirmed `Fix` items go through the normal branch, commit, and pull-request process described in [CONTRIBUTING.md](../CONTRIBUTING.md). This file is not updated by those fixes; set `Status: Done` on each item as its fix merges.

## Index

| ID | Title | Category | Disposition | Status |
|---|---|---|---|---|
| 1 | Review board described three ways | Consistency conflict | Fix | Done |
| 2 | Level 3 definition is circular | Consistency conflict | Fix | Done |
| 3 | Vendor names conflict with sanitization policy | Consistency conflict | TBD | Open |
| 4 | Tool-portability rule stated in four places | Consistency conflict | TBD | Open |
| 5 | IPT, sub-IPT, and SME never expanded | Needs clarification | TBD | Open |
| 6 | "customer-deliverable branch" undefined | Needs clarification | TBD | Open |
| 7 | Safety-critical code scope gap | Needs clarification | TBD | Open |
| 8 | Contract confirmation has no owner | Needs clarification | TBD | Open |
| 9 | CURRENT_STATE status field undefined | Needs clarification | TBD | Open |
| 10 | Submission template status lifecycle undefined | Needs clarification | TBD | Open |
| 11 | Junior-developer heuristic has no anchored example | Needs clarification | TBD | Open |
| 12 | Two formulas for the approval standard | Needs clarification | TBD | Open |
| 13 | README automation phrasing | Needs clarification | TBD | Open |
| 14 | "Work around" security phrasing | Needs clarification | TBD | Open |
| 15 | Communication lifecycle between approval and merge | Needs clarification | TBD | Open |
| 16 | "Program IP" coverage of credentials undefined | Needs clarification | TBD | Open |
| 17 | No remediation guidance for committed sensitive data | Should be expanded | TBD | Open |
| 18 | No decision records for embedded decisions | Should be expanded | TBD | Open |
| 19 | Tagging feasibility risk missing from plan | Should be expanded | TBD | Open |
| 20 | Multi-sub-IPT use cases unaddressed | Should be expanded | TBD | Open |
| 21 | Review cadence never defined | Should be expanded | TBD | Open |
| 22 | Em dashes in EXAMPLE titles | Minor style | TBD | Open |
| 23 | EXAMPLE status outside documented lifecycle | Minor style | TBD | Open |
| 24 | Communication template status vs directory rule | Minor style | TBD | Open |
| 25 | PLAN internal duplication | Minor style | TBD | Open |
| 26 | Rules restated across five files | Minor style | TBD | Open |
| 27 | No LICENSE file | Worth deciding deliberately | TBD | Open |

## Consistency conflicts

### 1. Review board described three ways

* Where: [PLAN.md](../PLAN.md):28, [DIR-003](../directives/DIR-003-program-level-ai-use-case-approval.md):74, [CURRENT_STATE.md](../CURRENT_STATE.md):23
* Finding: The review body is called "a small cross-team subject-matter expert and point-of-contact group" in PLAN.md, "a small IPT-level SME board" in DIR-003, and "cross-team use-case review authority" in CURRENT_STATE.md, while the DIR-003 title says "Program-level".
* Reason: A reader cannot tell what organizational level owns approval. Program, IPT, and sub-IPT are different levels, so this is a real contradiction, not a wording preference. Membership, charter, and approval authority all depend on resolving it.
* Disposition: Fix. The board is IPT-level. Unified on the DIR-003 term "IPT-level SME board": PLAN.md:28, :42, :52, :74, :89, :97 and CURRENT_STATE.md:23 reworded; PLAN.md and CURRENT_STATE.md timestamps updated. DIR-003's "Program-level" title was kept, since it describes the program-wide effect of the approval rather than the board's organizational level.
* Status: Done

### 2. Level 3 definition is circular

* Where: [DIR-001](../directives/DIR-001-ai-model-data-and-usage-policy.md):29, :67, :89
* Finding: Line 29 assigns data-use levels to "Program-approved AI tools", but Level 3 at line 67 contains "All AI tools and services not separately approved", and line 89 says to prefer ChatGPT or Claude "when those services are approved for use".
* Reason: If unapproved tools count as Level 3, then "use only program-approved AI tools" (DIR-002:39) permits every tool on earth at Level 3, and the approval concept collapses. The repo must decide whether Level 3 means "approved for non-IP use" or "not approved, use prohibited". These are opposite policies.
* Disposition: Fix. Level 3 is now the default classification for tools that are not program-approved, permitted only for non-IP, non-deliverable activities and subject to all other applicable requirements. DIR-001 intro, Level 3 section, tool selection, restrictions, and verification reworded. Matching "program-approved" language aligned in DIR-002, DIR-003, and PLAN.md: sandbox evaluation now requires only that the tool's data-use level permit the sandbox activity, and the "use only program-approved AI tools" requirement now applies to source code destined for customer-deliverable branches or delivery.
* Status: Done

### 3. Vendor names conflict with sanitization policy

* Where: [DIR-001](../directives/DIR-001-ai-model-data-and-usage-policy.md):45, :57, :67, :89; [frontier AI pilot proposal](frontier-ai-devsecops-pilot-proposal.md):17
* Finding: DIR-001 names Poolside, Microsoft Copilot, ChatGPT, and Claude, while the pilot proposal uses `<current_internal_ai_tool>` for the same kind of information.
* Reason: Naming the program's Level 1 and Level 2 vendors in a public repository reveals procurement relationships, which the README warning covers under "program, project, customer, contract, and system names". The two files treat the same risk differently, so one of them is wrong.
* Disposition: TBD
* Status: Open

### 4. Tool-portability rule stated in four places

* Where: [PLAN.md](../PLAN.md):53, [DIR-002](../directives/DIR-002-code-generation-customer-deliverables.md):31, [DIR-003](../directives/DIR-003-program-level-ai-use-case-approval.md):35, :90
* Finding: The rule that an approved use case may run with any program-approved AI tool without reapproval appears in at least four locations.
* Reason: AGENTS.md says to keep each fact in one authoritative place. This is the most consequential rule in the strategy, and four copies will drift.
* Disposition: TBD
* Status: Open

## Needs clarification

### 5. IPT, sub-IPT, and SME never expanded

* Where: [PLAN.md](../PLAN.md):28, [DIR-003](../directives/DIR-003-program-level-ai-use-case-approval.md):61, :74, used throughout
* Finding: The acronyms IPT, sub-IPT, and SME are used throughout but never expanded or defined, and no glossary exists.
* Reason: This is a public repository read by outsiders and AI agents who lack the org chart. Expanding on first use or adding a short glossary costs three lines.
* Disposition: TBD
* Status: Open

### 6. "customer-deliverable branch" undefined

* Where: [PLAN.md](../PLAN.md):15, :37, :49; [DIR-002](../directives/DIR-002-code-generation-customer-deliverables.md):29, :41
* Finding: The term is used throughout the plan and directives but never defined.
* Reason: The entire sandbox boundary hangs on this term. If two teams disagree about which branches are customer-deliverable, the core control fails.
* Disposition: TBD
* Status: Open

### 7. Safety-critical code scope gap

* Where: [DIR-002](../directives/DIR-002-code-generation-customer-deliverables.md):35, :88
* Finding: Scope covers all customer-deliverable code, while line 88 lists "Safety-critical code approval criteria" as unresolved.
* Reason: If the criteria do not exist yet, the draft should carve safety-critical code out explicitly rather than leave readers to guess whether the directive already governs it.
* Disposition: TBD
* Status: Open

### 8. Contract confirmation has no owner

* Where: [DIR-002](../directives/DIR-002-code-generation-customer-deliverables.md):40
* Finding: "Confirm that the applicable contract permits AI-generated source code" names no role.
* Reason: An unowned required action is unverifiable, and the repo's own standard says completion criteria must be testable.
* Disposition: TBD
* Status: Open

### 9. CURRENT_STATE status field undefined

* Where: [CURRENT_STATE.md](../CURRENT_STATE.md):3
* Finding: The snapshot file carries `Status: DRAFT`, but no documented lifecycle defines what would move it out of DRAFT.
* Reason: Every other artifact has a documented lifecycle. Either define the field's meaning for a snapshot file or drop the field.
* Disposition: TBD
* Status: Open

### 10. Submission template status lifecycle undefined

* Where: [AI use-case submission template](../templates/ai-use-case-submission.md):7
* Finding: `Submission Status: DRAFT` exists with no defined set of statuses or transitions.
* Reason: Teams will invent their own values if the lifecycle is undefined.
* Disposition: TBD
* Status: Open

### 11. Junior-developer heuristic has no anchored example

* Where: [DIR-003](../directives/DIR-003-program-level-ai-use-case-approval.md):29; [PLAN.md](../PLAN.md):84
* Finding: The first-day-junior-developer standard is subjective, and the plan already lists inconsistent reviewer application as a risk without any mitigation.
* Reason: The heuristic is memorable, which is good, but without an anchored example of an approved use case, each SME board will draw its own line. One worked example in the template would do more than another paragraph of criteria.
* Disposition: TBD
* Status: Open

### 12. Two formulas for the approval standard

* Where: [PLAN.md](../PLAN.md):42; [DIR-003](../directives/DIR-003-program-level-ai-use-case-approval.md):27
* Finding: PLAN.md says "simple, bounded, demonstrated, and compliant"; DIR-003 says "simple, bounded, and demonstrated".
* Reason: Matching formulas act as a checksum in governance writing. A mismatch invites the question of which one is the real standard.
* Disposition: TBD
* Status: Open

### 13. README automation phrasing

* Where: [README.md](../README.md):5
* Finding: "The only initial automation checks links in Markdown files" reads awkwardly.
* Reason: "Only initial automation" is not a phrase a person writes. "The only automation currently checks links in Markdown files" says the same thing.
* Disposition: TBD
* Status: Open

### 14. "Work around" security phrasing

* Where: [frontier AI pilot proposal](frontier-ai-devsecops-pilot-proposal.md):27
* Finding: The phrase "work around version or installation constraints imposed by secured environments" appears in a public file.
* Reason: It can be misread as advising circumvention of security controls. "Operate within" says the same thing safely, and the proposal itself states that the pilot "would not relax security requirements".
* Disposition: TBD
* Status: Open

### 15. Communication lifecycle between approval and merge

* Where: [README.md](../README.md):50-53; [communications README](../communications/README.md):5
* Finding: README steps 10 to 13 record approval, merge, then "Preserve the final approved communication", then mark SENT. The communications README says the artifact is added "once its wording is approved", which sounds pre-merge.
* Reason: The two documents give different answers to when the canonical file appears.
* Disposition: TBD
* Status: Open

### 16. "Program IP" coverage of credentials undefined

* Where: [DIR-001](../directives/DIR-001-ai-model-data-and-usage-policy.md):25, :41
* Finding: Level 1 permits "program IP" as input, but whether that term covers credentials and secrets is never stated.
* Reason: Engineers will reasonably ask whether API keys and credentials count. One sentence closes a real leak path.
* Disposition: TBD
* Status: Open

## Should be expanded

### 17. No remediation guidance for committed sensitive data

* Where: [README.md](../README.md):7-22; [CONTRIBUTING.md](../CONTRIBUTING.md):38-50
* Finding: Prevention is covered thoroughly; nothing describes what to do after restricted information has been committed.
* Reason: PLAN.md:79 names "sensitive context may be copied from private discussions" as a risk. The missing half of the procedure is who to notify, whether history must be purged, and who decides. Prevention without response is half a policy.
* Disposition: TBD
* Status: Open

### 18. No decision records for embedded decisions

* Where: [decisions/](../decisions/); [DIR-001](../directives/DIR-001-ai-model-data-and-usage-policy.md):19, [DIR-002](../directives/DIR-002-code-generation-customer-deliverables.md):19, [DIR-003](../directives/DIR-003-program-level-ai-use-case-approval.md):19
* Finding: The three-level data-use model, the use-case approval model, and the `-AI` tagging convention live only inside directive drafts, and all three show `Related Decisions: None`.
* Reason: The repo's own flow says to create a DEC record when rationale should be preserved. Drafting the DEC records as Proposed now would give that rationale a durable home before approval.
* Disposition: TBD
* Status: Open

### 19. Tagging feasibility risk missing from plan

* Where: [DIR-002](../directives/DIR-002-code-generation-customer-deliverables.md):67; [PLAN.md](../PLAN.md):77-84
* Finding: DIR-002 requires AI tools to tag every generated line, but "tools may not apply the tag reliably" is absent from the plan's risk list.
* Reason: Tool compliance will be imperfect, and a missed tag is silent. The risk list already covers similar execution risks, so this one belongs next to them.
* Disposition: TBD
* Status: Open

### 20. Multi-sub-IPT use cases unaddressed

* Where: [DIR-003](../directives/DIR-003-program-level-ai-use-case-approval.md):61
* Finding: The sponsorship rule assumes one "sub-IPT lead responsible for the affected product or codebase".
* Reason: Shared codebases will produce proposals that affect two products. The rule needs a tiebreaker or a joint-sponsorship clause.
* Disposition: TBD
* Status: Open

### 21. Review cadence never defined

* Where: [DIR-001](../directives/DIR-001-ai-model-data-and-usage-policy.md):13, [DIR-002](../directives/DIR-002-code-generation-customer-deliverables.md):13, [DIR-003](../directives/DIR-003-program-level-ai-use-case-approval.md):13
* Finding: Every directive has `Review Date: TBD`, and no document defines what triggers a review or how often one occurs.
* Reason: A field with no defined semantics invites people to leave it TBD forever.
* Disposition: TBD
* Status: Open

## Minor style

### 22. Em dashes in EXAMPLE titles

* Where: [EXAMPLE-directive](../directives/EXAMPLE-directive.md):1, [EXAMPLE-decision](../decisions/EXAMPLE-decision.md):1, [EXAMPLE-communication](../communications/EXAMPLE-communication.md):1, [notes README](README.md):13
* Finding: The example titles use the pattern `EXAMPLE — NOT ACTIVE` with additional em dashes, and the notes README uses an em dash as a separator.
* Reason: Em dash use is a known AI tell, and these are the most visible files to a new reader. `EXAMPLE (NOT ACTIVE): DIR-000` works fine.
* Disposition: TBD
* Status: Open

### 23. EXAMPLE status outside documented lifecycle

* Where: [directives README](../directives/README.md):13-18; [EXAMPLE-directive](../directives/EXAMPLE-directive.md):3
* Finding: `Status: EXAMPLE — NOT ACTIVE` is not among the six documented directive lifecycle states.
* Reason: Harmless, but one sentence noting that example files use a status outside the lifecycle would prevent confusion.
* Disposition: TBD
* Status: Open

### 24. Communication template status vs directory rule

* Where: [communication template](../templates/communication.md):4; [communications README](../communications/README.md):5
* Finding: The template starts at `Status: TBD`, while the directory README says files are added only once approved, with `Status: APPROVED`.
* Reason: The template suggests a state the directory forbids. Default it to APPROVED or drop the field.
* Disposition: TBD
* Status: Open

### 25. PLAN internal duplication

* Where: [PLAN.md](../PLAN.md):32-43, :46-54
* Finding: The Requirements list of nine bullets and the Operating model of seven numbered assumptions restate the same content.
* Reason: This is exactly the divergence AGENTS.md warns about, duplicated within a single file.
* Disposition: TBD
* Status: Open

### 26. Rules restated across five files

* Where: [AGENTS.md](../AGENTS.md), [README.md](../README.md), [CONTRIBUTING.md](../CONTRIBUTING.md), [directives README](../directives/README.md), [decisions README](../decisions/README.md)
* Finding: The public-data rules and the ID and supersession rules are restated in five places with slightly different example lists.
* Reason: Per-directory convenience is defensible, but the normative text should live once, with the other documents linking to it.
* Disposition: TBD
* Status: Open

## Worth deciding deliberately

### 27. No LICENSE file

* Where: repository root
* Finding: The public repository has no LICENSE file.
* Reason: Absence means "all rights reserved" by default. That may be intentional for governance content, but it should be a choice, not an omission.
* Disposition: TBD
* Status: Open
