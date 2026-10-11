# Program plan

Status: DRAFT

Owner: TBD

Approved By: TBD

Approval Date: TBD

Last Updated: 2026-10-11

## Objective

Authorize teams to use company-approved AI tools for code generation while keeping human engineers accountable for source code merged into customer-deliverable branches or delivered to customers.

The adoption model qualifies software modules or components based on their verification and review environment.

## Scope

This plan covers AI-assisted code generation for customer-deliverable software, including tool/data eligibility, module qualification, required training, regression expectations, human review, reviewability limits, and temporary exceptions.

Higher-autonomy and agentic governance is deferred from the initial release.

This plan does not authorize customer-deliverable use by itself. Active directives remain the source of truth for operational instructions.

## Current priorities

* Establish module/component qualification as the path for developer-in-the-loop AI code generation.
* Require reproducible regression testing and a justified test cadence appropriate to each software environment.
* Require AI users to complete the training identified at `<ai_training_list_url>` within the stated completion windows.
* Protect human reviewability, engineering competency, and system/architecture understanding as AI increases implementation speed.
* Define temporary, time-bounded exceptions for modules that do not yet have sufficient regression infrastructure, with a required remediation plan.
* Require additional approval for new or materially changed interfaces without an established independent verification basis.

## Requirements

* Use only AI tools whose data-use level permits the intended input and output under [DIR-001](directives/DIR-001-ai-model-data-and-usage-policy.md).
* Follow the universal deliverable-code requirements in [DIR-002](directives/DIR-002-code-generation-customer-deliverables.md).
* Use module/component qualification under [DIR-003](directives/DIR-003-ai-code-generation-module-qualification.md) for developer-in-the-loop AI code generation.
* Require reproducible regression testing that meaningfully exercises the affected behavior. Permit non-per-build cadence where justified by the sub-IPT and where fault detection remains manageable.
* Require engineers submitting AI-generated deliverable code to complete the mandatory training identified at `<ai_training_list_url>` within the defined completion windows.
* Keep human engineers responsible for understanding, reviewing, maintaining, and debugging AI-generated code and its relevant system interactions.
* Protect reviewability through cohesive change scope, SLOC limits, and reviewer authority to require decomposition.
* Permit AI to help create test infrastructure, while requiring independent evidence of expected behavior when AI generates both functionality and its tests.
* Allow only temporary, time-bounded exceptions where adequate regression infrastructure does not yet exist. Exceptions require a remediation plan and approval by the responsible sub-IPT lead and an outside SME.
* Require the responsible sub-IPT lead and an outside SME to approve new or materially changed interfaces that lack an established independent verification basis.
* Require AI-altered source files to carry the file-level provenance header defined by DIR-002.

## Operating model

The following statements are planning assumptions. They are not active instructions while this plan remains in `DRAFT`:

1. The company determines which AI tools may receive company IP and which outputs may enter deliverables under DIR-001.
2. Teams identify the software modules or components in which they want developer-in-the-loop AI code-generation authority.
3. The responsible sub-IPT lead sponsors the requested software scope.
4. An IPT-level SME board evaluates whether the requested scope has an adequate independent verification and review environment under DIR-003.
5. Once qualified, engineers may use approved developer-in-the-loop AI within the qualified boundary.
6. Engineers remain responsible for generated changes and must satisfy applicable training, review, testing, and provenance requirements.
7. Work that lacks adequate regression infrastructure may proceed only under a time-bounded exception with compensating controls and a plan to establish qualification capability.
8. New or materially changed interfaces without an established independent verification basis receive additional approval from the responsible sub-IPT lead and an outside SME.

## Implementation plan

### Phase 1

Finalize the module/component qualification criteria, required training reference, file-level AI provenance convention, review-size policy, approval register, and temporary-exception process.

### Phase 2

Qualify initial modules and components using representative sub-IPTs. Capture how regression cadence, reviewability, and exception handling operate across different embedded and non-embedded software environments.

### Phase 3

Use program evidence to adjust review-size limits, verification expectations, and reevaluation triggers. Address higher-autonomy and agentic governance separately when that capability is ready for evaluation.

## Risks

* AI can produce code faster than humans can meaningfully review it, causing review to become superficial or unmanageable.
* Engineers, particularly less-experienced engineers, may overdevelop prompt/tool skills while underdeveloping core software-engineering, debugging, and design expertise.
* Heavy AI usage may reduce engineer understanding of system behavior, architecture, interfaces, and downstream effects.
* Generated code may pass narrow tests without fitting repository-wide behavior, architecture, or conventions.
* AI-generated implementation and AI-generated tests may reproduce the same misunderstanding and create false confidence if treated as independent evidence.
* Regression cadence may be too slow to associate introduced faults with the responsible change, especially in constrained embedded environments.
* Temporary regression exceptions may become de facto permanent approval if expiration and remediation are not enforced.
* Approved module boundaries may be interpreted too broadly.
* Automated quality gates may provide false confidence if their scope or enforcement is weak.

## Dependencies

* Named plan owner and approval authority: TBD.
* Membership and authority of the IPT-level SME board: TBD.
* Authoritative approved-tool, approved-interface, and module-qualification records: TBD.
* Replace `<ai_training_list_url>` with the authoritative internal training-list URL.
* Exact AI-altered file-header convention: TBD.
* Default AI-generated Merge Request SLOC limit: TBD.
* Maximum default duration for temporary regression exceptions: TBD.
* Definition of a new or materially changed interface requiring additional approval: TBD.

## Open questions

* Who owns this plan and who has final approval authority?
* What is the authoritative source for approved AI interfaces and interaction modes?
* What exact file-level header identifies an AI-altered source file, and what is its lifecycle?
* What default review-size limit should apply to AI-generated changes?
* Should the single added-SLOC review limit include test code as well as production code?
* What maximum duration should apply to a temporary regression exception?
* What exact boundary defines a new or materially changed interface requiring additional approval?
* What review cadence and suspension/reapproval triggers should apply to qualified modules?

## Related decisions

None.

## Related directives

* [DIR-001: AI tool data and output usage](directives/DIR-001-ai-model-data-and-usage-policy.md)
* [DIR-002: Code generation for customer deliverables](directives/DIR-002-code-generation-customer-deliverables.md)
* [DIR-003: AI-assisted code-generation module qualification](directives/DIR-003-ai-code-generation-module-qualification.md)

## Deferred work

* [DIR-004: Higher-autonomy and agentic AI development](directives/DIR-004-DEFERRED-higher-autonomy-agentic-ai-development.md)
