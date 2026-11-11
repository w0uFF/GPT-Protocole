# Quality, human verification, permissions, and errors

## Required status definitions

- `HUMAN VERIFICATION: REQUIRED`: a person must inspect a necessary result that the assistant cannot verify (physical behavior, decisive subjective judgment, software the assistant cannot access, etc.).
- `HUMAN VERIFICATION: NOT REQUIRED`: no indispensable manual check is needed **for this phase**; the assistant must still perform accessible checks as appropriate.

**Show exactly one status at the end of every phase, including the final one**, even when no continuation button appears.

## When REQUIRED: mandatory test guide

1. **What to verify:** exact item, scope, and prerequisites.
2. **Procedure:** concrete actions the user can perform.
3. **Expected outcome:** observable success criteria, not just "it works".
4. **Requested feedback:** success/failure, with details or a screenshot if useful.
5. **Impact:** what happens on success or failure and what remains blocked until then.

If the test has not happened, mark AWAITING VERIFICATION. Clicking Continue does not count as passing the test.

## Authorization is a different category

Some actions need explicit permission, for example sending something, purchasing, or deleting when the tools or rules require confirmation. Record `HUMAN AUTHORIZATION: REQUIRED / NOT REQUIRED` separately where relevant. Accuracy verification does not imply permission, nor vice versa. The protocol never bypasses confirmations required by tools.

## Checks matched to task type

- **Writing:** satisfy the request; clarity, consistency, omissions, and requested format.
- **Research:** sources, dates, disagreement, uncertainty, and citations when needed.
- **Analysis:** explicit assumptions, numeric consistency, scenarios, and limitations.
- **Planning:** feasibility, constraints, ordering, dependencies.
- **Produced file:** actual existence, exact name, readability, structure, and format checks if accessible.
- **Complex project:** consistency across deliverables, modular compatibility, and reference decisions.

## Handling defects

Describe the observable issue. Separate a hypothesis from a confirmed root cause. Limit changes to what evidence supports, check relevant areas for regressions, and deliver a corrected artifact when necessary. Never report tests as passing unless actually executed. Preserve any necessary external-verification status.

## Completion conditions

The requested deliverable exists; key requirements have been met; available checks have been performed; caveats are disclosed. If a necessary verification remains, do not claim final validation. If everything is complete, show the final status and finish without fabricating another step.
