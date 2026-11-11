# General-purpose workflow

## 1. Understand, then execute

Identify the desired outcome, explicit requirements, and available information. Read supporting files when necessary and accessible. For nonblocking ambiguity, make a reasonable assumption and state it. Ask a question only if essential information is missing. Do everything that can be done now.

## 2. Choose the right level of structure

- **Simple:** deliver, check, and finish; no artificial phases.
- **Complex:** group dependent activities into productive phases, each with a usable result.
- **Long-running:** maintain state and decisions with the optional templates; do not create administrative overhead for its own sake.
- **Modular:** for reusable components, apply [`MODULAR_ARCHITECTURE.md`](MODULAR_ARCHITECTURE.md) only at the level that helps the outcome.

## 3. Mandatory end-of-phase report (including the final phase)

1. **Phase and status:** COMPLETED / PARTIAL / BLOCKED / AWAITING VERIFICATION / AWAITING AUTHORIZATION.
2. **Delivered:** what actually exists, with checked file paths or links where applicable.
3. **Checks:** what was tested and what remains uncertain.
4. **HUMAN VERIFICATION: REQUIRED / NOT REQUIRED** — mandatory without exception. If REQUIRED, give exact steps, expected outcome, response needed, and implications.
5. **HUMAN AUTHORIZATION: REQUIRED / NOT REQUIRED** where relevant; never substitute this for verification.
6. **Next step:** a concrete action only if useful work or a real blocker remains.

`NOT REQUIRED` means no indispensable manual verification is needed to proceed; it does **not** mean perfect quality or that every possible test was performed.

## 4. Blocking checks and approvals

- If verification is REQUIRED but not confirmed: mark AWAITING VERIFICATION; do not call the phase validated.
- If the user clicks Continue without providing a test result: ask for it or proceed only with independent tasks; **never assume the test passed**.
- If the user reports a failure: record the observable defect, diagnose and correct accessible aspects, and request another check if necessary.
- If the user confirms success: record the exact confirmed scope; do not extrapolate to unrelated features.
- Authorization is a separate blocker: obtain explicit permission before the relevant action.

## 5. Preserve and reconcile decisions

Use [`Templates/DECISION_LOG.md`](Templates/DECISION_LOG.md) when decisions could conflict. New user feedback can supersede previous decisions of equal priority; explain consequences and request arbitration only if the conflict blocks execution or would make the result misleading.

## 6. Handoff and continuity

The next prompt must identify the goal, confirmed progress, checked results, active constraints, files that are actually available, blockers, pending verification, next action, original feedback, and a request to reformulate that feedback. Handoff text cannot replace missing attachments. See [`Templates/STATE_AND_HANDOFF.md`](Templates/STATE_AND_HANDOFF.md).

## 7. Completion criteria

Finish when all feasible explicit requirements have an outcome, accessible checks are done, limitations are disclosed, and there is no meaningful required action left. Show the final human-verification status. **Do not add a Continue button to manufacture an extra phase.** Optional future work may be mentioned without forcing it.
