# DIR-003: AI tool data and output usage

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

Define which AI tools may receive program intellectual property (IP), how their outputs may be used, and how users should select an AI tool for a task.

## Data-use levels

Program-approved AI tools are assigned one of three data-use levels.

| Level | Program IP as Input | Output in Deliverable Products |
|---|---|---|
| **Level 1** | Allowed | Allowed |
| **Level 2** | Allowed | Not allowed |
| **Level 3** | Not allowed | Not allowed |

### Level 1 — Deliverable-capable

Program IP may be provided to the AI tool.

Output may be incorporated into deliverable products when all other applicable program requirements are satisfied.

**Current tool:**

* Poolside

Use of AI-generated source code remains subject to the code-generation requirements defined by DIR-001 and DIR-002.

### Level 2 — Internal-use only

Program IP may be provided to the AI tool.

AI-generated output must not be incorporated into deliverable products.

**Current tool:**

* Microsoft Copilot

### Level 3 — Non-IP use only

Program IP must not be provided to the AI tool.

AI-generated output must not be incorporated into deliverable products.

**Current tools:**

* All AI tools and services not separately approved as Level 1 or Level 2, including ChatGPT and Claude

## Examples of non-deliverable use

Subject to the input restrictions of the selected data-use level, Level 2 and Level 3 tools may be used for non-deliverable activities such as:

* Researching algorithms, libraries, tools, or engineering approaches.
* Brainstorming designs or alternative implementations.
* Troubleshooting errors and developing debugging approaches.
* Developing prompts, workflows, or AI use-case proofs of concept.
* Developing or configuring CI and internal scripts that will not enter a customer-deliverable baseline or be released to customers.

For Level 2 tools, program IP may be included as input. For Level 3 tools, all inputs must remain free of program IP.

These examples are non-exhaustive and do not authorize an activity by themselves. The input data and intended use of the output must comply with the tool's assigned level. Level 2 and Level 3 outputs must remain outside deliverable products.

## Tool selection

Users should use the most capable approved AI tool whose data-use level supports the task.

The broad permissions of a Level 1 tool do not make it the preferred tool for every task.

When a task does not require program IP and its output will not enter a deliverable product, users should prefer capable frontier AI models such as ChatGPT or Claude over Poolside when those services are approved for use.

When program IP is required but the AI output will not enter a deliverable product, a Level 2 tool should generally be preferred when it provides better capability than the available Level 1 tool.

Level 1 tools should primarily be used when the task requires permissions unavailable at the other levels, particularly when:

* program IP must be provided and no suitable Level 2 tool exists, or
* AI-generated output is intended for a deliverable product.

## Restrictions

Tool approval does not override other program, contractual, security, export-control, data-handling, or engineering requirements.

Users must:

* determine the required data-use level before selecting an AI tool,
* provide program IP only to tools approved to receive it,
* prevent Level 2 and Level 3 outputs from entering deliverable products, and
* comply with any additional use-case approval requirements applicable to the work.

## Exceptions

None currently exist.

## Verification and compliance

Compliance requires that:

* the AI tool is approved for the data provided to it,
* the intended use of the output is permitted by the tool's assigned level, and
* any additional program-level approval required for the activity has been obtained.

## Related directives

* [DIR-001: Code generation for customer deliverables](DIR-001-code-generation-customer-deliverables.md)
* DIR-002: Program-level AI code-generation use-case approval

## Related communications

None.
