# MIE366 Engineering Decision Records

No engineering decisions are recorded yet.

Workspace setup approval does not constitute acceptance of a circuit
design or engineering assumption.

## Record Rules

- Assign stable IDs: D001, D002, and so on.
- Record meaningful engineering choices and link related requirements.
- Keep proposed recommendations distinct from student-accepted decisions.
- Accepted status requires student acceptance recorded under Decision.
- Distinguish a passed challenge gate from student acceptance and
  requirement verification.
- Append records rather than rewriting decision history.
- For changed decisions, append a new record linking the earlier one
  and state whether it supersedes that decision.
- Preserve the original evidence, rationale, and known risks.

## Record Template

The following is a template only. Dxxx is not an actual decision.

```markdown
# Dxxx — Title

## Status

Proposed / Accepted / Superseded / Rejected

## Date

YYYY-MM-DD

## HVE Phase

Research / Plan / Implement / Review / Follow-up

## Question

What must be decided?
Related requirement IDs: <IDs, or explain why not applicable>

## Options Considered

<Candidate options and relevant tradeoffs>

## Evidence

<Source references and links using the AGENTS.md evidence labels>

## Assumptions

<Explicit assumptions, their consequences, and how to check them>

## Grill Me Findings

<Not yet challenged, or dated findings and remaining risks>
<Do not claim the challenge gate passed without a completed review>

## Decision

<Proposed recommendation or student-accepted choice>
<Student acceptance and date, when applicable>
<Related or superseded decision IDs, when applicable>

## Rationale

<Why the evidence and comparison support this choice>

## Consequences / Risks

<Expected consequences, limitations, and unresolved risks>

## Verification Needed

<Acceptance criteria, methods, required evidence, and related IDs>
```
