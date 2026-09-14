# MIE366 Engineering Workspace Instructions

## Project purpose

This repository tracks the MIE366 Design Assignment engineering process
across assignment stages. Engineering design is the primary activity;
software and automation support research, calculations, simulation,
documentation, and verification.

Preserve traceability across:

Requirement → Research/evidence → Design decision → Calculation/design
→ Simulation or physical verification → Revision

AI advises and analyzes. Significant engineering decisions remain visible
to the student and require student acceptance before implementation.

## Session orientation

Before meaningful work:

- Read AGENTS.md, STATUS.md, REQUIREMENTS.md, DECISIONS.md, and TODO.md.
- Inspect task-relevant assignment sources and engineering files.
- Determine the current assignment stage and HVE phase from evidence.
- Treat missing or empty records as unknown, not as completed work.
  Use "Not yet assessed" where appropriate.
- Explain the current objective, phase, and intended exit condition.
- Resolve questions from repository sources when possible before asking
  the student.

Repository files are the durable project record. Do not rely on chat
history as the sole record of requirements, decisions, or verification.

## Configuration setup approval rules

These section-by-section rules apply during the workspace configuration
setup. They take precedence over routine file-maintenance instructions
elsewhere in this document.

The setup sequence is:

2. AGENTS.md
3. STATUS.md, REQUIREMENTS.md, DECISIONS.md, and TODO.md
4. mie366-grill-me
5. mie366-hve-design
6. mie366-writing-reviewer
7. Usage documentation
8. Validation

For each section:

1. Inspect what currently exists.
2. Explain the proposed changes, exact affected paths, and usefulness.
3. Show the complete proposed contents or a sufficiently detailed diff.
   Show complete contents wherever the setup request requires them.
4. End the proposal with exactly these two lines, replacing [number]
   with the current section number:

APPROVAL REQUIRED — Section [number]
Reply APPROVE to implement this section, or tell me what to change.

5. Stop and wait. Approval applies only to that section.
6. Before approval, do not create, modify, delete, rename, move, or
   overwrite any file, including temporary proposal files.
7. After approval, implement only the approved section, inspect the
   resulting files, summarize actual changes, and show git diff --stat.
8. Then inspect and propose the next section; stop for its approval.
   Do not implement it automatically.

During setup:

- Do not solve the current-sense circuit or make circuit-design choices.
- Do not update tracking files as a side effect of another section.
- If existing content conflicts with the proposal, stop and show the
  conflict before editing.
- Do not install packages, extensions, MCP servers, plugins, or external
  software without separate explicit approval.
- Do not change .gitignore without a concrete reason and approval.
- Do not commit without an explicit request. Do not push to GitHub.
- Validation must not introduce new architecture. Report issues and
  propose any needed corrections before changing files.
- After final validation, propose an optional commit message and ask
  whether the student wants to commit; do not execute the commit.

These setup approvals do not authorize future engineering decisions.
After setup, perform work within the student's requested scope and
continue to obtain acceptance for significant engineering decisions.

## Adapted HVE lifecycle

Research → Plan → Implement → Review → Follow-up

Keep phases distinct. Explain a transition using the evidence that
satisfies the current phase's exit condition.

### Research

- Determine what is actually known from assignment sources and evidence.
- Gather relevant datasheets and credible primary technical sources.
- Identify unknowns, contradictions, and assumptions.
- Do not prematurely finalize a circuit.

Exit when enough evidence exists to make a defensible plan. Keep any
remaining uncertainty explicit.

### Plan

- Translate evidence into candidate approaches and compare alternatives.
- Develop equations or preliminary calculations where useful.
- Identify risks, unresolved assumptions, and decision criteria.
- Define acceptance criteria and verification methods linked to requirements.
- Challenge major choices with mie366-grill-me before student acceptance.
- Record the accepted plan and significant decisions.

Exit when the student has accepted a sufficiently supported plan and its
verification criteria. Do not silently substitute a different design.

### Implement

- Follow the accepted design plan.
- Perform the authorized calculations, simulation, schematic work,
  PCB work, or physical implementation.
- Preserve inputs, units, assumptions, and relevant design versions.
- Document deviations from the plan.
- If a deviation requires a significant design change, return to Plan
  before implementing that change.
- If necessary evidence is missing, return to Research.

Exit when the planned work and evidence needed for review are available.

### Review

- Compare the implementation and evidence against REQUIREMENTS.md.
- Check calculations, assumptions, units, simulation conditions, and
  physical test conditions.
- Evaluate explicit acceptance criteria.
- Report PASS, FAIL, or INSUFFICIENT EVIDENCE for the reviewed scope.
- Do not equate "simulation ran" with "requirement passed."
- Do not infer PASS merely because no obvious problem was found.

Exit when each reviewed criterion has an evidence-backed outcome or a
clearly identified evidence gap.

### Follow-up

Route each issue according to its cause:

- Evidence gap → Research.
- Decision or design gap → Plan.
- Execution mistake → Implement.
- Successful completed scope → update project records and identify
  the next task.

Record unresolved issues, affected requirements, and the next action.

## Sources and evidence

Prefer sources in approximately this order:

1. Official MIE366 assignment documents.
2. Instructor-provided component datasheets and resources.
3. Instructor/TA feedback.
4. Explicitly cited external primary technical sources.
5. Derived engineering calculations.
6. Simulation/test evidence.
7. Engineering assumptions.

This is a provenance and authority guide, not a universal ranking of
technical reliability. Simulation and testing verify behavior under
specific conditions; they do not replace assignment requirements.

Preserve source meaning. Attribute instructor/TA feedback explicitly.
If sources conflict or feedback creates ambiguity, show the conflict
and seek clarification before accepting a consequential interpretation.

Do not populate engineering facts from general knowledge when relevant
assignment sources are available. If sources are missing or unreadable,
report that limitation and keep requirements unassessed.

Make substantive technical claims identifiable using:

| Label | Meaning |
| --- | --- |
| [REQ] | Requirement supported by an authoritative assignment source or explicit official clarification. |
| [DATASHEET] | Component information supported by an identified datasheet. |
| [RESEARCH] | Finding supported by cited external technical research. |
| [DERIVED] | Result derived from stated equations, inputs, units, and assumptions. |
| [SIM] | Evidence from an identified simulation and its conditions. |
| [TEST] | Evidence from an identified physical test and its conditions. |
| [ASSUMPTION] | Unverified premise, estimate, or provisional interpretation. |

A label does not replace a citation or evidence link.

For source claims, include the filename or URL and page, section, table,
or figure where available. For derived results, show the derivation or
link to it. For simulation/test claims, identify the setup, inputs,
design revision, results, and applicable limitations.

Keep assumptions separate from requirements and measured results.
State how important assumptions will be checked.

## Requirement traceability and verification

For each requirement maintain:

Requirement → Design response → Evidence → Verification status

Use requirement and decision IDs to connect research, calculations,
design artifacts, verification, and revisions.

Mark a requirement Verified only when:

- Its source and meaning are established.
- Its acceptance criteria and verification method are explicit.
- Evidence applies to the relevant design revision and conditions.
- The evidence demonstrates that the acceptance criteria are met.
- The evidence location and any limitations are recorded.

Plausibility, student acceptance, a completed calculation, or a successful
simulation run alone is insufficient.

Use the tracking vocabulary consistently:

Unreviewed / Understood / Planned / Implemented / Verified / Failed /
Needs Review

Do not invent completion or verification status. If a design change,
new interpretation, or contradictory result undermines earlier
verification, preserve the previous evidence and mark affected
requirements Needs Review until reassessed.

## Skill responsibilities and challenge gates

Keep the three repo-local skills separate:

- mie366-grill-me: skeptical challenger. Uses adaptive questioning,
  exactly one question per questioning turn, then waits for the student.
  It does not silently modify design files.
- mie366-hve-design: workflow orchestrator. Determines the HVE phase,
  guides work and transitions, and helps maintain project records.
- mie366-writing-reviewer: technical-writing reviewer. Reviews precision,
  clarity, structure, notation, units, and claim support. It flags
  engineering errors or missing evidence without deciding the circuit
  design or silently changing technical meaning.

Before accepting a major engineering choice, use mie366-grill-me.

Challenge gates include:

- Choosing a circuit topology.
- Accepting a resistor network.
- Deciding a consequential requirement interpretation.
- Accepting an important assumption.
- Declaring a design ready for simulation.
- Declaring a design ready for submission.

Read the relevant skill's SKILL.md before using it. Do not assume a skill
exists merely because its directory exists. If it is unavailable, report
that limitation and hold acceptance of the major choice until the skill
can run or the student explicitly changes the gate requirement.

"Challenge gate passed" does not mean a requirement is Verified and does
not substitute for student acceptance. Record remaining risks and
required verification.

## Progress management

After meaningful authorized work:

- STATUS.md: keep the present phase, objective, assignment stage,
  progress, blockers, and next actions concise and current.
- TODO.md: maintain actionable tasks, preferably linked to requirement
  or decision IDs and an HVE phase.
- DECISIONS.md: append meaningful engineering decision records with
  options, evidence, assumptions, challenge findings, rationale, risks,
  student acceptance, and verification still needed.
- REQUIREMENTS.md: maintain source meaning, design response, evidence,
  verification method, and justified status.

Preserve decision history. Record later changes through explicit
superseding records rather than rewriting the original rationale.

Update only records affected by the work. Avoid duplicating detailed
engineering notes across tracking documents. During setup, these updates
remain subject to the current section's approval boundary.

## Preserve the workspace and student control

- Preserve the existing repository structure and useful content.
- Do not recreate or restructure the repository without explicit approval.
- Inspect relevant files and existing changes before editing.
- Do not overwrite unrelated student work.
- Make significant recommendations, tradeoffs, and uncertainties visible.
- Ask for student acceptance before making a significant new engineering
  decision; do not treat silence as acceptance.
- Distinguish proposed, accepted, implemented, and verified work.
- Report what actually changed, how it was checked, and what remains
  unresolved.
