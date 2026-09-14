# MIE366 Requirements and Traceability

## Current Baseline

Initial DA1 source extraction recorded on 2026-09-14 from the supplied
assignment handouts. The current research scope is DA1, “Design Proposal.”
No design response, simulation, physical test, or student-accepted
interpretation is implied by this extraction.

Rows are Unreviewed pending requirement review, or Needs Review where an
interpretation remains unresolved. None is Verified. Source wording such
as “should,” strict page inequalities, and the endpoint-error allowance
is retained rather than silently strengthened or weakened.

Verification Method entries are proposed future checks unless the
handout explicitly requires the method. They are not an accepted test
plan or evidence that a requirement passed.

See [DA1 source review](research/DA1_SOURCE_REVIEW.md) for source context,
advice separated from constraints, and open questions Q01–Q06.

## Source Key

Page numbers are 1-based PDF pages; the numbered handout pages agree.

- **DA1A**: [MIE366 - Design Assignment 1A, Background Handout v1.1.pdf](<source-docs/MIE366 - Design Assignment 1A, Background Handout v1.1.pdf>).
- **DA1B**: [MIE366 - Design Assignment 1B, Deliverable Handout v1.1.pdf](<source-docs/MIE366 - Design Assignment 1B, Deliverable Handout v1.1.pdf>).
- **ROADMAP**: [MIE366 - Design Assignment Roadmap v1.2.pdf](<source-docs/MIE366 - Design Assignment Roadmap v1.2.pdf>).
- Component evidence is kept separately in the source review; datasheet
  limits do not become additional assignment requirements by default.

## Traceability Matrix

| ID | Requirement | Source | Type | Design Response | Verification Method | Evidence | Status |
| --- | --- | --- | --- | --- | --- | --- | --- |
| R001 | [REQ] Design the CURRENT SENSE block identified in the background handout. | DA1B p. 1; DA1A p. 4 | Functional | Not yet planned | Scope review against the supplied block diagram | None recorded | Unreviewed |
| R002 | [REQ] Accept returning load current over 0–3.5 A. | DA1B p. 3, INPUT | Electrical | Not yet planned | Final-design simulation over the stated input range | None recorded | Unreviewed |
| R003 | [REQ] Use low-side sensing, with the low side of the sense resistor tied to circuit ground. | DA1B pp. 2–3 | Electrical | Not yet planned | Schematic connectivity inspection | None recorded | Unreviewed |
| R004 | [REQ] Include a 0.1 Ω sense resistor in the design. | DA1B pp. 2–3 | Component | Not yet planned | Schematic and component-value inspection | None recorded | Unreviewed |
| R005 | [REQ] Provide one voltage output representing load current. | DA1B p. 3, OUTPUT | Functional | Not yet planned | Schematic interface inspection | None recorded | Unreviewed |
| R006 | [REQ] Target the linear-with-offset mapping from 0.25 V at 0 A to 3.3 V at 3.5 A; preserve the p. 9 allowance for small endpoint deviations. | DA1B pp. 3, 7, 9 | Electrical | Not yet planned | Compare simulated transfer with the source target; quantitative error limits unresolved (Q01) | None recorded | Needs Review |
| R007 | [REQ] Use no more than three op-amp units (three of the four in one LM324 chip). | DA1B p. 3, CONSTRAINTS | Component | Not yet planned | Count amplifier units in the schematic | None recorded | Unreviewed |
| R008 | [REQ] Use LM324N op-amps; the handout points to the labs for the LTspice model. | DA1B p. 3, CONSTRAINTS | Component | Not yet planned | Check device identity and model provenance; see Q03 | None recorded | Unreviewed |
| R009 | [REQ] Power the op-amps from a single +19 V supply: V+ = +19 V and V− = 0 V. | DA1B p. 3, CONSTRAINTS | Electrical | Not yet planned | Inspect supply connections and simulation conditions | None recorded | Unreviewed |
| R010 | [REQ] Select every resistor other than the sense resistor within 1 kΩ–100 kΩ. | DA1B p. 3, CONSTRAINTS | Component | Not yet planned | Inspect nominal values against the permitted range | None recorded | Unreviewed |
| R011 | [REQ] Select those non-sense resistors from the standard 5% values in Appendix A. | DA1B pp. 3, 10 | Component | Not yet planned | Check nominal values against the permitted Appendix A entries | None recorded | Unreviewed |
| R012 | [REQ] Do not use series/parallel combinations to create equivalent resistances outside 1 kΩ–100 kΩ; the specified sense resistor is the exception. | DA1B p. 3, CONSTRAINTS | Component | Not yet planned | Review any resistor combinations and their equivalents | None recorded | Unreviewed |
| R013 | [REQ] Use only the permitted op-amps and resistors in the designed circuit; no capacitors, inductors, diodes, transistors, or other components. | DA1B pp. 3, 8 | Component | Not yet planned | Inspect the design component list; distinguish permitted simulation stimuli | None recorded | Unreviewed |
| R014 | [REQ] Include Engineering Specification and Background Research, summarizing relevant building blocks, their core functionality, limitations, and a plan for integration. | DA1B p. 4, Deliverable 1 | Deliverable | Not yet planned | Review the report section and its supporting references | None recorded | Unreviewed |
| R015 | [REQ] The Engineering Specification and Background Research section is labelled <1 page. | DA1B p. 4, Deliverable 1 | Deliverable | Not yet planned | Check section length; preserve the stated inequality (Q02) | None recorded | Needs Review |
| R016 | [REQ] Present two candidate designs addressing the problem. | DA1B p. 4, Deliverable 2 | Deliverable | Not yet planned | Check that two candidate designs are documented | None recorded | Unreviewed |
| R017 | [REQ] Represent each candidate with a schematic or block diagram. | DA1B p. 4, Deliverable 2 | Deliverable | Not yet planned | Inspect both candidate representations | None recorded | Unreviewed |
| R018 | [REQ] Give a brief functionality description for each candidate; selected equations or key results are optional supporting material. | DA1B p. 4, Deliverable 2 | Deliverable | Not yet planned | Review both functionality descriptions | None recorded | Unreviewed |
| R019 | [REQ] The Candidate Designs section is labelled <2 pages. | DA1B p. 4, Deliverable 2 | Deliverable | Not yet planned | Check section length; preserve the stated inequality (Q02) | None recorded | Needs Review |
| R020 | [REQ] Show a final design developed from the candidate work, with a fully designed schematic and a description of changes or modifications where applicable; combination or modification of candidates is allowed. | DA1B p. 4, Deliverable 3 | Deliverable | Not yet planned | Trace final design development to the candidates and inspect the final schematic | None recorded | Unreviewed |
| R021 | [REQ] Briefly discuss and justify the final design relative to the candidates (source wording: should). | DA1B p. 4, Deliverable 3 | Deliverable | Not yet planned | Review the selection rationale | None recorded | Unreviewed |
| R022 | [REQ] The final schematic should show the +19 V op-amp supply, current input, and voltage output. | DA1B p. 4, Deliverable 3 | Deliverable | Not yet planned | Inspect the external connections on the final schematic | None recorded | Unreviewed |
| R023 | [REQ] Simulate the final design under YOUR Design Goals; LTspice or other software is permitted. | DA1B p. 4, Deliverable 3; p. 3 | Simulation | Not yet planned | Inspect the simulation model, stimuli, supply conditions, and results | None recorded | Unreviewed |
| R024 | [REQ] Include simulation results and a brief discussion demonstrating feasibility and how the design solves the stated problem. | DA1B p. 4, Deliverable 3 | Deliverable | Not yet planned | Review the evidence against the stated requirements; tool execution alone is insufficient | None recorded | Unreviewed |
| R025 | [REQ] The Final Candidate section is labelled <3 pages. | DA1B p. 4, Deliverable 3 | Deliverable | Not yet planned | Check section length; preserve the stated inequality (Q02) | None recorded | Needs Review |
| R026 | [REQ] The document should be no more than six pages; the cover page and appendices do not count toward that limit. | DA1B p. 4, Deliverable Constraints | Deliverable | Not yet planned | Count applicable pages; reference-section treatment remains unspecified (Q02) | None recorded | Needs Review |
| R027 | [REQ] Use a minimum font size of 11 pt. | DA1B p. 4, Deliverable Constraints | Deliverable | Not yet planned | Inspect the final document formatting | None recorded | Unreviewed |
| R028 | [REQ] Submit the document in PDF format only. | DA1B p. 4, Deliverable Constraints | Deliverable | Not yet planned | Inspect the submission format | None recorded | Unreviewed |
| R029 | [REQ] Include a cover page with both partners' names and student numbers (source wording: should). | DA1B p. 4, Deliverable Constraints | Deliverable | Not yet planned | Inspect the cover page | None recorded | Unreviewed |
| R030 | [REQ] Omit extraneous abstract, executive summary, table of contents, problem introduction/explanation, conclusion, and similar sections; keep the report mainly schematics, equations, and minimal explanatory text (source wording: should). | DA1B p. 4, Deliverable Constraints | Deliverable | Not yet planned | Review the report structure and concision | None recorded | Unreviewed |
| R031 | [REQ] Use appendices for large graphics such as schematics/results; label figures and make them legible and appropriately sized. | DA1B p. 4, Deliverable Constraints | Deliverable | Not yet planned | Visually inspect figure placement, labels, and readability | None recorded | Unreviewed |
| R032 | [REQ] Reference use or application of existing works, including circuit fragments, in a clearly labelled reference section with specific numbered citations in the text. | DA1B p. 4, Deliverable Constraints | Deliverable | Not yet planned | Audit borrowed material, in-text citations, and reference entries | None recorded | Unreviewed |
| R033 | [REQ] Submit online through the provided submission link. | DA1B pp. 1, 4 | Process | Not yet planned | Confirm the current course submission destination and submission receipt (Q04) | None recorded | Unreviewed |
| R034 | [REQ] Work in a group of two. | DA1A p. 1; DA1B p. 1 | Process | Not yet planned | Check team details | None recorded | Unreviewed |
| R035 | [REQ] The handouts state September 21, end-of-day, Toronto time as the deadline; no year or precise cutoff is stated. | DA1A p. 1; DA1B p. 1; ROADMAP p. 1 | Process | Not yet planned | Confirm the applicable course year and current portal deadline (Q04) | None recorded | Needs Review |

## Entry Rules

- Assign stable IDs in sequence: R001, R002, and so on.
- Preserve the source's exact meaning, limits, units, and conditions.
- Include source filename and page/section where available.
- Record the applicable assignment stage in Source when established.
- Distinguish explicit requirements from provisional interpretations.
- Keep assumptions labeled [ASSUMPTION]; do not silently turn them
  into requirements.
- Link Design Response to relevant decision IDs and engineering files.
- In Verification Method, specify both the method and acceptance criteria.
- In Evidence, link the result, relevant design revision, conditions,
  and limitations.
- Use "Not yet assessed" or "Not yet defined" where appropriate.
- Preserve conflicting evidence and identify interpretations requiring
  student or instructor clarification.

## Requirement Types

Functional / Electrical / Component / Simulation / Physical /
Deliverable / Process

Choose the type supported by the requirement's actual scope.

## Status Definitions

- Unreviewed: recorded from a source; interpretation is not yet assessed.
- Understood: meaning and applicable conditions have been reviewed;
  significant interpretation questions are resolved.
- Planned: a design response and verification approach are identified.
- Implemented: the design response exists; verification is incomplete.
- Verified: applicable evidence demonstrates the acceptance criteria.
- Failed: applicable evidence demonstrates that a criterion is not met.
- Needs Review: ambiguity, conflicting evidence, or a change requires
  reassessment.

A simulation completing successfully does not by itself establish
Verified status. Apply the verification rules in AGENTS.md.

When a revision undermines previous verification, retain the evidence
and mark the affected requirement Needs Review until reassessed.

## Evidence Labels

Use the labels defined in AGENTS.md:

[REQ] / [DATASHEET] / [RESEARCH] / [DERIVED] / [SIM] / [TEST] /
[ASSUMPTION]

Labels supplement source references and evidence links.
