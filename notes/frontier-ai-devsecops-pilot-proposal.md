# Working proposal: Frontier AI pilot for DevSecOps activities

> NON-AUTHORITATIVE: This working proposal is under development. It does not record approval, authorize spending, or change AI-use policy.

Status: WORKING DRAFT

Owner: TBD

Target Audience: `<leadership_role>`

Related Directive: [DIR-001: AI tool data and output usage](../directives/DIR-001-ai-model-data-and-usage-policy.md)

Evidence Basis: `<internal_source_reference>`

## Context

Leadership has established a goal of reducing software cycle time through AI adoption. Based on current testing and team experience, `<current_internal_ai_tool>` is unlikely to achieve the `<target_cycle_time_reduction>` objective by itself.

The current tool has demonstrated value for narrow, low-complexity tasks, such as generating diagnostic output or assisting with straightforward error-handling code. These uses can save time, but they occur intermittently and do not represent enough of the team's daily work to produce a sustained cycle-time reduction.

This does not mean the current tool has no value. Its demonstrated strengths should be treated as one part of the adoption strategy rather than the sole path to the productivity objective.

## Opportunity

Existing policy permits Level 3 frontier AI models to support qualifying non-IP, non-deliverable activities when applicable input and output restrictions are followed. Level 3 treatment does not make those tools company-approved for company-IP or deliverable use. DevSecOps work that can be performed without company IP represents a potential opportunity for this type of use.

Teams frequently need to establish or modify CI workflows, evaluate available tools, develop internal automation, and operate within version or installation constraints imposed by secured environments. These tasks often require research, troubleshooting, and reasoning across multiple possible approaches.

Frontier models such as ChatGPT or Claude may help engineers identify compatible solutions, evaluate alternatives, and develop workable approaches when the task can be performed within the Level 3 restrictions defined by DIR-001.

## Proposed pilot

The Integrated Product Team (IPT) should sponsor a limited, time-bounded pilot that provides selected engineers with access to qualifying frontier AI models for DevSecOps-related activities that remain within applicable Level 3 restrictions.

Participants should:

* have active CI, automation, or internal tooling work suitable for non-IP frontier-model use;
* voluntarily participate and consistently use the capability;
* comply with all applicable data-input and output-use restrictions; and
* record measurable results from representative tasks.

The pilot would not replace the existing internal AI tool or relax security requirements. Its purpose would be to evaluate whether stronger models can produce meaningful gains in policy-compliant, non-deliverable engineering work.

## Measurements

Participants should record:

* time required to create or modify a pipeline;
* engineering hours saved compared with the existing process;
* recurring manual work eliminated through automation;
* issues identified earlier in the development lifecycle;
* rework or troubleshooting avoided;
* successful and unsuccessful AI-assisted attempts; and
* reusable workflows developed during the pilot.

These results should be compared with license costs and the baseline effort for similar work.

## Requested outcome

Leadership is requested to sponsor and fund a limited frontier AI pilot for selected DevSecOps users, designate an owner for collecting results, and review the measured outcomes before deciding whether broader access is justified.

The pilot would provide evidence for determining whether frontier AI access can contribute materially to the program's cycle-time objective while remaining within existing data-use restrictions.
