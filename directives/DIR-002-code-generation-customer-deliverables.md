# DIR-002: Code generation for customer deliverables

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

Define the proposed conditions under which AI-generated source code may be merged into a customer-deliverable branch or delivered to a customer.

## Directive

Teams may evaluate code-generation approaches in a sandbox with any AI tool and interaction method whose data-use level permits the sandbox activity.

Before AI-generated source code enters a customer-deliverable branch or is delivered to a customer, the affected module or component must be qualified under [DIR-003](DIR-003-ai-code-generation-module-qualification.md), or the specific work must be covered by an active temporary exception or additional approval defined by that directive.

## Scope

This directive applies to AI-generated source code intended for release or delivery to a customer.

## Required actions

* Use only company-approved AI tools whose data-use level permits deliverable output.
* Confirm that the applicable contract permits AI-generated source code in customer deliverables.
* Keep sandbox output out of customer-deliverable branches and customer deliveries until the applicable module qualification or exception requirements are satisfied.
* Follow the module/component qualification, training, interaction-mode, reviewability, and additional-approval requirements defined in DIR-003.
* Follow the normal code-review process for customer-deliverable software.
* Apply the same engineering, testing, verification, qualification, and release requirements used for human-authored code.
* Have human reviewers determine whether generated code is correct and acceptable for delivery. Passing automated tests alone is not sufficient.

## AI-altered file identification

Every source file altered using AI-generated code must include a file-level header indicating that AI was used to alter the file.

The purpose of this header is to provide durable provenance without requiring the AI tool or developers to maintain line-level AI tags.

Line-by-line `-AI` tagging is not required.

The file-level header must remain compatible with the file's language and existing header conventions and must not obscure required copyright, classification, licensing, change-history, or other mandated header content.

**TODO: Define the exact standard header wording, placement, and rules for files that already contain controlled or standardized headers. Define whether the header remains permanently once AI has altered a file or may later be removed under an approved condition.**

Human reviewers must verify that affected files contain the required AI-alteration header before accepting the change.

## Safety-critical and specialized software

AI-generated source code intended for safety-critical or otherwise specially controlled applications remains subject to all previously applicable standards and team-defined review requirements.

DIR-002 and qualification under DIR-003 are additional controls, not replacements for existing safety, security, mission, architecture, qualification, or release requirements.

## Exceptions

None currently exist except where DIR-003 explicitly defines a temporary regression exception or additional approval path.

## Verification and compliance

Compliance requires evidence that:

* the AI tool is eligible for deliverable output under DIR-001;
* the affected module/component is qualified under DIR-003 or the specific work is covered by an active DIR-003 exception or additional approval;
* the engineer has satisfied applicable training requirements;
* the generated source code passed the normal engineering review and release process; and
* every AI-altered source file contains the required file-level AI header.

## Unresolved items

The following items must be resolved before this directive can become active:

* The authoritative approved-tool and approved-interface sources.
* The exact AI-altered file header convention and lifecycle.

## Related directives

* [DIR-001: AI tool data and output usage](DIR-001-ai-model-data-and-usage-policy.md)
* [DIR-003: AI-assisted code-generation module qualification](DIR-003-ai-code-generation-module-qualification.md)

## Related communications

None.
