# MIE366 Project Status

## Current HVE Phase

Research.

Reason: the four supplied sources establish DA1 scope, but candidate
research and several acceptance/model details remain unresolved.

Exit condition: source-backed requirements, applicable component/model
evidence, and explicit acceptance criteria sufficient for a defensible
candidate plan; significant interpretations require student acceptance.

## Current Objective

Build the student's understanding of DA1 through small, source-backed
steps, then resolve the highest-impact evidence gaps before planning
candidate circuits.

Current learning checkpoint: explain the potential low-current error of
a unity-gain buffer connected directly to V_SENSE, using the handout's
output-floor approximation (DA1B p. 6; Q03/Q05). This is a building-block
exercise, not an accepted buffer placement. Use one question at a time,
with hints before answers.

Learning progress: the student identified R_SENSE as the measurement
source and correctly calculated (3.5 A)(0.1 Ω) = 0.35 V [DERIVED]. The
student's gain of 8.714 is correct to three decimal places:
A = (3.3 V - 0.25 V)/(0.35 V - 0 V) = 8.714285... V/V [DERIVED]. The
nominal target is V_OUT = A V_SENSE + 0.25 V (R006; DA1B pp. 3, 7), with
no resistor network or circuit topology selected. The
student identified the hardware motivation for the nonzero output target
in DA1B p. 5. Its approximately 0.1 V output floor remains a teaching
approximation pending Q03/Q05, not an accepted universal device limit.
The zero-input algebra and zero-voltage/open-circuit distinction were
deferred at the student's request; understanding is not yet confirmed.
The grill-me exchange ended without a design-acceptance gate outcome.

## Current Assignment Stage

DA1 — Design Proposal, based on the supplied detailed handouts.
Current course-year scheduling and any work outside this repository
have not been confirmed.

## Completed

- Workspace setup and final repository validation (Sections 2–8).
- Four source PDFs added by the student and inspected.
- Initial DA1 requirement extraction: R001–R035.
- Source review recorded in research/DA1_SOURCE_REVIEW.md, including
  assignment constraints, separate design hints, and datasheet cautions.

## In Progress

- Requirement interpretation and acceptance-criteria review.
- Research preparation for the two candidate designs.

## Blocked / Unknown

- Q01: exact output-error and tolerance acceptance criteria.
- Q02: section-page allocations and reference-section counting.
- Q03/Q05: lab LM324N model, applicable device/loading conditions, and
  the handout/datasheet output-swing discrepancy.
- Q04: the handouts say September 21, end-of-day, Toronto time, but
  omit year and precise cutoff; current course posting needs confirmation.
- Building-block research is not yet completed (Q06).

## Next Actions

- Start with the current learning checkpoint and assess the student's
  explanation before advancing to the next concept.
- Review REQUIREMENTS.md and the open questions in the source review.
- Resolve acceptance/model evidence and gather primary building-block
  research; see TODO.md.
- Use mie366-grill-me before accepting consequential interpretations
  or a major candidate/design choice.

## Open Decisions

No engineering decisions accepted. Open interpretations are recorded
as Q01–Q06 in research/DA1_SOURCE_REVIEW.md.

## Latest Major Decision

None recorded.

## Latest Evidence Added

[REQ] DA1A/DA1B v1.1 and roadmap v1.2.
[DATASHEET] Supplied TI LM324-N-family datasheet, SNOSC16D.
Source filenames and page references are in research/DA1_SOURCE_REVIEW.md.
No simulation or physical test evidence is recorded.

## Last Updated

2026-09-14 — gain calculation checked; buffer-limit checkpoint pending.
