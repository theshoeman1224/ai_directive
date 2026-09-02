# DIR-003: Program-level AI code-generation use-case approval

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

Define how teams demonstrate and seek program approval for code-generation use cases. Tool approval and use-case approval are separate. An approved use case may run with any program-approved AI tool.

Proposed use cases must be simple, bounded, and demonstrated.

A suitable use case should be comparable to a task that could be given to a junior developer on their first day and completed correctly by the end of the day without additional design guidance.

## Sandbox evaluation

Teams may use any program-approved AI tool and interaction method to develop and test a proposed use case in a sandbox. Sandbox output must not merge into a customer-deliverable branch or be delivered to a customer before the use case is approved.

The sandbox demonstration may use any approved tool. After approval, the team may run the use case with any approved tool without repeating use-case approval, provided the use case and workflow boundaries do not change.

## Team submission

Use the [AI use-case submission template](../templates/ai-use-case-submission.md) to prepare each submission.

Each proposed use case must include:

1. Why the task is simple enough

   Explain why the task is low-complexity and does not require significant design judgment.

2. Template prompt or workflow

   Provide the prompt, prompt template, or repeatable workflow that will be used.

3. Use-case boundaries and required context

   Identify the in-scope task, excluded uses, required context, examples, coding standards, and other constraints.

4. Proof of concept

   Provide representative sandbox examples and their expected results. Include failures as well as successful results so reviewers can assess correctness.

## SME approval

A small SME board will review each submission and confirm:

* The use case is sufficiently simple and narrow.
* The expected output is clearly defined.
* The sandbox evidence demonstrates that the workflow produces correct results.
* The boundaries of acceptable use are clear.
* Applicable engineering, safety, or contractual concerns have been considered.

The proposing team remains responsible for the technical details of its own codebase and workflow.

## Scope of approval

Approval applies only to the submitted use case and workflow.

Material expansion of the use case requires reapproval. Minor prompt refinements that do not change the approved scope do not require a new approval.

Changing between program-approved AI tools does not require reapproval.

## Approval record

Approved use cases will be recorded in `<internal_approval_register>`. That register is the authoritative record of use-case approval.

Each entry must include:

* Team
* Submitter
* Use case
* Purpose
* Approved prompt or workflow
* Required context and limitations
* Proof-of-concept evidence
* Approval status
* Approval date
* Approving SMEs

The register allows teams to see how AI is used across the program. An existing entry does not authorize a different use case.

## Exceptions

None currently exist.

## Verification and compliance

A team may merge generated source code into a customer-deliverable branch or deliver it to a customer only when the authoritative register shows that the use case is approved and the work remains within the recorded boundaries.

## Related directives

* [DIR-002: Code generation for customer deliverables](DIR-002-code-generation-customer-deliverables.md)

## Related communications

None.
