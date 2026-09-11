# DIR-004: Full AI code-generation approval

Status: DRAFT

Owner: TBD

Approved By: TBD

Approval Date: TBD

Effective Date: TBD

Review Date: TBD

Supersedes: None

Superseded By: None

Related Decisions: None

> DRAFT: This proposed directive is not active and grants no permission.

## Purpose

Define a higher-assurance approval path that allows a team to use Level 1 AI tooling permitted under [DIR-001](DIR-001-ai-model-data-and-usage-policy.md) for broad code-generation purposes within specifically approved repositories and modules without obtaining separate approval for each individual use case.

This approval is based on demonstrated software-assurance controls, not an assumption that AI-generated code is correct.

## Relationship to use-case approval

[DIR-003](DIR-003-program-level-ai-use-case-approval.md) remains the default path for bounded AI code-generation use cases.

A team approved under this directive does not need separate DIR-003 approval for each code-generation use case performed within the repositories and modules explicitly covered by its Full AI Code Generation Approval.

This broader authority does not waive any other engineering, review, tagging, safety, security, contractual, verification, qualification, or release requirement.

## Scope of approval

This directive applies only to AI-generated source code intended for customer-deliverable branches or customer delivery.

Approval applies only to the repositories and modules explicitly reviewed by the SME board and recorded in `<internal_approval_register>`.

Each approval record must identify:

* Team
* Approved repositories
* Approved modules or components
* Required regression controls
* Required static-analysis controls
* Required coverage thresholds
* Required quality gates
* Approval status
* Approval date
* Approving SMEs

Material expansion beyond the approved repositories or modules requires renewed SME review.

AI tooling used under this directive must satisfy the Level 1 requirements defined in [DIR-001](DIR-001-ai-model-data-and-usage-policy.md). Only Level 1 tooling may be used to generate source code that enters customer-deliverable products.

This directive does not independently approve AI tools or models. Tool eligibility remains governed by DIR-001.

## Entry requirements

Before receiving Full AI Code Generation Approval, the team must demonstrate that the requested repositories and modules have mature, automated software-assurance controls.

### Automated regression

The approved scope must have an automated regression suite that:

* runs automatically for every Merge Request,
* exercises the repositories and modules covered by the requested approval,
* automatically produces pass/fail and code-coverage results, and
* participates directly in the Merge Request quality gate.

Minimum required coverage:

**TODO: Establish the minimum required code-coverage threshold.**

Coverage requirements for newly modified or AI-generated code:

**TODO: Determine whether changed-code coverage requires a separate threshold.**

### Static analysis

The team must demonstrate static-analysis coverage appropriate to its languages, architecture, risks, and coding standards.

This directive does not prescribe a specific product. Examples may include SonarQube, Coverity, language-specific static analyzers, security analyzers, coding-standard enforcement tools, and compiler-warning enforcement.

The team must document:

* what each analysis tool detects,
* which findings are considered blocking,
* how findings are presented during review,
* how findings are enforced, and
* how suppressions and exceptions are controlled.

The team proposes its blocking thresholds and severity policy. The SME board determines whether the proposed controls and thresholds are sufficiently rigorous for the requested scope.

### Quality gates

Regression, coverage, and static-analysis results must be gathered automatically for every Merge Request and included in the Merge Request quality gates.

Required quality gates must block integration by default.

A failed or unavailable required gate may be bypassed only under exceptional circumstances, including an approved exception or an outage of required tooling. Any bypass must be documented and handled under the applicable engineering exception process.

## Demonstrated effectiveness

Before approval, the team must demonstrate successful operation of the proposed controls across a meaningful body of normal development work.

The minimum evidence set is a number of completed Merge Requests equal to at least:

**2 × the number of software engineers on the team.**

The controls proposed for Full AI Code Generation Approval must be active during this evidence period so the SME board can evaluate their actual operation.

The SME board reviews the resulting regression, coverage, static-analysis, quality-gate, exception, and defect evidence before granting approval.

## AI change size

An individual AI-generated Merge Request must contain no more than **500 added production SLOC**.

Deleted production code does not count toward the 500-SLOC generated-code limit. However, an individual AI-generated Merge Request must normally contain no more than **2,000 deleted production SLOC**.

Test code and automatically generated artifacts are excluded from both calculations.

Each AI-generated Merge Request must represent a single cohesive engineering purpose.

A change exceeding either threshold must be decomposed into independently reviewable changes or receive explicit SME-board approval before integration.

These thresholds are initial limits and should be revisited using program data on review effectiveness, defect rates, and change complexity.

## Human review and existing requirements

Human code review remains mandatory for all AI-generated code.

Full AI Code Generation Approval does not replace or reduce any additional review requirement that already applies to the affected software, including safety-critical, security-critical, mission-critical, architectural, or other specialized review requirements.

All requirements in [DIR-002](DIR-002-code-generation-customer-deliverables.md) remain applicable unless an active directive explicitly supersedes them.

AI-generated source lines must continue to follow the applicable AI provenance and source-tagging requirements.

## Ongoing monitoring

Approved teams must continuously collect and retain the metrics already produced through their Merge Request quality gates, including where applicable:

* regression results,
* code-coverage results,
* static-analysis findings,
* quality-gate failures,
* quality-gate exceptions or bypasses,
* AI-related defects identified during human review, and
* defects discovered after integration.

These metrics must remain available to the SME board for periodic review.

## Suspension or revocation

The SME board may suspend or revoke Full AI Code Generation Approval when the approved software-assurance controls are no longer operating as reviewed or when AI-related defects become unreasonably frequent or severe.

Conditions that may trigger reevaluation include:

* required quality controls being disabled or repeatedly bypassed,
* regression or static-analysis capability materially degrading,
* coverage falling below the approved threshold,
* repeated or severe escaped defects associated with AI-generated changes, or
* material changes to the approved repositories, modules, workflow, or reviewed assurance controls.

Specific quantitative suspension or revocation thresholds are TBD and may be established as program evidence grows.

## Exceptions

Exceptions to the normal quality-gate requirements must be documented and handled through the applicable engineering exception process.

No exception removes the requirement for human review or permits use of AI tooling that does not satisfy the Level 1 requirements of DIR-001 for customer-deliverable source code.

## Verification and compliance

A team may operate under Full AI Code Generation Approval only when the authoritative approval register shows that:

* the specific repositories and modules are approved,
* the required automated regression, coverage, static-analysis, and quality-gate controls are in place,
* the required evidence period has been completed,
* the AI tooling used satisfies the Level 1 requirements of DIR-001,
* ongoing metrics remain available for review, and
* the work remains within the approved change-size and repository/module boundaries.

## Related directives

* [DIR-001: AI tool data and output usage](DIR-001-ai-model-data-and-usage-policy.md)
* [DIR-002: Code generation for customer deliverables](DIR-002-code-generation-customer-deliverables.md)
* [DIR-003: Program-level AI code-generation use-case approval](DIR-003-program-level-ai-use-case-approval.md)

## Related communications

None.
