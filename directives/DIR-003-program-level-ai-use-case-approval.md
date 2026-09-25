# DIR-003: AI-assisted code-generation module qualification

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

Define the baseline conditions under which developer-in-the-loop AI code generation may be used within approved software modules or components for customer-deliverable source code.

This directive is intended to govern the software-assurance boundary rather than require program approval for each individual prompt or code-generation use case. Teams remain responsible for deciding where AI is useful within an approved scope.

Approval under this directive does not independently approve an AI tool, model, interface, or interaction mode. Applicable tool and data-use requirements remain governed by [DIR-001](DIR-001-ai-model-data-and-usage-policy.md), and customer-deliverable requirements remain governed by [DIR-002](DIR-002-code-generation-customer-deliverables.md).

## Core principles

AI-assisted development under this directive follows these principles:

* AI proposes code; human engineers remain responsible for the resulting implementation.
* Approval is based on whether the affected software can be independently verified, not on whether a specific prompt has been approved.
* Repository or tool access does not imply that the AI understands the complete repository or system.
* Automated testing is an important control but does not independently establish correctness.
* AI-generated tests may improve verification, but AI-generated implementation and AI-generated tests must not be treated as independent evidence of one another.
* Changes must remain sufficiently bounded and reviewable for a human reviewer to understand their behavior and system impact.
* Existing safety, security, mission-critical, architectural, contractual, qualification, and release requirements continue to apply.

## Scope

This directive applies to AI-generated source code intended for a customer-deliverable branch or customer delivery.

Normal approval under this directive applies only to explicitly qualified modules or components and only through separately approved AI tools and interaction modes.

This directive does not authorize autonomous or agentic software-development capabilities merely because the underlying AI tool is approved.

**TODO: Identify the authoritative source for approved AI interaction modes and interfaces. The initial policy should explicitly identify currently approved developer-in-the-loop interfaces and define the approval path for additional interfaces, CLI tooling, or agentic capabilities.**

## Required user training

Personnel must complete required AI training before submitting AI-generated source code for customer-deliverable use under this directive.

Required training must cover at least:

* AI limitations and common failure modes, including hallucination, incomplete context, and plausible but incorrect code;
* applicable AI-tool, data-use, IP, security, and deliverable restrictions; and
* AI-assisted software-engineering responsibilities, including context selection, verification, testing, and human code review.

Training completion establishes user eligibility only. It does not independently authorize a tool, interaction mode, repository, module, component, or otherwise restricted activity.

**TODO: Define the authoritative training curriculum and required courses. Map the required competencies above to the current company/program classes, including any refresher or retraining requirement.**

## Module or component qualification

A sub-Integrated Product Team (sub-IPT) seeking normal AI-assisted code-generation authority must identify the modules or components for which approval is requested.

The responsible sub-IPT lead must sponsor the requested scope and confirm that the team has appropriate engineering ownership of the affected software.

A small Integrated Product Team (IPT)-level Subject Matter Expert (SME) board reviews the requested scope and determines whether the software-assurance environment is sufficient for normal developer-in-the-loop AI code generation.

Qualification is based on the team's ability to detect incorrect AI-generated changes through independent engineering controls. It is not an approval of individual prompts or individual code-generation use cases.

### Minimum assurance expectations

The requested scope must have verification infrastructure appropriate to the software and its risks. At minimum, the team must identify:

* the build and integration checks that apply to the module or component;
* preexisting regression or automated tests that exercise the affected behavior;
* how test results are incorporated into the normal review or integration workflow;
* applicable static-analysis, compiler-warning, coding-standard, or other automated checks;
* the normal human code-review process; and
* any additional specialized review required for safety-critical, security-critical, mission-critical, timing-sensitive, concurrency-sensitive, architectural, or otherwise high-consequence software.

The SME board evaluates whether these controls provide sufficient independent assurance for the requested scope. A fixed program-wide test or coverage threshold is not assumed to be appropriate for every software stack.

**TODO: Determine whether program-wide minimum regression, coverage, changed-code coverage, static-analysis, or quality-gate requirements are necessary in addition to team-specific justification.**

## Existing regression baseline

Normal AI-assisted code generation is intended for software where meaningful independent verification already exists.

A module or component should not receive normal qualification merely because tests exist somewhere in the repository. The team must demonstrate that the applicable regression or verification infrastructure meaningfully exercises the behavior likely to be modified.

Where a module or component lacks adequate preexisting regression or verification infrastructure, additional approval is required before AI-generated product functionality may be integrated under this directive.

## AI-assisted creation of test infrastructure

AI may be used to create, expand, refactor, or improve test infrastructure, including for modules or components that are not yet qualified for normal AI-assisted product-code generation.

AI-generated tests may be used to help establish the verification infrastructure needed for later qualification.

However, AI-generated tests do not by themselves establish an independent correctness baseline for AI-generated product functionality. Before those tests are relied upon as part of module or component qualification, the team must validate them against an independent source of expected behavior.

Independent validation may include, as appropriate:

* approved requirements;
* interface or design specifications;
* known-good historical behavior;
* independently derived expected outputs or test vectors;
* reference models or simulations;
* established peer implementations;
* integration behavior with an independently verified component; or
* direct SME review of expected behavior.

**TODO: Define the minimum evidence required to consider newly created AI-assisted regression infrastructure independently validated.**

## New interfaces and capabilities

AI-generated changes that create a new interface, introduce materially new system behavior, or establish a capability without a preexisting independent regression baseline require additional approval before integration into a customer-deliverable branch.

The purpose of this additional approval is to confirm that the proposed verification approach has an independent source of truth and that the normal module-level approval is not being used to bootstrap both the behavior and its only evidence of correctness from the same AI-generated work.

AI may assist in creating both the new implementation and its supporting tests, but the implementation must be verified against independently established expected behavior before delivery.

**TODO: Define what constitutes a "new interface" or "materially new capability" for this requirement and identify who grants the additional approval. The definition should avoid capturing ordinary contained implementation work that is already well specified and independently verifiable.**

## Human responsibility and review

Human engineers remain accountable for all AI-generated source code they submit.

The submitting engineer must be capable of explaining and evaluating the generated change and must not rely solely on the AI's explanation, generated tests, or successful automated execution as evidence of correctness.

Normal peer review remains mandatory.

Reviewers must evaluate the implementation, not merely confirm that automated checks passed.

AI may assist with code review or test generation, but AI assistance does not replace required human review or independently established verification.

## Change size and reviewability

AI-generated changes must remain sufficiently small and cohesive for meaningful human review.

Numeric Source Lines of Code (SLOC) limits are reviewability controls, not proof that a change is low risk. A small change with broad architectural, interface, timing, concurrency, safety, or security impact may require greater scrutiny than a larger repetitive change.

Deleted production code should be evaluated separately from added production code because legitimate refactoring may remove substantial legacy code without creating equivalent generated-code review burden.

An AI-assisted Merge Request must represent a single cohesive engineering purpose.

**TODO: Establish the default AI-generated Merge Request size limits. A candidate initial value is no more than 500 added production SLOC and 2,000 deleted production SLOC, consistent with the current DIR-004 draft. Determine whether test code and generated artifacts are excluded and define the exception path for larger changes.**

## Activities requiring additional approval

Normal module or component qualification does not by itself authorize:

* AI-generated functionality in areas without adequate independent regression or verification infrastructure;
* new interfaces or materially new capabilities without an established independent verification basis;
* changes exceeding the approved review-size or reviewability limits;
* use through an AI interface, execution mode, or agentic capability that has not been separately approved;
* expansion outside the approved module or component boundary; or
* any activity for which existing safety, security, contractual, export-control, qualification, or engineering rules require additional authorization.

**TODO: Determine whether other high-consequence categories require explicit program-level approval even when the affected module otherwise satisfies this directive.**

## Team use within an approved scope

Once a module or component is qualified, the team may determine which developer-in-the-loop AI code-generation use cases are useful within that approved scope without obtaining separate SME approval for each prompt, workflow, or coding task.

Teams are encouraged to document and share effective prompts, workflows, known model limitations, and failed approaches, but those materials are engineering guidance rather than individual program approvals unless another directive explicitly requires otherwise.

A prompt change or a new ordinary use case does not require renewed approval when the work remains within the approved module or component, interaction mode, reviewability limits, and verification boundaries.

## Qualification record

Approved module or component scopes will be recorded in `<internal_approval_register>`.

Each qualification record should include at least:

* Team
* Sponsoring sub-IPT lead
* Approved repository
* Approved modules or components
* Applicable regression and verification controls
* Applicable automated analysis or quality controls
* Specialized review requirements or exclusions
* Approved interaction-mode boundary
* Approval status
* Approval date
* Approving SMEs
* Conditions or limitations
* Reapproval triggers

**TODO: Confirm the authoritative qualification register and determine whether user training status is recorded in the same system or an existing company training system.**

## Reapproval and reevaluation

Material changes to the software-assurance environment or approved scope require reevaluation.

Examples include:

* expansion into additional modules or components;
* removal, degradation, or repeated bypass of required verification controls;
* material changes to the approved interaction mode or AI execution capability;
* repeated or severe defects associated with AI-generated changes; or
* a change that causes the qualified scope to no longer meet the assurance basis under which it was approved.

Routine prompt changes and ordinary team-selected use cases within the approved boundary do not require reapproval.

**TODO: Define the normal review cadence and any quantitative suspension, revocation, or reevaluation triggers.**

## Relationship to DIR-004

[DIR-004](DIR-004-full-ai-code-generation-approval.md) currently defines a separate higher-assurance repository/module approval path.

The revised model in this directive substantially overlaps with that concept by making module/component qualification the normal approval mechanism.

**TODO: Reconcile DIR-004 with this directive. Consider repurposing DIR-004 for higher-autonomy or agentic software-development capabilities rather than maintaining two overlapping module/repository approval paths.**

## Exceptions

Exceptions to this directive must be explicitly approved through the applicable engineering or program exception process.

No exception removes the requirement for human accountability or permits use of an AI tool, data type, or interaction mode that is otherwise prohibited.

**TODO: Identify the authoritative exception process and approval role.**

## Verification and compliance

A team may use normal developer-in-the-loop AI code generation for customer-deliverable source code under this directive only when:

* the affected module or component is recorded as qualified;
* the engineer has completed the required AI training;
* the AI tool and interaction mode are separately approved for the activity;
* applicable regression, verification, analysis, and human-review controls remain in place;
* the change remains within applicable reviewability limits;
* no additional-approval condition in this directive applies; and
* all requirements in DIR-001, DIR-002, and other applicable engineering or contractual controls are satisfied.

## Related directives

* [DIR-001: AI tool data and output usage](DIR-001-ai-model-data-and-usage-policy.md)
* [DIR-002: Code generation for customer deliverables](DIR-002-code-generation-customer-deliverables.md)
* [DIR-004: Full AI code-generation approval](DIR-004-full-ai-code-generation-approval.md)

## Related communications

None.
