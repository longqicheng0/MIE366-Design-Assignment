# MIE366 Design Assignment

Engineering workspace for the MIE366 Design Assignment: developing,
simulating, building, and verifying circuitry for an adjustable power
supply. This repository keeps assignment sources, research, design
decisions, calculations, simulation results, and deliverables connected
through a shared project record.

## Current focus: DA1 — Design Proposal

The current assignment concerns the supply's **current-sense block**.
Its main requirements are summarized below; the complete constraints and
report requirements are tracked in [REQUIREMENTS.md](REQUIREMENTS.md).

| Item | DA1 requirement [REQ] |
| --- | --- |
| Sensing arrangement | Low-side sensing through a 0.1 Ω resistor. |
| Input range | 0–3.5 A returning load current. |
| Nominal output | Linear with an offset: 0.25 V at 0 A to 3.3 V at 3.5 A. |
| Amplifiers | At most three amplifier units from one LM324N chip. |
| Supply | Single +19 V supply, with the negative rail at 0 V. |
| Other resistors | Standard 5% values from 1 kΩ to 100 kΩ; equivalent combinations must respect that range. |
| Circuit components | The permitted op-amps and resistors only. |
| Proposal | Background research, two candidates, and a fully designed final schematic supported by simulation results and discussion. |

Source: [DA1B Deliverable Handout v1.1](<source-docs/MIE366 - Design Assignment 1B, Deliverable Handout v1.1.pdf>),
pp. 3–4; nominal mapping and endpoint guidance on pp. 7 and 9.
The exact output-error allowance remains unresolved.

As of **2026-09-14**, the project is in **Research**. Four source PDFs have
been reviewed and 35 draft requirements recorded. No circuit design has
been accepted, and no simulation or physical verification evidence is
recorded. See [STATUS.md](STATUS.md) for the latest state and
[the source review](research/DA1_SOURCE_REVIEW.md) for open questions about
acceptance criteria, device/model evidence, report limits, and scheduling.

## Start here

1. Read [STATUS.md](STATUS.md) for the current objective and blockers.
2. Review [REQUIREMENTS.md](REQUIREMENTS.md) alongside the original
   handouts in [source-docs/](source-docs/).
3. Read [DA1_SOURCE_REVIEW.md](research/DA1_SOURCE_REVIEW.md) for source
   findings, datasheet cautions, and unresolved interpretations.
4. Use [TODO.md](TODO.md) to choose the next task and
   [DECISIONS.md](DECISIONS.md) to record significant accepted choices.

The repository currently contains documentation and source material.
There is no executable project or automated build to run. DA1 permits
LTspice or another simulator; the lab LM324N model still needs to be
obtained and checked before model-dependent verification.

## Repository layout

| Path | Purpose |
| --- | --- |
| [source-docs/](source-docs/) | Original assignment roadmap, DA1 handouts, and supplied LM324N datasheet. |
| [research/](research/) | Source reviews, technical research, and unresolved questions. |
| [STATUS.md](STATUS.md) | Current phase, objective, progress, and blockers. |
| [REQUIREMENTS.md](REQUIREMENTS.md) | Requirement IDs, sources, design responses, verification methods, and evidence. |
| [DECISIONS.md](DECISIONS.md) | Engineering decision history, rationale, student acceptance, and remaining verification. |
| [TODO.md](TODO.md) | Actions grouped by priority and engineering phase. |
| [docs/AI_WORKFLOW.md](docs/AI_WORKFLOW.md) | Detailed guide and example prompts for the AI-assisted workflow. |
| [AGENTS.md](AGENTS.md) | Repository instructions, evidence standards, and student decision authority. |
| [.agents/skills/](.agents/skills/) | Project-specific workflow, questioning, and writing-review skills. |

The local workspace also reserves `design/calculations/`,
`design/schematics/`, `design/ltspice/`, `verification/figures/`, and
`deliverables/` for later work. These directories are currently empty;
Git does not retain empty directories, so they may be absent in a fresh
clone. Create them as needed when adding the corresponding files.

## Engineering workflow

**Research → Plan → Implement → Review → Follow-up**

Establish requirements and evidence, compare candidate approaches, then
implement the student-accepted plan. Review results against explicit
acceptance criteria and return unresolved issues to the appropriate phase.

Keep each requirement connected to its design response and verification
evidence. Cite source pages, state assumptions, and retain the conditions
and design revision associated with each result. A successful simulation
run alone does not make a requirement **Verified**.

The project provides three separate AI skills:

| Skill | Role |
| --- | --- |
| [mie366-hve-design](.agents/skills/mie366-hve-design/SKILL.md) | Guide the engineering phases and maintain project records. |
| [mie366-grill-me](.agents/skills/mie366-grill-me/SKILL.md) | Challenge consequential assumptions and design choices, one question at a time. |
| [mie366-writing-reviewer](.agents/skills/mie366-writing-reviewer/SKILL.md) | Review technical writing, requirement coverage, and support for claims. |

Major engineering choices require a challenge review and explicit student
acceptance before implementation. See [the workflow guide](docs/AI_WORKFLOW.md)
for usage examples and [AGENTS.md](AGENTS.md) for the full working rules.

## License

See [LICENSE](LICENSE) for the repository's MIT license text.
