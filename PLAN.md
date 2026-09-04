# Program plan

Status: DRAFT

Owner: TBD

Approved By: TBD

Approval Date: TBD

Last Updated: 2026-09-04

## Objective

Authorize teams to use company-approved AI tools for bounded code-generation use cases while keeping human engineers accountable for source code merged into customer-deliverable branches or delivered to customers.

## Scope

This plan covers the proposed adoption model for AI-assisted code generation, including sandbox evaluation, use-case approval, correctness evidence, and human responsibility for delivered source code.

Teams already have access to AI tools. This plan governs when source code generated with a company-approved AI tool may enter a customer-deliverable branch or be delivered to a customer. It does not govern account provisioning or how a team interacts with an approved tool.

This plan does not authorize customer-deliverable use by itself. Active directives remain the source of truth for operational instructions.

## Current priorities

* Define a lightweight process for teams to propose bounded code-generation use cases.
* Require the responsible sub-IPT lead to sponsor each proposal before a small IPT-level SME board reviews it.
* Define the correctness evidence needed to approve a use case.
* Set a clear boundary between sandbox evaluation and customer-deliverable use.

## Requirements

* Use only company-approved AI tools for source code intended for a customer-deliverable branch or customer delivery.
* Approve bounded use cases, not general permission to generate code.
* Allow teams to develop and test proposed use cases in a sandbox with any AI tool and interaction method whose data-use level permits the sandbox activity.
* Do not merge sandbox output into a customer-deliverable branch or deliver it to a customer before the use case is approved.
* Allow an approved use case to run with any company-approved AI tool without another use-case approval.
* Require correctness evidence for each proposed use case.
* Require sponsorship from the sub-IPT lead responsible for the affected product or codebase before program-level review.
* Keep the proposing team and sub-IPT lead responsible for product-specific technical suitability, implementation, testing, and normal code review.
* Keep the IPT-level SME review focused on whether the proposed use is simple, bounded, demonstrated, and compliant.

## Operating model

The following statements are planning assumptions. They are not active instructions while this plan remains in `DRAFT`:

1. Teams identify and sandbox proposed code-generation use cases with AI tools whose data-use level permits the sandbox activity.
2. Teams keep sandbox output out of customer-deliverable branches and customer deliveries until the use case is approved.
3. Teams submit the proposed use case, its boundaries, its repeatable workflow, and correctness evidence.
4. The responsible sub-IPT lead sponsors the proposal and confirms that it is appropriate for the team's product and codebase.
5. A small IPT-level SME board reviews the sponsored proposal for simplicity, boundaries, evidence, and acceptable AI use.
6. Approval applies only to the reviewed use case and its stated boundaries. The team may run that approved use case with any company-approved AI tool.
7. Human engineers and the sub-IPT retain responsibility for detailed design, implementation, testing, and normal code review.

## Implementation plan

### Phase 1

Define the use-case proposal, sandbox, sponsorship, review, evidence, approval, and recording process. Confirm sub-IPT sponsorship responsibility and assign the review group and its authority before treating any proposed use case as authorized for customer-deliverable source code.

### Phase 2

Teams sandbox bounded use cases, obtain sub-IPT lead sponsorship, and submit correctness evidence for program review. Approved use cases enter the normal engineering workflow.

### Phase 3

Review approved use cases when their scope changes and retire approvals that no longer match the work being performed.

## Active work

* Review and approval of this adoption strategy.
* Assignment of plan ownership and approval authority.
* Definition of sub-IPT sponsorship responsibilities, the IPT-level SME board, the submission process, and correctness criteria.
* Definition of the authoritative approval register and reapproval triggers.

## Risks

* Sensitive context may be copied from private discussions into this public repository.
* Draft material may be mistaken for approved direction if metadata is incomplete.
* Generated code may pass narrow tests without fitting repository-wide behavior, architecture, or conventions.
* Sandbox output may be merged or delivered before its use case is approved.
* Approval of one use case may be mistaken for approval of unrelated uses.
* Reviewers may apply subjective approval criteria inconsistently across teams.

## Dependencies

* Named plan owner and approval authority: TBD.
* Sub-IPT sponsorship roles and the membership and authority of the IPT-level SME board: TBD.
* A documented path for proposing, reviewing, approving, and revisiting bounded use cases: TBD.
* Verification methods appropriate to each use case and repository.
* An authoritative register for approved AI tools and use cases: TBD.

## Open questions

* Who owns this plan?
* Who selects the IPT-level SME board members, and what approval authority do they hold?
* What minimum correctness evidence is required before a use case can be approved?
* What changes to a use case require a new review?
* Where will approved tools and use cases be recorded?
* How should teams identify AI-generated lines after human modification?

## Related decisions

None.

## Related directives

* [DIR-001: AI tool data and output usage](directives/DIR-001-ai-model-data-and-usage-policy.md)
* [DIR-002: Code generation for customer deliverables](directives/DIR-002-code-generation-customer-deliverables.md)
* [DIR-003: Program-level AI code-generation use-case approval](directives/DIR-003-program-level-ai-use-case-approval.md)
