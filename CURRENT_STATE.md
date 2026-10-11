# Current state

Snapshot Date: 2026-10-11

Owner: TBD

## Currently active

The documentation structure is in place for review. [PLAN.md](PLAN.md) and four related directives describe a draft AI code-generation adoption strategy. They are not approved and create no active instruction.

## Approved

No plans, decisions, directives, or communications are recorded as approved.

## Work underway

* Review and approval of the module/component qualification model for normal developer-in-the-loop AI code generation.
* Definition of the authoritative approved-tool, approved-interface, and module-qualification records.
* Definition of required AI training and the completion window for newly introduced mandatory training.
* Definition of the AI-altered file header convention.
* Validation of the default AI-generated Merge Request review-size limit.
* Definition of the maximum temporary regression-exception duration and the evaluation required at expiration.
* Definition of the boundary for new interfaces or materially new capabilities requiring additional approval.
* Definition of higher-autonomy and agentic approval requirements under DIR-004.
* Development of a [working proposal for a limited frontier AI DevSecOps pilot](notes/frontier-ai-devsecops-pilot-proposal.md).

## Blocked

* Plan approval remains blocked until ownership, approval authority, qualification-record location, training requirements, provenance-header rules, and remaining reviewability/exception decisions are resolved.
* Directive activation remains blocked until required ownership, approval metadata, effective dates, and authoritative registers are established.
* DIR-004 activation is additionally blocked until higher-autonomy capability thresholds, approval authority, and mandatory human checkpoints are defined.

## Needs attention

* Validate whether the proposed default review-size limit should count all added source code or production code only.
* Confirm that temporary regression exceptions remain genuinely time bounded and require remediation progress at expiration.
* Ensure approved AI interfaces and autonomy levels are not inferred from tool approval alone.

## Next major actions

1. Assign plan ownership and approval authority.
2. Confirm the authoritative module-qualification and approved-interface records.
3. Finalize required AI training and completion windows.
4. Finalize the file-level AI provenance header.
5. Finalize the review-size rule.
6. Finalize temporary regression-exception duration and evaluation rules.
7. Define new-interface/material-capability boundaries.
8. Record an explicit decision if the strategy is approved.

## Active directives

None.

The following drafts are under review and impose no requirements:

* [DIR-001: AI tool data and output usage](directives/DIR-001-ai-model-data-and-usage-policy.md)
* [DIR-002: Code generation for customer deliverables](directives/DIR-002-code-generation-customer-deliverables.md)
* [DIR-003: AI-assisted code-generation module qualification](directives/DIR-003-ai-code-generation-module-qualification.md)
* [DIR-004: Higher-autonomy and agentic AI development](directives/DIR-004-full-ai-code-generation-approval.md)

[The directive example](directives/EXAMPLE-directive.md) is also not active and imposes no requirements.
