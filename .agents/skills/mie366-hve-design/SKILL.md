---
name: mie366-hve-design
description: >-
  Guide MIE366 engineering work through Research, Plan, Implement,
  Review, and Follow-up. Use when asked to identify the current phase,
  plan engineering work, implement an approved plan, review verification
  evidence, or manage project progress. Coordinates phases and project
  records while leaving adaptive questioning and final writing review
  to their separate skills.
---

# MIE366 HVE Design

Orchestrate the adapted engineering lifecycle:

Research → Plan → Implement → Review → Follow-up

Support explicit invocation through `$mie366-hve-design` and requests
matching the description.

Apply this workflow to the student's requested scope. Do not restart
every task at Research or assume the entire project shares one phase.

## Read context and establish the phase

Resolve project paths relative to the repository root.

Read:

- AGENTS.md.
- STATUS.md.
- REQUIREMENTS.md.
- DECISIONS.md.
- TODO.md.
- Task-relevant assignment sources, research, calculations, schematics,
  simulation files, PCB work, and verification evidence.

Compare tracking statements with actual artifacts. Report stale or
contradictory records rather than silently trusting them. Update those
records only within the current authorization.

Determine the phase from the task and evidence. Do not infer the
assignment stage, completion, or verification from empty records.

Before engineering work, explain:

```text
Current phase:
[Research / Plan / Implement / Review / Follow-up, or Not yet assessed.]

Reason:
[Task scope and evidence supporting this assessment.]

Exit condition:
[Observable evidence or accepted decision needed to leave this phase.]
```

If the phase is not yet assessable, identify the missing context and
inspect available sources before asking the student for information.

Workspace configuration is separate from engineering HVE work. During
configuration, follow the numbered approval process in AGENTS.md and
do not begin solving the circuit.

## Phase and decision boundaries

Work within the current phase unless a transition is justified.

For a transition, explain the destination and either:

- The evidence satisfying the current phase's exit condition.
- The newly discovered gap requiring a return to an earlier phase.

Continue only within the student's authorized scope. A phase transition
does not authorize a significant new engineering decision.

Before accepting a significant choice:

- Make the options, recommendation, evidence, assumptions, and risks
  visible to the student.
- Use the challenge gate required by AGENTS.md.
- Ask for student acceptance before treating the choice as accepted
  or implementing it.
- Record the accepted decision and its basis.

Do not treat silence, a recommendation, or a passed challenge gate as
student acceptance. Do not request repeated acceptance for an unchanged
decision the student has already accepted.

## Research

Goals:

- Establish assignment requirements from official sources.
- Inspect relevant datasheets and instructor-provided resources.
- Gather credible external primary technical evidence when needed.
- Understand relevant existing circuit and design patterns.
- Identify unknowns, conflicting evidence, and provisional assumptions.
- Avoid premature circuit selection or implementation.

Use the source hierarchy, citations, and evidence labels in AGENTS.md.
External research supplements assignment sources; it does not establish
missing assignment requirements.

If sources are unavailable, report the limitation and keep unsupported
requirements and interpretations unassessed.

Possible outputs:

- Research notes.
- Source-backed requirement interpretations.
- Evidence tables.
- Open questions and unresolved assumptions.

Exit when enough evidence exists to make a defensible plan for the
current scope. Explicitly carry forward remaining uncertainty.

## Plan

Goals:

- Define candidate approaches and compare alternatives.
- Derive design equations and preliminary calculations where useful.
- Identify assumptions, risks, and selection criteria.
- Define verification methods and acceptance criteria linked to
  requirements.
- Record significant decisions and the proposed implementation scope.

Possible outputs:

- Candidate design descriptions and block diagrams.
- Calculations with stated inputs, units, and assumptions.
- Proposed decision records.
- An implementation and verification plan.

Before accepting a major plan or design choice, recommend and use
mie366-grill-me as required by AGENTS.md.

Read `.agents/skills/mie366-grill-me/SKILL.md` and hand off the focused
challenge. While that skill is questioning, respect its one-question
format and stop-and-wait behavior. Do not continue implementation or
add a second question around the handoff.

If the skill is unavailable, disclose that limitation and follow the
missing-gate rule in AGENTS.md. Merely naming or recommending the skill
does not complete the challenge.

After the challenge, obtain student acceptance of the significant
decision and record remaining risks and verification still needed.

Exit when the student has accepted the sufficiently supported plan and
its verification criteria.

## Implement

Goals:

- Follow the accepted plan within the authorized scope.
- Create the relevant calculations, schematics, simulation files,
  PCB work, or other engineering artifacts.
- Preserve inputs, units, assumptions, and design revision references.
- Document deviations from the plan.

Do not redesign casually during implementation.

If a new design or decision problem appears, return to Plan before
making the consequential change. If evidence is missing, return to
Research. Explain the issue and the work it affects.

Do not fabricate tool execution, generated artifacts, or results when
a required tool or input is unavailable.

Exit when the planned implementation and evidence needed for Review
are available.

## Review

Goals:

- Compare the implementation with REQUIREMENTS.md.
- Inspect calculations and their inputs, assumptions, and units.
- Inspect simulation and physical test evidence.
- Evaluate the established acceptance criteria.
- Identify failures, uncertainty, and verification gaps.

For each reviewed requirement or criterion, report:

- Requirement ID and acceptance criterion.
- Applicable evidence and design revision.
- PASS, FAIL, or INSUFFICIENT EVIDENCE.
- Limitations and any necessary follow-up.

Use:

- PASS when applicable evidence demonstrates the criterion is met.
- FAIL when applicable evidence demonstrates the criterion is not met.
- INSUFFICIENT EVIDENCE when the available evidence cannot establish
  either result.

Do not infer PASS merely because no obvious problem was found or a
simulation completed successfully.

Do not invent or relax acceptance criteria during Review. Route missing
or disputed criteria back to Research or Plan according to their cause.

A passing result applies only to the reviewed scope and conditions.
Mark a requirement Verified only when the verification rules in
AGENTS.md are satisfied.

Exit when the reviewed scope has explicit outcomes and unresolved issues
are identified for Follow-up.

## Follow-up

Classify each issue and route it by cause:

| Cause | Destination |
| --- | --- |
| Research or evidence gap | Research |
| Design or decision gap | Plan |
| Execution defect | Implement |
| Successful completed scope | Update records and identify the next task |

Link each issue to affected requirements, decisions, artifacts, or
evidence. Specify the next action and what will resolve the issue.

After a correction, return to Review for the affected criteria.
Preserve earlier results rather than replacing their history.

For successful work, move to the next task only within the student's
authorized scope.

## Maintain project records

After meaningful authorized work, update affected records:

- STATUS.md: present phase, objective, progress, blockers, next actions,
  and update date.
- REQUIREMENTS.md: source meaning, design response, verification method,
  applicable evidence, and justified status.
- DECISIONS.md: significant choices, options, evidence, assumptions,
  challenge findings, student acceptance, risks, and verification needed.
- TODO.md: actionable next steps linked to requirements or decisions
  and their HVE phases where applicable.

Keep STATUS.md concise and avoid duplicating detailed engineering notes.
Use stable IDs and links to preserve:

Requirement → Research/evidence → Decision → Calculation/design
→ Simulation or physical verification → Revision

Append superseding decision records rather than rewriting the original
rationale. Retain prior evidence when changes require reassessment.

During configuration, tracking maintenance must not bypass section
approval boundaries. Report needed updates without editing files
outside the approved section.

## Keep skill responsibilities distinct

This skill coordinates the engineering workflow.

Use mie366-grill-me for adaptive skeptical questioning. Leave final
technical-writing review to mie366-writing-reviewer when available;
read its SKILL.md before use and disclose if it is unavailable.

Do not claim either specialized review occurred unless it actually did.

Finish meaningful work by reporting the outcome, supporting evidence,
record changes, unresolved issues, and next action. Stop when student
acceptance or missing information is required before proceeding.
