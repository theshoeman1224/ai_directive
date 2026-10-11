# DIR-003: AI-assisted code-generation module qualification

Status: DRAFT

Owner: TBD

Approved By: TBD

Approval Date: TBD

Effective Date: TBD

Review Date: TBD

Related Decisions: None

> DRAFT: This proposed directive is not active and grants no permission.

## Purpose

Define the conditions under which developer-in-the-loop AI code generation may be used within approved software modules or components for customer-deliverable source code.

Tool and data-use requirements are governed by [DIR-001](DIR-001-ai-model-data-and-usage-policy.md). Customer-deliverable requirements are governed by [DIR-002](DIR-002-code-generation-customer-deliverables.md).

## Scope

This directive applies to AI-generated source code intended for a customer-deliverable branch or customer delivery.

Qualification applies only to explicitly approved modules or components and only through separately approved AI tools and interaction modes.

Approved interfaces and interaction modes must be maintained in a separate authoritative source.

**TODO: Identify the authoritative source for approved AI interaction modes and interfaces and define the approval path for additional interfaces, CLI tooling, or agentic capabilities.**

## Required user training

Personnel must complete all training designated as required for AI use before submitting AI-generated source code for customer-deliverable use.

The authoritative list of required training, applicable audiences, and completion windows is maintained at `<ai_training_list_url>`. When new mandatory training is added, affected AI users must complete it within the timeframe specified there.

**TODO: Replace `<ai_training_list_url>` with the authoritative internal training-list URL.**

## Module or component qualification

A sub-Integrated Product Team (sub-IPT) seeking AI-assisted code-generation authority must identify the modules or components for which approval is requested.

The responsible sub-IPT lead must sponsor the requested scope and confirm that the team has appropriate engineering ownership of the affected software.

A small Integrated Product Team (IPT)-level Subject Matter Expert (SME) board reviews the requested scope and determines whether the software-assurance environment is sufficient for developer-in-the-loop AI code generation.

### Minimum regression baseline

At a minimum, the requested module or component must have regression testing that:

* produces reproducible results;
* meaningfully exercises the behavior likely to be modified; and
* provides a practical means to identify and manage failures introduced by changes.

Regression testing is not required to run on every build or Merge Request when that cadence is impractical, including embedded software where execution may require constrained hardware, long-duration environments, or other expensive resources.

When regression testing does not run on every build or Merge Request, the sub-IPT must:

* document the current regression cadence;
* explain why that cadence is reasonable for the affected software;
* make a reasonable effort to increase the cadence when seeking AI-assisted code-generation authority;
* describe how failures are surfaced and associated with the changes that may have introduced them; and
* demonstrate that the delay between introduction and detection of a fault remains manageable.

The team must also identify applicable build and integration checks, static analysis or compiler enforcement, the normal human-review process, and any specialized review required for high-consequence software.

A fixed program-wide coverage threshold or per-build regression requirement is not assumed to be appropriate for every software stack.

**TODO: Determine whether additional program-wide minimum coverage, changed-code coverage, static-analysis, or quality-gate requirements are necessary beyond the reproducible-regression baseline and team-specific justification.**

## Temporary exception for insufficient regression infrastructure

A module or component that does not yet meet the minimum regression baseline may receive only a temporary, time-bounded exception for AI-generated product functionality.

The exception requires approval from both:

* the responsible sub-IPT lead; and
* an SME outside the affected sub-IPT.

The exception must record:

* the specific module or component and permitted scope;
* the reason the existing verification is currently insufficient;
* compensating verification and review controls during the exception period;
* the exception expiration date; and
* a concrete plan to establish the regression capability required for normal qualification.

At the end of the exception period, the sub-IPT must evaluate the planned regression capability. AI-assisted code generation may continue only if the module qualifies under this directive or a renewed exception is explicitly approved with an updated remediation plan.

**TODO: Define the maximum default exception duration and the authoritative place where temporary exceptions are recorded.**

## AI-assisted creation of test infrastructure

AI may be used to create or improve regression and test infrastructure.

When AI generates both functionality and its tests, those tests cannot serve as the sole independent evidence of correctness. Tests used for qualification must be validated against an independent source of expected behavior.

## New interfaces

A new interface, or a material change to an existing interface, requires additional approval when an established independent verification baseline does not exist.

Additional approval requires both the responsible sub-IPT lead and an SME outside the affected sub-IPT. The approval must identify an independent source of expected behavior, such as requirements, interface specifications, reference behavior, or independently derived test results.

**TODO: Define the exact boundary for a new or materially changed interface that requires additional approval.**

## Human responsibility and engineering competency

Human engineers remain accountable for all AI-generated source code they submit.

The submitting engineer must be capable of explaining and evaluating the generated change and must not rely solely on the AI's explanation, generated tests, or successful automated execution as evidence of correctness.

Engineers submitting AI-generated changes must understand the implementation sufficiently to explain its relevant logic, assumptions, failure behavior, and interactions with affected software.

## Human review

Normal peer review remains mandatory in accordance with DIR-002.

Reviewers must evaluate the implementation and must not rely solely on successful automated checks.

## Change size and reviewability

AI-generated changes must remain sufficiently small and cohesive for meaningful human review. AI-generated code must not be produced or submitted at a rate or scope that prevents meaningful human comprehension and review.

Meaningful review requires a reasonable opportunity to understand the generated logic, assumptions, failure behavior, relevant system interactions, and expected impact of the change.

Numeric Source Lines of Code (SLOC) limits are reviewability controls, not proof that a change is low risk. A small change with broad architectural, interface, timing, concurrency, safety, or security impact may require greater scrutiny than a larger repetitive change.

Deleted production code should be evaluated separately from added code because legitimate refactoring may remove substantial legacy code without creating equivalent generated-code review burden.

An AI-assisted Merge Request must represent a single cohesive engineering purpose. Reviewers or technical leads may require decomposition even when a change is below the numeric SLOC limit if its architectural breadth, behavioral complexity, or review burden prevents meaningful review.

**TODO: Establish the default AI-generated Merge Request size limit. A candidate starting point is 500 added SLOC and 2,000 deleted production SLOC. Decide whether the single added-SLOC limit includes test code or only production code. Prefer one understandable review-size policy rather than separate production and test-code limit schemes. Automatically generated artifacts should not drive the human-review limit when they are not manually reviewed source.**

## Team use within an approved scope

Once a module or component is qualified, developer-in-the-loop AI code generation may be used within the approved module/component boundary, interaction mode, reviewability limits, and verification controls.

## Qualification record

Approved module or component scopes must be recorded in `<internal_approval_register>`.

Each record should include at least:

* team and sponsoring sub-IPT lead;
* approved repository and modules or components;
* applicable regression and verification controls and cadence;
* applicable automated analysis or quality controls;
* specialized review requirements or exclusions;
* approved interaction-mode boundary;
* approval status and date;
* approving SMEs;
* conditions or limitations; and
* reapproval triggers.

**TODO: Confirm the authoritative qualification register and determine whether training status is recorded there or in an existing company training system.**

## Reapproval and reevaluation

Material changes to the software-assurance environment or approved scope require reevaluation, including expansion into additional modules, material degradation or repeated bypass of verification controls, material changes to the approved interaction mode, repeated or severe AI-related defects, or loss of the assurance basis under which approval was granted.

**TODO: Define the normal review cadence and any quantitative suspension, revocation, or reevaluation triggers.**

## Exceptions

Exceptions not explicitly defined by this directive must be approved through the applicable engineering or program exception process.

No exception removes human accountability or permits use of an AI tool, data type, or interaction mode that is otherwise prohibited.

**TODO: Identify the authoritative exception process and approval role for exceptions not already covered by the temporary-regression or new-interface rules above.**

## Conditions for use

AI-assisted source-code generation may be used for customer-deliverable software only when:

* the module or component is qualified, or the specific work is covered by an active exception;
* required AI training is complete;
* the AI tool and interaction mode are approved;
* required regression, verification, and human-review controls remain in place;
* the change remains within applicable reviewability limits; and
* all applicable DIR-001 and DIR-002 requirements are satisfied.

## Related directives

* [DIR-001: AI tool data and output usage](DIR-001-ai-model-data-and-usage-policy.md)
* [DIR-002: Code generation for customer deliverables](DIR-002-code-generation-customer-deliverables.md)

## Related communications

None.
