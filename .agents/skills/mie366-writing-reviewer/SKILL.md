---
name: mie366-writing-reviewer
description: >-
  Review MIE366 technical deliverables for precision, concision,
  structure, notation, units, figure and table references, requirement
  coverage, and claim support. Use when asked to review or polish a
  report, assess technical writing, or perform a final writing review.
  Flags engineering errors and missing evidence without selecting
  circuit designs or orchestrating the engineering workflow.
---

# MIE366 Writing Reviewer

Review technical deliverables and recommend clear, precise engineering
writing while preserving technical meaning.

Support explicit invocation through `$mie366-writing-reviewer` and
requests matching the description.

## Establish review scope

Resolve project paths relative to the repository root.

Read the repository context required by AGENTS.md, then inspect:

- The deliverable or passage selected by the student.
- Relevant official assignment instructions and formatting constraints.
- REQUIREMENTS.md entries applicable to the deliverable.
- Relevant decision records and supporting calculations, datasheets,
  simulation results, physical test evidence, and cited research.
- Referenced figures, equations, tables, and appendices when available.

Resolve information from repository sources before asking the student.
If the review target is unclear, inspect the available context and ask
for the missing scope only when necessary.

State the reviewed document, sections, and material limitations.
Distinguish unavailable evidence from evidence that contradicts a claim.

If assignment sources or requirements are missing, report that coverage
or formatting compliance cannot yet be assessed. Do not invent rules
from general engineering conventions.

If figures, equations, layout, or other content cannot be inspected,
identify the limitation rather than claiming to have reviewed them.

## Classify findings

Classify each finding as one or more of:

- Writing problem: wording, organization, presentation, or consistency.
- Technical-content problem: an engineering statement is incorrect,
  contradictory, ambiguous in a consequential way, or inconsistent
  with the available evidence.
- Missing evidence: a claim lacks the support needed to assess it.

For each material finding, identify:

- Its location in the deliverable.
- The problem type and consequence.
- Supporting evidence or the specific evidence gap.
- A concrete suggested action.

Use the evidence labels and citation rules in AGENTS.md for supporting
technical claims. Finding categories do not replace evidence labels.

Prioritize issues affecting correctness, interpretation, evidence,
or assignment compliance before minor prose improvements.

## Review criteria

Check:

- Technical precision and appropriate strength of claims.
- Concise engineering language and unnecessary filler.
- Professional tone.
- Logical structure and progression of the argument.
- Alignment between requirements, design claims, and cited evidence.
- Unsupported generalizations or conclusions.
- Consistent definitions, symbols, subscripts, and notation.
- Consistent units, prefixes, dimensions, and numerical presentation.
- Figure and table numbering, captions, labels, and references.
- Equation numbering, variable definitions, and references.
- Agreement between the text and referenced figures, tables, or results.
- Assignment formatting constraints when established by sources.

Distinguish a requirement being discussed in the report from that
requirement being satisfied by the design.

## Preserve engineering meaning

Do not silently change:

- Numerical values or component specifications.
- Units, signs, inequalities, or mathematical relationships.
- Operating conditions or the scope of a conclusion.
- Qualifications, uncertainty, or assumptions.
- Whether evidence is derived, simulated, or physically measured.
- Whether work is proposed, implemented, or verified.

If a correction changes technical meaning, explicitly classify it as
a technical-content issue and explain its evidence and implications.

Do not hide incorrect or unsupported engineering behind smoother prose
or vague hedging. State what is wrong or missing and what must be
resolved before the claim can be supported.

Do not invent component values, calculations, test results, citations,
requirement IDs, figures, or acceptance criteria.

## Required output structure

Begin with a brief statement of review scope and limitations, then use
these headings:

```markdown
## Critical technical issues

[Consequential engineering errors, contradictions, or ambiguities.]

## Unsupported or weak claims

[Claims whose strength or scope exceeds the available evidence.]

## Clarity and concision

[Wording, filler, tone, definitions, and readability.]

## Structure / organization

[Logical progression, section placement, and missing connections.]

## Figures, equations, and tables

[References, captions, labels, notation, units, and consistency.]

## Requirement coverage

[Applicable requirement IDs, document locations, coverage gaps,
and limitations of the assessment.]

## Sentence-level suggestions

[Specific rewrites using Original / Suggested / Reason.]
```

When no issues are found in a category, say "None identified within
the reviewed scope." When a category could not be checked, say
"Not assessed" and explain why.

Do not invent findings to fill the structure. Avoid repeating a full
finding under multiple headings; cross-reference it when useful.

## Rewrite format

For every proposed rewrite, show:

```text
Original:
[Exact text from the deliverable, with its location.]

Suggested:
[Proposed replacement preserving supported technical meaning.]

Reason:
[Why the change helps, the problem type, and relevant evidence.]
```

Do not fabricate original text.

If a defensible replacement depends on unresolved engineering or
missing evidence, state "No supported rewrite yet" under Suggested
and identify what must be resolved under Reason.

Make any change in technical meaning explicit. Do not present a
substantive engineering correction as a purely stylistic edit.

## Scope and editing boundaries

A review provides findings and suggested edits. Apply edits only when
requested and authorized under AGENTS.md.

Do not select a circuit topology, choose component values, accept
engineering assumptions, or change the design while reviewing prose.

Identify necessary engineering follow-up without carrying it out or
taking over HVE orchestration.

Do not change requirement verification statuses, claim a challenge gate
passed, or declare the design ready for submission based on writing
quality alone.

During workspace configuration, obey the current section's approval
boundary and do not review or solve the circuit as a setup side effect.
