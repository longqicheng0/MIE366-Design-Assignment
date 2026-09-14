# DA1 Source Review

Reviewed: 2026-09-14
HVE phase: Research
Scope: initial intake of the supplied assignment sources, not circuit selection.

## Source inventory

All page references below are 1-based PDF pages. Printed handout page
numbers agree with PDF page numbers.

| Key | Local source | Extent and identity |
| --- | --- | --- |
| ROADMAP | [MIE366 - Design Assignment Roadmap v1.2.pdf](<../source-docs/MIE366 - Design Assignment Roadmap v1.2.pdf>) | 2 pages; course-stage overview with an explicitly tentative timeline. |
| DA1A | [MIE366 - Design Assignment 1A, Background Handout v1.1.pdf](<../source-docs/MIE366 - Design Assignment 1A, Background Handout v1.1.pdf>) | 5 pages; overall supply context and DA1 introduction. |
| DA1B | [MIE366 - Design Assignment 1B, Deliverable Handout v1.1.pdf](<../source-docs/MIE366 - Design Assignment 1B, Deliverable Handout v1.1.pdf>) | 10 pages; DA1 goals, constraints, report requirements, hints, and standard-value appendix. |
| DS | [LM324N - Main op-amp for your design.pdf](<../source-docs/LM324N - Main op-amp for your design.pdf>) | 39 pages; Texas Instruments SNOSC16D, March 2000 / revised January 2015 technical body; later packaging addendum includes 29-Jul-2023. |

Assignment handouts and roadmap were reviewed in full. Relevant datasheet
sections were reviewed for identity and design limitations; this is not
a full qualification of all 39 pages or a simulation-model validation.
Figures, equations, and critical tables were checked visually, including
the background block diagram, roadmap timeline, DA1 input/output
specification, nominal transfer graph, output-swing excerpt, and Appendix A.

The original PDFs were retained unchanged.

## Stage and schedule

[REQ] The supplied detailed handouts identify DA1 as “Design Proposal.”
The source-review scope is therefore DA1; previous student work or
completion outside this repository has not been assessed. DA1A/DA1B p. 1
state group size 2, weight 4%, online submission, and September 21,
end-of-day, Toronto time. They do not give a year or precise cutoff.

ROADMAP pp. 1–2 explicitly calls its timeline tentative:

| Stage | Source-described work | Source-stated timing |
| --- | --- | --- |
| DA1 — Design Proposal | Research, two candidates, final schematic and simulation evidence. | September 21. |
| DA2 — Prototype Design | Modified schematic and new filter; likely BOM, PCB CAD and production Gerbers. | October 4. |
| DA3 — Testing and Revision | Build/test and calibrate the PCB; revise design files if needed. | November 15; possible earlier refabrication deadline via Quercus. |
| DA4 — Design Verification and Final Report | Integrate with the provided motherboard, update schematic, final PCBA BOM; optional case. | Last day of classes. |

These are roadmap statements, not verified current calendar deadlines
or complete DA2–DA4 specifications. Confirm the current course posting
before scheduling against them (Q04).

## DA1 scope and nominal behavior

[REQ] DA1B p. 1 assigns the CURRENT SENSE block. DA1A pp. 4–5 places it
inside a larger adjustable power supply and describes later voltage
sensing and provided controller/interface work.

[REQ] DA1B pp. 2–3 requires low-side sensing through a 0.1 Ω resistor,
with its low side grounded, for returning current from 0 to 3.5 A.
The 3.5 A limit is intentional overshoot headroom above the overall
supply's 3 A output target. This difference is explicitly explained on
DA1B p. 3, so it is not an unresolved source conflict.

[REQ] DA1B pp. 3 and 7 gives a nominal linear-with-offset output:
0.25 V at 0 A and 3.3 V at 3.5 A. Its p. 7 examples express:

`V_SENSE = I_LOAD × 0.1 Ω`

`V_OUT = [(3.3 V − 0.25 V) / 0.35 V] × V_SENSE + 0.25 V`

The source's worked examples are approximately 0.337 V at 100 mA and
1.121 V at 1 A. These are source examples, not new calculated design
choices or four separately mandated simulation cases.

Use V_OUT for the sensing output in DA1 records; distinguish it from
the supply output that shares that label in the contextual diagram.

[REQ] The DA1 circuit may use up to three LM324N amplifier units,
powered from +19 V and 0 V, and resistors only. Non-sense resistors
must use standard 5% values within 1 kΩ–100 kΩ; series/parallel
combinations cannot evade that range. DA1B pp. 3, 8–10.

Appendix A's visually checked mantissas are:
1.0, 1.1, 1.2, 1.3, 1.5, 1.6, 1.8, 2.0, 2.2, 2.4, 2.7, 3.0,
3.3, 3.6, 3.9, 4.3, 4.7, 5.1, 5.6, 6.2, 6.8, 7.5, 8.2, 9.1.
Use only entries within the permitted range; the appendix also shows
values outside it. No component values have been selected here.

The draft traceability matrix is in [REQUIREMENTS.md](../REQUIREMENTS.md).
It retains source wording and leaves all design responses and
verification evidence unfilled.

## Overall-supply context, not additional DA1 acceptance criteria

DA1A p. 2 gives overall design targets: adjustable 0–15 V output,
adjustable 0–3 A current limit, no worse than 2% load/line regulation,
ideally no more than 250 mV noise under worst-case loading, isolated
output, safe construction/use, and a 19 V DC / 3.42 A input source.
DA1A p. 3 specifies an external prepackaged adapter rather than direct
AC-line work.

These belong to the overall supply scope. In particular, the ideal
noise target and later filter work have not been converted into new
numerical DA1 bandwidth, noise, or transient acceptance requirements.

## Hints and permissions kept separate from hard constraints

- DA1B p. 3 recommends a 0–3.5 A DC current sweep; it also permits a
  0–0.35 V voltage stimulus replacing the source/sense-resistor pair.
  Simulation stimulus sources are distinct from the allowed components
  of the designed circuit. Final-design simulation is required by p. 4.
- Fewer than three op-amps are encouraged to preserve capacity for the
  later filter, but using two is not mandated (p. 3).
- Candidates need not be fundamentally different or fully designed;
  block diagrams are allowed. Collaboration on both is recommended (p. 4).
- Inverting arrangements are cautioned against, not prohibited; the
  suggested toolkit does not select a topology for the student (pp. 6, 8).
- Low-current zoom, sensitivity checks, and attention to loading are
  recommended. Intermediate voltages may extend outside the final
  output interval while respecting device limits (p. 9).
- The endpoint guidance is asymmetric: upper-end deviations of a few
  tens of millivolts are acceptable, while the lower endpoint has less
  margin and an upward shift is favored. This does not establish a
  precise numerical acceptance band (p. 9; Q01).
- Two-resistor combinations are allowed. More than two is described as
  unnecessary, not as an absolute ban; p. 3 permits any number overall.
- [ASSUMPTION] Figure 1 on p. 1 uses a zero-current sense-branch
  simplification. This is a source modeling assumption, not a literal
  zero-input-current requirement for a real op-amp.

## Datasheet evidence requiring later design review

Use the LM324-N column in DS §6.6, pp. 6–7. The A-grade table in §6.5
is separate, and this PDF does not specify the newer LM324B family.
The p. 26 package addendum lists LM324N/NOPB as PDIP, package N,
14 pins, marking LM324N; the actual lab part/model is not yet confirmed.

All entries in this table are [DATASHEET], not new assignment requirements.

| Topic | Evidence and conditions | Source |
| --- | --- | --- |
| Supply | Recommended supply differential 3–32 V. Absolute maximum supply is also 32 V for LM324-N, but absolute ratings do not establish linear operation. | DS p. 4, §§6.1, 6.3. |
| Input common mode | At 25 °C the table gives 0 to V+−1.5 V; the full-temperature row gives 0 to V+−2 V, both with a 30 V test supply. Footnote (4) further discusses the upper-end relationship. Absolute input limits are not linear common-mode limits. | DS pp. 6–7, §6.6. |
| Input offset | 2 mV typical / 7 mV maximum at 25 °C; 9 mV maximum over the specified temperature range. Test footnote uses output about 1.4 V, source resistance 0 Ω, supply 5–30 V. | DS pp. 6–7, §6.6 and footnotes. |
| Input currents | Bias current 45 nA typical / 250 nA maximum at 25 °C and V_CM = 0 V; 500 nA maximum over temperature. Offset current 5 nA typical / 50 nA maximum at 25 °C; 150 nA maximum over temperature. Bias current flows out of the IC. | DS pp. 6–7, §6.6. |
| Output swing | At V+ = 30 V, V_OH minimum is 26 V with R_L = 2 kΩ, or 27 V minimum / 28 V typical with R_L = 10 kΩ. At V+ = 5 V and R_L = 10 kΩ, V_OL is 5 mV typical / 20 mV maximum. These are condition-dependent rows, not universal 19 V output bounds. | DS p. 7, §6.6. |
| Low-output sinking | At V+ = 15 V, V_O = 200 mV, 25 °C, V_IN− = 1 V and V_IN+ = 0 V: sink current is 12 µA minimum / 50 µA typical. A separate 2 V output row allows much more current. | DS p. 7, §6.6. |
| Temperature and dynamics | §6.6 footnote (1) limits LM324-N temperature specifications to 0–70 °C ambient. The 1 MHz bandwidth on p. 1 is a feature statement, not a guaranteed minimum in §6.6. Capacitive loading and layout/bypass guidance require later review. | DS pp. 1, 6, 11, 23. |

### Output-swing source discrepancy

DA1B p. 5 reproduces an excerpt with 22 V high-output and 100 mV
low-output figures and uses about 100 mV as an explanatory low-output
floor on pp. 5–6. Its low-output row is at 5 V supply / 10 kΩ load,
whereas the high-output rows use different supply/load conditions.

The supplied DS p. 7 lists 26 V / 20 mV for the corresponding LM324-N
rows. The handout's 22 V / 100 mV values coincide with the LM2902-N
column in that table. Preserve both sources and their conditions;
do not silently encode either value as a universal clamp for every
node at the assignment's +19 V supply. Confirm the applicable lab
part/model and expected treatment of the teaching approximation (Q03).

This discrepancy does not change the explicit nominal 0.25–3.3 V
assignment output target.

## Open questions and next evidence

No interpretation in this table has been accepted as a design decision.

| ID | Unresolved point | Relevant source / requirement | Next evidence or action |
| --- | --- | --- | --- |
| Q01 | Exact endpoint/linearity error allowance and whether compliance is required nominally or across resistor tolerances. “A few 10’s of mV” is not a precise threshold; no fixed 200–300 mV low-end band is granted. | DA1B p. 9; R006, R011, R023. | Obtain applicable instructor/TA clarification or a clearly identified proposed criterion; challenge and seek student acceptance before using it as a pass/fail rule. |
| Q02 | Literal <1 / <2 / <3 section allocations versus the ≤6-page body; treatment of the reference section is unstated. Only cover/appendices are explicitly excluded. | DA1B p. 4; R015, R019, R025–R026. | Preserve stated limits and clarify counting before report layout is accepted. |
| Q03 | Applicable LM324N device/model, output loading, and treatment of the handout/datasheet output-swing discrepancy. | DA1B pp. 3, 5–6; DS pp. 6–7; R008–R009, R023. | Obtain the lab-provided model and confirm its part/grade and relevant conditions; do not choose a universal output floor from the excerpt. |
| Q04 | Current course year, actual deadline/cutoff and submission URL; PDF does not state filename convention, partner submission arrangement, or native simulation-file upload. | DA1A/DA1B p. 1; DA1B p. 4; ROADMAP pp. 1–2; R033–R035. | Check the current course posting; do not infer current deadlines from the tentative roadmap alone. |
| Q05 | Required output loading, temperature, and dynamic verification conditions are not fully specified in the DA1 handout. | DA1B pp. 3–9; DS §6.6; R006, R023. | Keep assumptions explicit and identify conditions needed for a defensible plan; do not import overall-supply targets as new DA1 limits. |
| Q06 | Building-block research and candidate comparison have not been performed. | DA1B pp. 2, 4, 8; R014, R016–R024. | Review primary references and document their functionality, limits, and integration relevance before planning candidates. |

DA1B p. 2 points to Analog Devices / Linear Technology Application Note
105, “Current Sense Circuit Collection.” That external note has not been
reviewed in this intake. DA1A p. 5 also mentions an LMR33630 datasheet,
which is not among the four supplied PDFs; its relevance is mainly
overall-supply context. The lab LM324N simulation model is not present
in the repository.

## Research exit status

Initial source intake is complete. Research remains active: numerical
acceptance criteria, device/model evidence, applicable conditions, and
building-block evidence need work before a defensible candidate plan.
No topology, resistor network, verification result, or major engineering
interpretation has been accepted. No circuit simulations or physical
tests were run.
