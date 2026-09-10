# AI code-generation use-case submission

> TEMPLATE: This blank form does not record or grant approval.

> This repository is public. Do not enter company IP or other restricted information here. Complete and store submissions in `<internal_approval_register>`.

Submission Status: DRAFT

<!-- Submission Status lifecycle: DRAFT (being prepared), SUBMITTED (sent for sub-IPT lead sponsorship),
     ENDORSED (sponsored and awaiting SME review), APPROVED or NOT APPROVED (SME decision recorded), WITHDRAWN. -->

Team: `<team_name>`

Submitter: `<submitter_role>`

Submission Date: `<submission_date>`

Use-Case Title: `<use_case_title>`

Related Directive: [DIR-003: Program-level AI code-generation use-case approval](../directives/DIR-003-program-level-ai-use-case-approval.md)

## Purpose

<!-- Briefly describe the task, why AI assistance is useful, and the expected benefit. -->

`<use_case_purpose>`

## 1. Why the task is simple enough

<!-- Explain why the task is low-complexity, bounded, and does not require significant design judgment. Address the first-day junior developer and end-of-day completion standard in DIR-003.
     Anchors: writing a documentation comment, adding a small test scaffold, or generating simple diagnostic-output code from a fixed template are likely simple enough.
     Designing new logic whose correctness depends on cross-module behavior, or anything a first-day developer could not verify by end of day, is likely too complex. -->

`<simplicity_justification>`

## 2. Template prompt or workflow

<!-- Provide the exact reusable prompt, prompt template, or repeatable workflow that will be approved. Identify any required human steps before or after AI use. -->

```text
<approved_prompt_or_workflow>
```

## 3. Use-case boundaries and required context

### In scope

<!-- List the specific tasks and AI-generated output this approval would permit. -->

* `<in_scope_task>`

### Out of scope

<!-- List similar, higher-risk, or otherwise restricted tasks that remain outside the approval boundary. -->

* `<excluded_task>`

### Required context

<!-- Identify the input types, examples, files, or other context the workflow requires. Describe sensitive inputs generically in this public template. -->

* `<required_context>`

## 4. Proof of concept

### Evaluation method

<!-- Describe the sandbox trials, representative inputs, expected results, and correctness criteria. -->

`<evaluation_method>`

### Results

<!-- Include successful and failed trials so reviewers can assess reliability and limitations. Link evidence only from the authorized internal location. -->

| Trial | Expected Result | Actual Result | Pass/Fail | Evidence |
|---|---|---|---|---|
| `<trial_name>` | `<expected_result>` | `<actual_result>` | `<result>` | `<internal_evidence_reference>` |

### Known failures and limitations

<!-- Describe observed failures, unreliable conditions, and cases requiring rejection or escalation. -->

* `<known_failure_or_limitation>`

## Requested approval

<!-- State the exact use case and workflow boundaries the team is asking the Subject Matter Expert (SME) board to approve. -->

`<requested_approval_scope>`

## Sub-IPT lead sponsorship

<!-- Completed by the sub-Integrated Product Team (sub-IPT) lead responsible for the affected product or codebase. Sponsorship confirms that the proposed use is appropriate for the team and may proceed to Integrated Product Team (IPT)-level review. It does not grant program approval. -->

Sponsoring Sub-IPT Lead: `<sub_ipt_lead>`

Sponsorship Decision: `<endorsed_or_not_endorsed>`

Sponsorship Date: `<sponsorship_date>`

Conditions or Comments: `<conditions_or_comments>`

## SME review

<!-- Completed by the authorized SME board. Do not infer or prefill approval. -->

Approval Status: TBD

Approval Date: TBD

Approving SMEs: TBD

Review Findings: TBD

Approval Conditions: TBD

Reapproval Triggers: TBD
