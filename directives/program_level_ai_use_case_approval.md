# Program-Level AI Code Generation Use-Case Approval

## Purpose

Because each IPT/sub-IPT uses different languages, architectures, and development workflows, AI code-generation approval will be handled per use case rather than through a single umbrella policy.

Approved use cases must be **simple, bounded, and demonstrated**.

A suitable use case should be comparable to a task that could be given to a junior developer on their first day and completed correctly by the end of the day without additional design guidance.

## Team Submission

Each proposed use case must include:

1. **Why the task is simple enough**
   - Explain why the task is low-complexity and does not require significant design judgment.

2. **Template prompt or workflow**
   - Provide the prompt, prompt template, or repeatable workflow that will be used.

3. **Usage limitations / required context**
   - Identify any required context, examples, coding standards, or other constraints.
   - This section is optional when no additional limitations are needed.

4. **Proof of concept**
   - Provide a small set of representative examples showing that the approved Poolside model can perform the task reliably.

## SME Approval

A small SME board will review each submission and confirm:

- The use case is sufficiently simple and narrow.
- The expected output is clearly defined.
- The workflow has been demonstrated to work.
- The boundaries of acceptable use are clear.
- Applicable engineering, safety, or contractual concerns have been considered.

The proposing team remains responsible for the technical details of its own codebase and workflow.

## Scope of Approval

Approval applies only to the submitted use case and workflow.

Material expansion of the use case requires reapproval. Minor prompt refinements that do not change the approved scope do not require a new approval.

## Confluence Tracking

Approved use cases will be recorded on a shared Confluence page so other teams can understand how AI is being used across the program.

Each entry should include:

- Team / IPT
- Submitter
- Use case
- Purpose
- Approved prompt or workflow
- Required context / limitations
- Proof-of-concept evidence
- Approval date
- Approving SMEs

This catalog is intended to promote reuse of proven workflows without requiring a one-size-fits-all policy.
