# Current state

Snapshot Date: 2026-09-11

Owner: TBD

## Currently active

The documentation structure and public-repository safeguards are in place for review. [PLAN.md](PLAN.md) and four related directives describe a draft AI code-generation adoption strategy. They are not approved and create no active instruction.

## Approved

No plans, decisions, directives, or communications are recorded as approved.

## Work underway

* Human review of the repository structure, templates, and sanitization rules.
* Assignment of ownership and approval authority.
* Review of the draft AI code-generation assumptions in [PLAN.md](PLAN.md).
* Review of [DIR-001](directives/DIR-001-ai-model-data-and-usage-policy.md), [DIR-002](directives/DIR-002-code-generation-customer-deliverables.md), [DIR-003](directives/DIR-003-program-level-ai-use-case-approval.md), and [DIR-004](directives/DIR-004-full-ai-code-generation-approval.md).
* Definition of sub-Integrated Product Team (sub-IPT) sponsorship responsibilities, the proposed Integrated Product Team (IPT)-level Subject Matter Expert (SME) review authority, and correctness criteria.
* Definition of minimum coverage thresholds and changed-code coverage requirements for the higher-assurance repository/module approval path.
* Development of a [working proposal for a limited frontier AI DevSecOps pilot](notes/frontier-ai-devsecops-pilot-proposal.md).

## Blocked

* Plan approval is blocked until the owner, approver, sub-IPT sponsorship responsibilities, review authority, and correctness criteria are known.
* Directive activation is blocked until ownership, approval metadata, effective dates, the approval registers, and unresolved source-tagging rules are known.
* DIR-004 activation is additionally blocked until minimum coverage thresholds and changed-code coverage expectations are defined.

## Needs attention

* Review the draft plan and directives for information inappropriate for public release.
* Replace `TBD` fields only with verified information.
* Validate the proposed 500 added / 2,000 deleted production-SLOC limits using review and defect data as evidence becomes available.

## Next major actions

1. Complete public-release and governance review.
2. Assign the plan owner and approval authority.
3. Confirm sub-IPT sponsorship responsibilities and assign the use-case review authority.
4. Define minimum correctness evidence.
5. Define minimum coverage thresholds and changed-code coverage expectations for repository/module-level approval.
6. Resolve the source-tagging and approval-register questions.
7. Record an explicit decision if the strategy is approved.
8. Add approval and effective-date metadata only after the required approvals occur.

## Active directives

None.

The following drafts are under review and impose no requirements:

* [DIR-001: AI tool data and output usage](directives/DIR-001-ai-model-data-and-usage-policy.md)
* [DIR-002: Code generation for customer deliverables](directives/DIR-002-code-generation-customer-deliverables.md)
* [DIR-003: Program-level AI code-generation use-case approval](directives/DIR-003-program-level-ai-use-case-approval.md)
* [DIR-004: Full AI code-generation approval](directives/DIR-004-full-ai-code-generation-approval.md)

[The directive example](directives/EXAMPLE-directive.md) is also not active and imposes no requirements.
