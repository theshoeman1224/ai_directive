# DIR-001: AI tool data and output usage

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

Define which AI tools may receive company intellectual property (IP), how their outputs may be used, and how to select an AI tool for a task.

## Data-use levels

AI tools are assigned one of three data-use levels. Level 1 and Level 2 tools are company-approved. A tool that is not separately approved as Level 1 or Level 2 is treated as Level 3 by default and is not a company-approved tool.

| Level | Company IP as Input | Output in Deliverable Products |
|---|---|---|
| **Level 1** | Allowed | Allowed |
| **Level 2** | Allowed | Not allowed |
| **Level 3** | Not allowed | Not allowed |

### Level 1 — Deliverable-capable

Company IP may be provided to the AI tool.

Output may be incorporated into deliverable products when all other applicable program requirements are satisfied.

**Current tool:**

* Poolside

Use of AI-generated source code remains subject to the code-generation requirements defined by DIR-002 and DIR-003.

### Level 2 — Internal-use only

Company IP may be provided to the AI tool.

AI-generated output must not be incorporated into deliverable products.

**Current tool:**

* Microsoft Copilot

### Level 3 — Non-IP use only

Level 3 is the default classification for tools that are not company-approved.

Company IP must not be provided to the AI tool.

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

For Level 2 tools, company IP may be included as input. For Level 3 tools, all inputs must remain free of company IP.

These examples are non-exhaustive and do not authorize an activity by themselves. The input data and intended use of the output must comply with the tool's assigned level. Level 2 and Level 3 outputs must remain outside deliverable products.

## Tool selection

Users may use whichever AI tool they prefer, provided the tool's data-use level supports the task.

The broad permissions of a Level 1 tool do not make it the preferred tool for every task.

When a task does not require company IP and its output will not enter a deliverable product, users may prefer capable frontier AI models such as ChatGPT or Claude over Poolside.

When company IP is required but the AI output will not enter a deliverable product, users may prefer a Level 2 tool when it provides better capability than the available Level 1 tool.

A Level 1 tool is needed when the task requires permissions unavailable at the other levels, particularly when:

* company IP must be provided and no suitable Level 2 tool exists, or
* AI-generated output is intended for a deliverable product.

## Restrictions

Approval of a tool, or its treatment as Level 3 by default, does not exempt users from other requirements. Program, contractual, security, export-control, data-handling, and engineering requirements all still apply.

Users must:

* determine the required data-use level before selecting an AI tool,
* provide company IP only to tools approved to receive it,
* prevent Level 2 and Level 3 outputs from entering deliverable products, and
* comply with any additional use-case approval requirements applicable to the work.

## Exceptions

None currently exist.

## Verification and compliance

Compliance requires that:

* the tool's data-use level permits the data provided to it,
* the intended use of the output is permitted by the tool's assigned level, and
* any additional program-level approval required for the activity has been obtained.

## Related directives

* [DIR-002: Code generation for customer deliverables](DIR-002-code-generation-customer-deliverables.md)
* [DIR-003: Program-level AI code-generation use-case approval](DIR-003-program-level-ai-use-case-approval.md)

## Related communications

None.
