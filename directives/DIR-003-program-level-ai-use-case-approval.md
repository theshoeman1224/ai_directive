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

Define how teams demonstrate and seek program approval for code-generation use cases, including team-level sponsorship and program-level review. Tool approval and use-case approval are separate. An approved use case may run with any company-approved AI tool.

Proposed use cases must be simple, bounded, and demonstrated.

A suitable use case should be comparable to a task that could be given to a junior developer on their first day and completed correctly by the end of the day without additional design guidance.

## Sandbox evaluation

Teams may use any AI tool and interaction method whose data-use level permits the sandbox activity to develop and test a proposed use case in a sandbox. Sandbox output must not merge into a customer-deliverable branch or be delivered to a customer before the use case is approved.

The sandbox demonstration may use any tool whose data-use level permits the sandbox activity. After approval, the team may run the use case with any approved tool without repeating use-case approval, provided the use case and workflow boundaries do not change.

## Team submission

Use the [AI use-case submission template](../templates/ai-use-case-submission.md) to prepare each submission.

Each proposed use case must include:

1. Why the task is simple enough

   Explain why the task is low-complexity and does not require significant design judgment.

2. Template prompt or workflow

   Provide the prompt, prompt template, or repeatable workflow that will be used.

3. Use-case boundaries and required context

   Identify the in-scope task and expected output, excluded uses, required context, examples, and approval-critical boundaries.

4. Proof of concept

   Provide representative sandbox examples and their expected results. Include failures as well as successful results so reviewers can assess correctness.

## Sub-IPT lead sponsorship

Before IPT-level SME review, the sub-IPT lead responsible for the affected product or codebase must endorse the submission.

Sponsorship confirms that the sub-IPT lead:

* is aware of the proposed use case and workflow,
* considers the use case appropriate for the team's product and codebase,
* accepts that the team remains responsible for implementation, testing, and normal code review, and
* has identified any product-specific limits that belong in the approval boundary.

Sponsorship permits the submission to proceed to IPT-level review. It does not grant program approval.

## SME approval

A small IPT-level SME board will review each sponsored submission and confirm:

* The use case is sufficiently simple and narrow.
* The proposed task and AI-generated output are clearly bounded.
* The prompt or workflow is repeatable.
* The sandbox evidence is sufficient to evaluate the proposed use.
* The applicable AI-tool and data-use restrictions are satisfied.

The SME board is not responsible for detailed design, coding standards, or product-specific correctness. Those responsibilities remain with the proposing team and its sub-IPT lead through the normal engineering process.

## Scope of approval

Approval applies only to the submitted use case and workflow.

Material expansion of the use case requires renewed sub-IPT sponsorship and program reapproval. Minor prompt refinements that do not change the approved scope do not require a new approval.

Changing between company-approved AI tools does not require reapproval.

## Approval record

Approved use cases will be recorded in `<internal_approval_register>`. That register is the authoritative record of use-case approval.

Each entry must include:

* Team
* Submitter
* Sponsoring sub-IPT lead
* Sponsorship decision
* Sponsorship date
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

A team may merge generated source code into a customer-deliverable branch or deliver it to a customer only when the authoritative register records the required sub-IPT sponsorship, shows that the use case is approved, and confirms that the work remains within the recorded boundaries.

## Related directives

* [DIR-002: Code generation for customer deliverables](DIR-002-code-generation-customer-deliverables.md)

## Related communications

None.
