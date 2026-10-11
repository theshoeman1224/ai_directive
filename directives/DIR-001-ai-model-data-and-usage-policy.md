# DIR-001: AI tool data and output usage

Status: DRAFT

Owner: TBD

Approved By: TBD

Approval Date: TBD

Effective Date: TBD

Review Date: TBD

Related Decisions: None

> DRAFT: This proposed directive is not active and grants no permission.

## Purpose

Define which AI tools may receive company intellectual property (IP) and how their outputs may be used.

## Data-use levels

AI tools are assigned one of three data-use levels. Level 1 and Level 2 tools are company-approved. Any tool not separately approved as Level 1 or Level 2 is treated as Level 3.

| Level | Company IP as Input | Output in Deliverable Products |
|---|---|---|
| **Level 1** | Allowed | Allowed |
| **Level 2** | Allowed | Not allowed |
| **Level 3** | Not allowed | Not allowed |

### Level 1 — Deliverable-capable

**Current tool:**

* <level_1>

Company IP may be provided to the tool. Output may be incorporated into deliverable products when all other applicable requirements are satisfied.

### Level 2 — Internal-use only

**Current tool:**

* <level_2>

Company IP may be provided to the tool. AI-generated output must not be incorporated into deliverable products.

### Level 3 — Non-IP use only

**Current tools:**

* All AI tools and services not separately approved as Level 1 or Level 2, including ChatGPT and Claude.

Company IP must not be provided to Level 3 tools, and their outputs must not be incorporated into deliverable products.

## Tool selection

Users may use any AI tool whose data-use level permits both the intended input and intended use of the output.

For example, ChatGPT or Claude may be used for non-IP, non-deliverable work because they are treated as Level 3 unless separately approved at another level.

## Restrictions

Tool approval does not override contractual, security, export-control, data-handling, engineering, or other applicable requirements.

Approval of an AI tool does not automatically approve every interface, interaction mode, CLI, or agentic capability associated with that tool.

For AI-generated source code intended for customer deliverables, users must also comply with DIR-002 and DIR-003.

## Related directives

* [DIR-002: Code generation for customer deliverables](DIR-002-code-generation-customer-deliverables.md)
* [DIR-003: AI-assisted code-generation module qualification](DIR-003-ai-code-generation-module-qualification.md)

## Related communications

None.
