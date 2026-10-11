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

This directive governs the software-assurance boundary rather than requiring approval for each prompt or individual code-generation use case. Teams remain responsible for deciding where AI is useful within an approved scope.

Approval under this directive does not independently approve an AI tool, model, interface, or interaction mode. Tool and data-use requirements remain governed by [DIR-001](DIR-001-ai-model-data-and-usage-policy.md), and customer-deliverable requirements remain governed by [DIR-002](DIR-002-code-generation-customer-deliverables.md).

## Core principles

* AI proposes code; human engineers remain responsible for the resulting implementation.
* Approval is based on whether the affected software can be independently verified, not on whether a specific prompt has been approved.
* Repository or tool access does not imply complete repository or system understanding by the AI.
* Automated testing is an important control but does not independently establish correctness.
* AI-generated implementation and AI-generated tests must not be treated as independent evidence of one another.
* AI-generated changes must remain sufficiently bounded for meaningful human review.
* AI may accelerate implementation, but it must not replace the engineering judgment or system knowledge required to understand, verify, maintain, and debug the resulting software.
* Existing safety, security, mission-critical, architectural, contractual, qualification, and release requirements continue to apply.

## Scope

This directive applies to AI-generated source code intended for a customer-deliverable branch or customer delivery.

Normal approval applies only to explicitly qualified modules or components and only through separately approved AI tools and interaction modes.

This directive does not authorize autonomous or agentic software-development capabilities merely because the underlying AI tool is approved.

Approved interfaces and interaction modes must be maintained in a separate authoritative source so this directive remains independent of specific products or interfaces.

**TODO: Identify the authoritative source for approved AI interaction modes and interfaces and define the approval path for additional interfaces, CLI tooling, or agentic capabilities.**

## Required user training

Personnel must complete required AI training before submitting AI-generated source code for customer-deliverable use.

Required training must cover at least:

* AI limitations and common failure modes, including hallucination, incomplete context, and plausible but incorrect code;
* applicable AI-tool, data-use, IP, security, and deliverable restrictions; and
* AI-assisted software-engineering responsibilities, including context selection, verification, testing, human review, and preservation of system understanding.

Training completion establishes user eligibility only. It does not independently authorize a tool, interaction mode, repository, module, component, or otherwise restricted activity.

When new mandatory AI training is introduced, AI users must complete it within the program-defined completion window.

**TODO: Define the authoritative training curriculum, required courses, and completion window for newly introduced training.**

No additional AI-specific reviewer training is required by this draft beyond existing code-review qualifications.

**TODO: Reevaluate reviewer-specific AI training if dedicated training becomes available or evidence shows that reviewers need additional qualification.**

## Module or component qualification

A sub-Integrated Product Team (sub-IPT) seeking normal AI-assisted code-generation authority must identify the modules or components for which approval is requested.

The responsible sub-IPT lead must sponsor the requested scope and confirm that the team has appropriate engineering ownership of the affected software.

A small Integrated Product Team (IPT)-level Subject Matter Expert (SME) board reviews the requested scope and determines whether the software-assurance environment is sufficient for normal developer-in-the-loop AI code generation.

Qualification is based on the team's ability to detect incorrect AI-generated changes through independent engineering controls. It is not an approval of individual prompts or individual code-generation use cases.

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

At the end of the exception period, the sub-IPT must evaluate the planned regression capability. Normal AI-assisted code generation may continue only if the module qualifies under this directive or a renewed exception is explicitly approved with an updated remediation plan.

A temporary exception does not permanently qualify the module or component.

**TODO: Define the maximum default exception duration and the authoritative place where temporary exceptions are recorded.**

## AI-assisted creation of test infrastructure

AI may be used to create, expand, refactor, or improve test infrastructure, including for modules or components that are not yet qualified for normal AI-assisted product-code generation.

AI-generated tests may help establish the regression infrastructure required for later qualification.

However, AI-generated tests do not by themselves establish an independent correctness baseline for AI-generated product functionality. Before those tests are relied upon for qualification, the team must validate them against an independent source of expected behavior, such as approved requirements, interface or design specifications, known-good historical behavior, independently derived test vectors, reference models, integration behavior, or direct SME review.

**TODO: Define the minimum evidence required to consider newly created AI-assisted regression infrastructure independently validated.**

## New interfaces and materially new capabilities

AI-generated changes that create a new interface, introduce materially new system behavior, or establish a capability without a preexisting independent regression baseline require additional approval before integration into a customer-deliverable branch.

Additional approval requires both the responsible sub-IPT lead and an SME outside the affected sub-IPT.

The approval must confirm that the verification approach has an independent source of expected behavior. AI may assist in creating both the implementation and its supporting tests, but those tests cannot be the sole basis for determining correctness.

**TODO: Define what constitutes a "new interface" or "materially new capability" without capturing ordinary contained implementation work that is already well specified and independently verifiable.**

## Human responsibility and engineering competency

Human engineers remain accountable for all AI-generated source code they submit.

The submitting engineer must be capable of explaining and evaluating the generated change and must not rely solely on the AI's explanation, generated tests, or successful automated execution as evidence of correctness.

AI assistance must supplement, not replace, the software-engineering competency needed to design, understand, verify, maintain, and debug the affected software.

Engineers submitting AI-generated changes must understand the implementation sufficiently to explain its relevant logic, assumptions, failure behavior, and interactions with affected software.

AI assistance does not remove responsibility to understand relevant system behavior, architectural boundaries, interfaces, and downstream effects. A locally correct change is not acceptable if its broader system impact has not been adequately understood and reviewed.

Teams and technical leads must avoid patterns of AI usage that materially erode the development or exercise of core software-engineering skills, particularly when mentoring or developing less-experienced engineers.

This directive does not prescribe different AI permissions solely by seniority. The same requirement to understand and defend submitted work applies to all engineers.

## Human review

Normal peer review remains mandatory.

Reviewers must evaluate the implementation, not merely confirm that automated checks passed.

AI may assist with code review or test generation, but AI assistance does not replace required human review or independently established verification.

## Change size and reviewability

AI-generated changes must remain sufficiently small and cohesive for meaningful human review. AI-generated code must not be produced or submitted at a rate or scope that prevents meaningful human comprehension and review.

Meaningful review requires a reasonable opportunity to understand the generated logic, assumptions, failure behavior, relevant system interactions, and expected impact of the change.

Numeric Source Lines of Code (SLOC) limits are reviewability controls, not proof that a change is low risk. A small change with broad architectural, interface, timing, concurrency, safety, or security impact may require greater scrutiny than a larger repetitive change.

Deleted production code should be evaluated separately from added code because legitimate refactoring may remove substantial legacy code without creating equivalent generated-code review burden.

An AI-assisted Merge Request must represent a single cohesive engineering purpose. Reviewers or technical leads may require decomposition even when a change is below the numeric SLOC limit if its architectural breadth, behavioral complexity, or review burden prevents meaningful review.

**TODO: Establish the default AI-generated Merge Request size limit. A candidate starting point is 500 added SLOC and 2,000 deleted production SLOC. Decide whether the single added-SLOC limit includes test code or only production code. Prefer one understandable review-size policy rather than separate production and test-code limit schemes. Automatically generated artifacts should not drive the human-review limit when they are not manually reviewed source.**

## Activities requiring additional approval

Normal module or component qualification does not by itself authorize:

* use under a temporary regression exception beyond its approved scope or expiration date;
* new interfaces or materially new capabilities without the required additional approval;
* changes exceeding the approved review-size or reviewability limits;
* use through an AI interface, execution mode, or agentic capability that has not been separately approved;
* expansion outside the approved module or component boundary; or
* activity for which existing safety, security, contractual, export-control, qualification, or engineering rules require additional authorization.

**TODO: Determine whether other high-consequence categories require explicit additional approval even when the affected module otherwise satisfies this directive.**

## Team use within an approved scope

Once a module or component is qualified, the team may determine which developer-in-the-loop AI code-generation tasks are useful within that approved scope without obtaining separate SME approval for each prompt, workflow, or coding task.

Teams are encouraged to document and share effective prompts, workflows, known model limitations, and failed approaches as engineering guidance.

Routine prompt changes and ordinary team-selected tasks do not require renewed approval when the work remains within the approved module or component, interaction mode, reviewability limits, and verification boundaries.

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

Routine prompt changes and ordinary team-selected tasks within the approved boundary do not require reapproval.

**TODO: Define the normal review cadence and any quantitative suspension, revocation, or reevaluation triggers.**

## Relationship to DIR-004

[DIR-004](DIR-004-full-ai-code-generation-approval.md) is reserved for future higher-autonomy or agentic software-development capabilities.

Normal developer-in-the-loop module qualification is governed by this directive. DIR-004 must not create a second competing module-qualification path.

## Exceptions

Exceptions to this directive must be explicitly approved through the applicable engineering or program exception process.

No exception removes the requirement for human accountability or permits use of an AI tool, data type, or interaction mode that is otherwise prohibited.

**TODO: Identify the authoritative exception process and approval role for exceptions not already covered by the temporary-regression or new-capability rules above.**

## Verification and compliance

Normal developer-in-the-loop AI code generation for customer-deliverable source code is permitted under this directive only when:

* the affected module or component is recorded as qualified, or the specific work is covered by an active temporary exception;
* the engineer has completed required AI training;
* the AI tool and interaction mode are separately approved for the activity;
* applicable regression, verification, analysis, and human-review controls remain in place;
* the change remains within applicable reviewability limits;
* any required additional approval has been obtained; and
* all requirements in DIR-001, DIR-002, and other applicable engineering or contractual controls are satisfied.

## Related directives

* [DIR-001: AI tool data and output usage](DIR-001-ai-model-data-and-usage-policy.md)
* [DIR-002: Code generation for customer deliverables](DIR-002-code-generation-customer-deliverables.md)
* [DIR-004: Higher-autonomy and agentic AI development](DIR-004-full-ai-code-generation-approval.md)

## Related communications

None.
