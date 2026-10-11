# DIR-004: Higher-autonomy and agentic AI development

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

Define the additional controls required before teams may use AI software-development capabilities that operate with greater autonomy than the normal developer-in-the-loop model governed by [DIR-003](DIR-003-ai-code-generation-module-qualification.md).

This directive is intentionally separate from module qualification. Approval of a module under DIR-003 does not authorize agentic or higher-autonomy development within that module.

## Scope

This directive applies to AI capabilities that can perform one or more software-development actions with materially increased autonomy, including examples such as:

* inspecting or traversing multiple files without a developer selecting each file;
* modifying multiple files as part of a single autonomous workflow;
* executing build, test, analysis, or repository commands;
* iterating on failures without a human approving each modification cycle;
* creating or modifying branches, commits, or Merge Requests; or
* otherwise taking engineering actions beyond the currently approved developer-in-the-loop interaction model.

The exact boundary between normal assistive use and higher-autonomy use must be defined through the authoritative approved-interface and interaction-mode source referenced by DIR-003.

**TODO: Define the formal capability threshold that requires DIR-004 approval and identify the authoritative inventory of approved interaction modes.**

## Relationship to other directives

DIR-001 continues to govern AI-tool data and output eligibility.

DIR-002 continues to govern AI-generated source code intended for customer deliverables.

DIR-003 continues to govern module/component qualification, required user training, regression expectations, human responsibility, reviewability, and normal developer-in-the-loop usage.

Approval under this directive is additive. It does not replace or weaken requirements from DIR-001, DIR-002, or DIR-003.

## Approval basis

Higher-autonomy approval must be based on the specific capabilities being requested, the software scope in which they will operate, and the controls available to bound and observe those capabilities.

At minimum, an approval request should identify:

* the AI tool and interface;
* the autonomous capabilities requested;
* repositories, modules, directories, commands, or resources the capability may access;
* actions that remain prohibited;
* required human checkpoints;
* rollback and recovery mechanisms;
* logging or audit evidence produced by the workflow;
* applicable testing and regression controls; and
* how the team will detect and contain unintended behavior.

**TODO: Define the authoritative submission template and approval body for higher-autonomy requests.**

## Human control points

Higher-autonomy tooling must not eliminate human accountability for delivered software.

Approvals must define where human authorization is required before the AI may proceed, including where applicable:

* before reading or modifying sensitive areas;
* before executing commands with material side effects;
* before expanding beyond the requested task scope;
* before committing or submitting generated changes; and
* before any customer-deliverable integration action.

**TODO: Define minimum mandatory human checkpoints for each autonomy category.**

## Software-assurance requirements

Higher-autonomy use may increase the volume and breadth of changes produced before human inspection. Therefore, the approved software scope must satisfy DIR-003 qualification requirements and may require stronger controls based on the capability requested.

Additional controls may include tighter change-size limits, stronger automated quality gates, more frequent regression execution, additional audit logging, constrained command allowlists, or mandatory staged review.

**TODO: Define which additional controls are mandatory by autonomy level rather than leaving every request fully bespoke.**

## Change size and reviewability

Higher-autonomy approval does not relax the reviewability protections in DIR-003.

The capability must not be used to generate or accumulate changes at a rate or scope that prevents meaningful human comprehension and review.

**TODO: Revisit change-size limits specifically for autonomous multi-file workflows after evidence is available from controlled pilots.**

## Suspension and revocation

Higher-autonomy approval may be suspended or revoked when:

* the approved capability operates outside its defined scope;
* required human checkpoints are bypassed;
* required audit evidence is unavailable;
* regression or other assurance controls materially degrade;
* repeated or severe defects are associated with the autonomous workflow; or
* the tool/interface changes materially from what was approved.

**TODO: Define quantitative or event-based suspension criteria after initial pilot evidence is available.**

## Exceptions

No exception under this directive may remove human accountability or authorize a data use, AI tool, module, or deliverable activity prohibited by DIR-001, DIR-002, or DIR-003.

## Verification and compliance

A team may use higher-autonomy or agentic development capabilities only when:

* the AI tool and interface are separately approved for the requested capability;
* the affected module or component is qualified under DIR-003;
* the higher-autonomy approval explicitly covers the requested actions and scope;
* required human checkpoints, audit controls, regression controls, and reviewability limits remain in place; and
* all applicable DIR-001, DIR-002, DIR-003, contractual, security, and engineering requirements are satisfied.

## Related directives

* [DIR-001: AI tool data and output usage](DIR-001-ai-model-data-and-usage-policy.md)
* [DIR-002: Code generation for customer deliverables](DIR-002-code-generation-customer-deliverables.md)
* [DIR-003: AI-assisted code-generation module qualification](DIR-003-ai-code-generation-module-qualification.md)

## Related communications

None.
