# DIR-002: Code generation for customer deliverables

Status: DRAFT

Owner: TBD

Approved By: TBD

Approval Date: TBD

Effective Date: TBD

Review Date: TBD

Related Decisions: None

> DRAFT: This proposed directive is not active and grants no permission.

## Purpose

Define the conditions under which AI-generated source code may enter a customer-deliverable branch or be delivered to a customer.

## Scope

This directive applies to AI-generated source code intended for customer delivery.

## Required actions

Before AI-generated source code enters a customer-deliverable branch or customer delivery:

* use only an AI tool whose data-use level permits deliverable output under DIR-001;
* confirm that the applicable contract permits AI-generated source code in customer deliverables;
* ensure the affected module or component is qualified under DIR-003, or the work is covered by an active DIR-003 exception or additional approval;
* follow the normal engineering, testing, verification, qualification, release, and human code-review processes required for the software; and
* ensure human reviewers determine that the generated code is correct and acceptable. Passing automated tests alone is not sufficient.

All existing safety, security, mission, architecture, qualification, and release requirements remain applicable.

## AI-altered file identification

Every source file altered using AI-generated code must include a file-level header indicating that AI was used to alter the file.

The header must remain compatible with the file's language and existing header conventions and must not obscure required copyright, classification, licensing, change-history, or other mandated header content.

**TODO: Define the exact standard header wording, placement, rules for controlled or standardized headers, and whether the header is permanent or may later be removed under an approved condition.**

Human reviewers must verify the required AI-alteration header before accepting the change.

## Related directives

* [DIR-001: AI tool data and output usage](DIR-001-ai-model-data-and-usage-policy.md)
* [DIR-003: AI-assisted code-generation module qualification](DIR-003-ai-code-generation-module-qualification.md)

## Related communications

None.
