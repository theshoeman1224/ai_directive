# AI code-generation module qualification submission

> TEMPLATE: This blank form does not record or grant approval.

Submission Status: DRAFT

Team: `<team_name>`

Submitter: `<submitter_role>`

Submission Date: `<submission_date>`

Related Directive: [DIR-003: AI-assisted code-generation module qualification](../directives/DIR-003-ai-code-generation-module-qualification.md)

## Requested scope

Repository: `<repository>`

Modules or Components:

* `<module_or_component>`

Describe the requested developer-in-the-loop AI code-generation boundary:

`<requested_scope>`

## Engineering ownership

Responsible Sub-IPT Lead: `<sub_ipt_lead>`

Describe the team's ownership of the affected software:

`<ownership_description>`

## Regression baseline

Describe the regression testing that applies to the requested scope, including what behavior it exercises and how reproducible results are established.

`<regression_description>`

Regression Cadence: `<cadence>`

If regression does not run on every build or Merge Request, explain:

* why the cadence is reasonable;
* what effort has been made to increase cadence;
* how failures are surfaced and associated with changes; and
* why the fault-detection delay remains manageable.

`<cadence_justification>`

## Other engineering controls

Build / Integration Checks:

`<build_checks>`

Static Analysis / Compiler / Coding-Standard Controls:

`<analysis_controls>`

Normal Human Review Process:

`<review_process>`

Specialized Safety / Security / Mission / Architecture Requirements:

`<specialized_controls>`

## Reviewability

Describe how the team will keep AI-generated changes sufficiently cohesive and limited for meaningful human review.

`<reviewability_controls>`

## Training

Required Training List: `<ai_training_list_url>`

Describe how the team will ensure engineers submitting AI-generated deliverable code have completed all required training within the stated completion windows.

`<training_verification>`

## Interaction-mode boundary

Identify the approved AI interfaces or interaction modes expected to be used within this scope. Reference the authoritative internal source rather than treating this form as interface approval.

`<interaction_mode_reference>`

## Known limitations and exclusions

List software areas, behaviors, or conditions that should remain outside normal qualification.

* `<limitation_or_exclusion>`

## Temporary regression exception

Complete this section only if the requested work does not yet meet the normal regression baseline.

Exception Required: `<yes_or_no>`

Reason Current Regression Is Insufficient: `<reason>`

Compensating Controls: `<controls>`

Exception Expiration Date: `<date>`

Regression Remediation Plan: `<plan>`

Outside SME: `<outside_sme>`

Sub-IPT Lead Decision: `<approved_or_not_approved>`

Outside SME Decision: `<approved_or_not_approved>`

## New or materially changed interface

Complete this section only when a new interface or material change to an existing interface lacks an established independent verification baseline.

Additional Approval Required: `<yes_or_no>`

Independent Source of Expected Behavior: `<source>`

Sub-IPT Lead Decision: `<approved_or_not_approved>`

Outside SME Decision: `<approved_or_not_approved>`

## SME board review

Qualification Status: TBD

Approval Date: TBD

Approving SMEs: TBD

Review Findings: TBD

Conditions / Exclusions: TBD

Reapproval Triggers: TBD
