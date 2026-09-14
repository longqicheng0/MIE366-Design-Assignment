# MIE366 Action List

Engineering phase: Research. Source intake is recorded in STATUS.md.
Requirement IDs refer to REQUIREMENTS.md; Q01–Q06 refer to
research/DA1_SOURCE_REVIEW.md. No engineering decisions are accepted yet.

## Now

- [ ] Gather cited building-block evidence and prepare a concise first
  section covering functionality, limitations, and a plan for integration
  (R014, R015, R032; DA1B p. 4). Content guidance clarified; drafting and
  source collection remain pending. Preserve the <1-page source label
  and unresolved page-count questions in Q02. Phase: Research.
- [x] Learning checkpoint: identify R_SENSE as the measurement source
  and calculate its voltage at 3.5 A (R002, R004). Student's 0.35 V result
  checked using V = IR. Phase: Research; no design verification implied.
- [x] Derive the gain from the sense-voltage and nominal output ranges
  (R006; DA1B pp. 3, 7). Student's 8.714 V/V is correct when rounded to
  three decimal places. Phase: Research; no circuit design selected.
- [x] Identify a resistor circuit that produces a fixed reference from
  +19 V, as background for buffered-reference and combined gain/offset
  building blocks (DA1B p. 8; R014). Student identified the divider and
  correctly checked its equal-resistor fraction after the unloaded
  formula was demonstrated. Phase: Research.
- [x] Recognize midpoint current splitting and identify the ideal buffer
  input property that avoids loading the divider (DA1B p. 8; R014).
  Student correctly identified ideally infinite input resistance.
  Phase: Research; real-device loading remains unassessed.
- [ ] Relate the weighted reference term b V_REF to the required output
  offset in a weighted sum (R006, R014; DA1B pp. 3, 8). Phase: Research.
- [ ] Derive the non-inverting summing input-node voltage, starting with
  equal input resistors and ideal sources, then connect it to feedback
  gain (R006, R014; DA1B p. 8). Feedback-gain derivation was shown;
  input-node and combined-weight derivations remain pending.
  Phase: Research. Student response pending.
- [x] Check the low-current limitation of a hypothetical unity-gain
  buffer directly on V_SENSE using the handout's approximation (DA1B
  p. 6; Q03/Q05). Student correctly recognized that a buffer with an
  assumed 0.1 V floor cannot reproduce 0.05 V. Phase: Research;
  conceptual example only, not device/model verification.
- [ ] Review the initial requirement extraction R001–R035 and resolve
  consequential interpretations through the required challenge gate.
  Phase: Research.
- [ ] Clarify nominal/worst-case endpoint and transfer-error acceptance
  criteria (Q01; R006, R011, R023).
  Phase: Research.
- [ ] Confirm the current course deadline and submission instructions,
  including the unstated year/cutoff (Q04; R033–R035).
  Phase: Research.
- [ ] Obtain the lab LM324N model and reconcile applicable device/output
  limits and loading with the supplied sources (Q03/Q05; R008, R009, R023).
  Phase: Research.
- [ ] Research relevant building blocks and primary references, including
  the source-recommended Application Note 105; record functionality,
  limitations, and integration relevance (Q06; R014).
  Phase: Research.

## Next

- [ ] Once evidence is sufficient, compare two candidate approaches using
  diagrams, stated assumptions, and requirement links (R016–R019).
  Phase: Plan.
- [ ] Define a verification plan with explicit criteria and conditions
  (R002–R013, R023–R024); use mie366-grill-me before major plan acceptance.
  Phase: Plan.

## Later

- [ ] Revisit the zero-input algebra and zero-voltage/open-circuit
  distinction when useful; deferred at the student's request and not
  yet confirmed understood. Phase: Research.
- [ ] Implement the student-accepted final design and collect simulation
  evidence for the stated conditions (R020–R024).
  Phase: Implement.
- [ ] Review results against requirements without treating a successful
  simulation run as proof of compliance (R002–R013, R023).
  Phase: Review.
- [ ] Prepare the report within the source-stated content/format rules;
  resolve page-count questions first, then use mie366-writing-reviewer
  (Q02; R014–R032).
  Phase: Review.

## Blocked

- Final numerical pass/fail thresholds depend on Q01 and applicable
  conditions in Q05; no acceptance band has been adopted.
- Model-dependent simulation validation awaits the lab model (Q03).
- Submission-date certainty awaits the current course posting (Q04).
