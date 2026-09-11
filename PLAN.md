# Program plan

Status: DRAFT

Owner: TBD

Approved By: TBD

Approval Date: TBD

Last Updated: 2026-09-11

## Objective

Authorize teams to use company-approved AI tools for code generation while keeping human engineers accountable for source code merged into customer-deliverable branches or delivered to customers.

The proposed adoption model provides two approval paths: bounded use-case approval for normal adoption and a higher-assurance repository/module approval path for teams that demonstrate mature automated software-assurance controls.

## Scope

This plan covers the proposed adoption model for AI-assisted code generation, including sandbox evaluation, use-case approval, higher-assurance repository/module approval, correctness evidence, automated quality controls, and human responsibility for delivered source code.

Teams already have access to AI tools. This plan governs when source code generated with a company-approved AI tool may enter a customer-deliverable branch or be delivered to a customer. It does not govern account provisioning or how a team interacts with an approved tool.

This plan does not authorize customer-deliverable use by itself. Active directives remain the source of truth for operational instructions.

## Current priorities

* Define a lightweight process for teams to propose bounded code-generation use cases.
* Require the responsible sub-Integrated Product Team (sub-IPT) lead to sponsor each bounded-use proposal before a small Integrated Product Team (IPT)-level Subject Matter Expert (SME) board reviews it.
* Define the correctness evidence needed to approve a bounded use case.
* Define a higher-assurance path for repository/module-level code-generation approval based on demonstrated automated regression, coverage, static analysis, and enforceable quality gates.
* Set a clear boundary between sandbox evaluation and customer-deliverable use.

## Requirements

* Use only company-approved AI tools for source code intended for a customer-deliverable branch or customer delivery.
* Use bounded use-case approval under [DIR-003](directives/DIR-003-program-level-ai-use-case-approval.md) as the default adoption path.
* Allow broader repository/module-level code-generation approval only when the team satisfies the higher-assurance requirements in [DIR-004](directives/DIR-004-full-ai-code-generation-approval.md).
* Allow teams to develop and test proposed use cases in a sandbox with any AI tool and interaction method whose data-use level permits the sandbox activity.
* Do not merge sandbox output into a customer-deliverable branch or deliver it to a customer before the applicable approval path is satisfied.
* Keep use-case scope, tool portability, and reapproval conditions authoritative in [DIR-003](directives/DIR-003-program-level-ai-use-case-approval.md).
* Keep repository/module scope, automated quality controls, evidence requirements, change-size limits, ongoing monitoring, and suspension conditions authoritative in [DIR-004](directives/DIR-004-full-ai-code-generation-approval.md).
* Require correctness evidence for each bounded use case and demonstrable software-assurance evidence for repository/module-level approval.
* Require sponsorship from the sub-IPT lead responsible for the affected product or codebase before program-level review.
* Keep the proposing team and sub-IPT lead responsible for product-specific technical suitability, implementation, testing, and normal code review.
* Keep the IPT-level SME review focused on whether the proposed approval path has sufficient boundaries and evidence for the authority being requested.

## Operating model

The following statements are planning assumptions. They are not active instructions while this plan remains in `DRAFT`:

1. Teams identify and sandbox proposed code-generation use cases with AI tools whose data-use level permits the sandbox activity.
2. Teams keep sandbox output out of customer-deliverable branches and customer deliveries until the applicable approval requirements are satisfied.
3. For normal adoption, teams submit the proposed bounded use case, its boundaries, its repeatable workflow, and correctness evidence under DIR-003.
4. The responsible sub-IPT lead sponsors the proposal and confirms that it is appropriate for the team's product and codebase.
5. A small IPT-level SME board reviews the sponsored proposal for boundaries, evidence, and acceptable AI use.
6. Bounded use-case approval applies only to the reviewed use case and its stated boundaries, with tool portability and reapproval conditions as defined in DIR-003.
7. Teams seeking broader authority may instead request repository/module-level approval under DIR-004 after demonstrating mature automated regression, coverage, static analysis, enforceable quality gates, and the required evidence period.
8. Repository/module-level approval removes the need for separate use-case approval only within its explicitly approved repositories, modules, tools, and other recorded boundaries.
9. Human engineers and the sub-IPT retain responsibility for detailed design, implementation, testing, normal code review, and all additional review requirements regardless of approval path.

## Implementation plan

### Phase 1

Define the bounded-use proposal, sandbox, sponsorship, review, evidence, approval, and recording process. Confirm sub-IPT sponsorship responsibility and assign the review group and its authority before treating any proposed use case as authorized for customer-deliverable source code.

### Phase 2

Teams sandbox bounded use cases, obtain sub-IPT lead sponsorship, and submit correctness evidence for program review. Approved use cases enter the normal engineering workflow.

In parallel, define the measurable entry requirements for higher-assurance repository/module approval, including minimum coverage expectations and changed-code coverage requirements.

### Phase 3

Allow qualified teams to seek repository/module-level approval under DIR-004 after demonstrating the required automated controls and evidence. Review approvals when their scope or control environment changes and retire approvals that no longer match the work being performed.

## Active work

* Review and approval of this adoption strategy.
* Assignment of plan ownership and approval authority.
* Definition of sub-IPT sponsorship responsibilities, the IPT-level SME board, the submission process, and correctness criteria.
* Definition of the authoritative approval register and reapproval triggers.
* Definition of minimum coverage thresholds and changed-code coverage expectations for higher-assurance approval.
* Validation of the initial AI-generated Merge Request size limits using program evidence.
* Definition of quantitative suspension or revocation criteria as evidence becomes available.

## Risks

* Sensitive context may be copied from private discussions into this public repository.
* Draft material may be mistaken for approved direction if metadata is incomplete.
* Generated code may pass narrow tests without fitting repository-wide behavior, architecture, or conventions.
* Sandbox output may be merged or delivered before its applicable approval requirements are satisfied.
* Approval of one bounded use case may be mistaken for approval of unrelated uses.
* Repository/module-level approval may be incorrectly treated as authority outside its approved repositories, modules, tools, or quality-control boundaries.
* Automated quality gates may provide false confidence if their coverage, thresholds, or enforcement are weak.
* Reviewers may apply subjective approval criteria inconsistently across teams.

## Dependencies

* Named plan owner and approval authority: TBD.
* Sub-IPT sponsorship roles and the membership and authority of the IPT-level SME board: TBD.
* A documented path for proposing, reviewing, approving, and revisiting bounded use cases: TBD.
* A documented path for higher-assurance repository/module approval: [DIR-004](directives/DIR-004-full-ai-code-generation-approval.md).
* Verification methods appropriate to each use case and repository.
* Minimum coverage thresholds for higher-assurance approval: TBD.
* Changed-code coverage requirements for higher-assurance approval: TBD.
* An authoritative register for approved AI tools, use cases, repositories, and modules: TBD.

## Open questions

* Who owns this plan?
* Who selects the IPT-level SME board members, and what approval authority do they hold?
* What minimum correctness evidence is required before a bounded use case can be approved?
* What minimum code-coverage threshold is required for repository/module-level approval?
* Should newly modified or AI-generated code have a separate changed-code coverage threshold?
* What quantitative conditions should trigger suspension or revocation of repository/module-level approval?
* What changes to a bounded use case require a new review?
* Where will approved tools, use cases, repositories, and modules be recorded?
* How should teams identify AI-generated lines after human modification?

## Related decisions

None.

## Related directives

* [DIR-001: AI tool data and output usage](directives/DIR-001-ai-model-data-and-usage-policy.md)
* [DIR-002: Code generation for customer deliverables](directives/DIR-002-code-generation-customer-deliverables.md)
* [DIR-003: Program-level AI code-generation use-case approval](directives/DIR-003-program-level-ai-use-case-approval.md)
* [DIR-004: Full AI code-generation approval](directives/DIR-004-full-ai-code-generation-approval.md)
