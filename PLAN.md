# Program plan

Status: DRAFT

Owner: TBD

Approved By: TBD

Approval Date: TBD

Last Updated: 2026-08-30

## Objective

Adopt AI code generation through bounded, evidence-based use cases that keep human engineers accountable for the resulting code. Build toward greater AI autonomy only as verification becomes strong enough to support it.

## Scope

This plan covers the proposed adoption model for AI-assisted code generation, including use-case selection, review, evidence, human responsibility, and the conditions for expanding autonomy.

Current scope assumes developer-in-the-loop code generation through an approved IDE extension. Autonomous or agentic development is a future capability to account for, but it is outside the current scope.

This plan does not grant permission to use AI for any use case or through any tool. Approved directives remain the source of truth for operational instructions.

## Current priorities

* Define a lightweight process for teams to propose valuable code-generation use cases.
* Establish a small cross-team subject-matter expert and point-of-contact group to review proposed use cases.
* Define the evidence needed to show that a use case produces correct code and a measurable engineering benefit.
* Set boundaries for each approved use case and the verification needed before those boundaries can expand.

## Requirements

* Keep a human developer in the loop for current code-generation use cases.
* Limit current engineering interaction to the approved IDE extension unless a later approved record changes that boundary.
* Approve bounded use cases, not general permission to generate code.
* Require evidence of both code correctness and engineering benefit.
* Keep human engineers responsible for understanding, reviewing, testing, and submitting generated code.
* Treat repository-scale access as access, not evidence that an AI system understands the repository.
* Tie any increase in AI autonomy to stronger, demonstrated verification.

## Operating model

The following statements are planning assumptions. They are not active instructions while this plan remains in `DRAFT`:

1. Teams identify code-generation use cases that could improve their engineering work.
2. A small cross-team subject-matter expert and point-of-contact group reviews each proposed use case.
3. Reviewers assess the use case's boundaries, expected benefit, correctness evidence, testing approach, and human oversight.
4. Approval applies only to the reviewed use case and its stated boundaries. It does not confer general permission to generate code.
5. Human engineers understand, review, test, and submit generated code through the normal engineering workflow.
6. Evidence from approved use cases informs whether stronger verification can support greater autonomy in later phases.

## Implementation plan

### Phase 1

Operate developer-in-the-loop code generation through the approved IDE extension. Define the use-case proposal, review, evidence, and approval process before treating any proposed use case as authorized.

### Phase 2

Evaluate bounded use cases. Collect correctness evidence and evidence of engineering benefit while keeping human engineers responsible for the resulting code.

### Phase 3

Define stronger verification levels and the additional autonomy each level can safely support. Agentic development remains out of scope until a later decision defines its controls, evidence threshold, and approval path.

## Active work

* Review and approval of this adoption strategy.
* Assignment of plan ownership and approval authority.
* Definition of the cross-team review group, submission process, and evaluation criteria.
* Definition of correctness and engineering-benefit evidence for initial use cases.

## Risks

* Sensitive context may be copied from private discussions into this public repository.
* Draft material may be mistaken for approved direction if metadata is incomplete.
* Generated code may pass narrow tests without fitting repository-wide behavior, architecture, or conventions.
* Repository-scale access may create misplaced confidence in repository-scale understanding.
* Engineering benefit may be asserted without a useful baseline or repeatable measurement.
* A use-case approval may be interpreted as general approval for a tool or development method.
* Review overhead may outweigh the benefit of low-value use cases.

## Dependencies

* Named plan owner and approval authority: TBD.
* Membership and authority of the cross-team review group: TBD.
* A documented path for proposing, reviewing, approving, and revisiting bounded use cases: TBD.
* Verification methods appropriate to each use case and repository.
* A practical method for measuring engineering benefit against a baseline: TBD.

## Open questions

* Who owns this plan?
* Who selects the cross-team reviewers, and what approval authority do they hold?
* What minimum correctness evidence is required before a use case can be approved?
* How should teams measure engineering benefit, and over what period?
* What changes to a use case require a new review?
* What verification levels would justify greater AI autonomy?
* What evidence and controls would be required before agentic development enters scope?

## Deferred ideas

* Autonomous or agentic development.
* Engineering interaction through tools other than the approved IDE extension.
* Repository-wide permission based only on repository-wide tool access.

## Related decisions

None.
