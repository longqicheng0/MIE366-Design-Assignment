# Using the MIE366 AI Engineering Workspace

Use this guide for engineering sessions after setup. During configuration,
the section-by-section approval rules in AGENTS.md remain in force.

## What each part does

| Part | Purpose |
| --- | --- |
| AGENTS.md | Persistent repository instructions: engineering workflow, evidence standards, student control, and working boundaries. |
| Skill | A reusable procedure for a particular kind of task, stored in a folder containing SKILL.md. |
| Prompt | Your instruction for the current task, including its scope, files, and constraints. |
| Repository files | The durable record of requirements, research, decisions, calculations, designs, verification, and progress. |

Codex reads AGENTS.md as repository guidance. You do not need to paste
its contents into every Codex prompt. See the
[official AGENTS.md guide](https://learn.chatgpt.com/docs/agent-configuration/agents-md).

## Choose the right skill

| Skill | Role | Expected behavior |
| --- | --- | --- |
| `$mie366-hve-design` | Workflow orchestrator | Explains the current phase, supporting evidence, and exit condition; guides work and maintains authorized project records. |
| `$mie366-grill-me` | Skeptical challenger | Challenges the highest-impact unresolved issue, asks one question per questioning turn, gives a recommendation and evidence status, then waits. |
| `$mie366-writing-reviewer` | Technical-writing reviewer | Flags writing problems, technical-content problems, and missing evidence; proposes rewrites without silently changing engineering meaning. |

Their sources are:

- [HVE Design](../.agents/skills/mie366-hve-design/SKILL.md)
- [Grill Me](../.agents/skills/mie366-grill-me/SKILL.md)
- [Writing Reviewer](../.agents/skills/mie366-writing-reviewer/SKILL.md)

A completed challenge does not mean you accepted the decision or that
a technical requirement is Verified. A writing review does not verify
the circuit.

## Find and invoke skills in Codex

Open this repository as the working project.

Codex discovers repo-local skills under `.agents/skills/`. In Codex CLI
or the IDE extension, use `/skills` to browse, or type `$` to select a
skill. In the ChatGPT desktop app, use the Skills sidebar to inspect
available skills. Matching natural-language requests can also select
skills implicitly. See [Build skills](https://learn.chatgpt.com/docs/build-skills).

The examples below use Codex's `$skill-name` syntax. Enter them in the
message composer, not as shell commands.

If a skill is missing, check its directory and SKILL.md. Codex detects
skill changes automatically; restart Codex if an update does not appear.

You can also ask:

> List the available MIE366 skills and their source paths. Do not edit files.

## Daily workflow

```text
Open the repository
        ↓
Read STATUS.md and check current artifacts
        ↓
Invoke $mie366-hve-design
        ↓
Research / Plan as appropriate
        ↓
Use $mie366-grill-me before a major decision
        ↓
Resolve concerns and explicitly accept the decision
        ↓
Implement the accepted plan
        ↓
Review against requirements and acceptance criteria
        ↓
Follow up on gaps or failures
        ↓
Update the affected tracking files
```

Follow-up returns evidence gaps to Research, design or decision gaps to
Plan, and execution mistakes to Implement.

Before finalizing a deliverable, use `$mie366-writing-reviewer`.

At the start of engineering work, make the official assignment sources
available in `source-docs/`. Leave the assignment stage and requirements
unassessed until supported by those sources.

## Example prompts

Replace bracketed placeholders with actual files or a specific scope.

Start a session:

```text
$mie366-hve-design
Read the project records and relevant artifacts. Explain the current
phase, reason, and exit condition, then identify the next task.
```

Research assignment requirements:

```text
$mie366-hve-design
Review source-docs/[assignment filename]. Propose source-backed
requirements with page references and identify ambiguous interpretations.
```

Challenge a candidate:

```text
$mie366-grill-me
Challenge the candidate described in [design file] before I accept it.
Use the related requirements and evidence, and ask one question at a time.
```

Review a deliverable:

```text
$mie366-writing-reviewer
Review deliverables/[report filename]. Flag unsupported claims and
technical inconsistencies. Show Original, Suggested, and Reason for
rewrites, preserving technical meaning.
```

Close an engineering session:

```text
Update the affected tracking files for the authorized work completed
today. Preserve unresolved assumptions and verification gaps. Show the
changes without committing.
```

During setup, this last prompt does not bypass section approvals.

## Keep the project record current

- [STATUS.md](../STATUS.md): present state, phase, objective, and blockers.
- [REQUIREMENTS.md](../REQUIREMENTS.md): source-backed requirements,
  design responses, verification methods, evidence, and status.
- [DECISIONS.md](../DECISIONS.md): decision history, student acceptance,
  rationale, risks, and verification still needed.
- [TODO.md](../TODO.md): actionable work and dependencies.

Link records to actual research, design, calculation, and verification
files. Preserve previous decisions and evidence when revising the design.

Repository files are the durable source of truth. Useful conclusions
from chat should be recorded through authorized updates; chat history
alone is insufficient for project traceability.

## Use the same skills in ChatGPT

ChatGPT skill installation and availability are separate from Codex's
repo-local discovery. A file in `.agents/skills/` does not by itself
install that skill into every ChatGPT conversation.

In ChatGPT, use `@` to select an available skill. Official documentation
describes standalone skills in the desktop app and plugin packaging
for broader distribution across ChatGPT clients.
See [Build skills](https://learn.chatgpt.com/docs/build-skills).

Keep these SKILL.md files as the version-controlled sources. The same
sources can be packaged separately for ChatGPT without combining the
three responsibilities. Packaging and installation are separate tasks.

A skill contains instructions; it does not automatically supply access
to this repository. Make the current AGENTS.md, tracking records, and
task-relevant sources available in the ChatGPT session through its
supported file or project access.

Confirm which files ChatGPT can actually read. If a referenced file is
unavailable, keep that limitation explicit.

ChatGPT suggestions do not automatically update local repository files,
and separately packaged skills do not automatically synchronize with
later edits here. Bring accepted changes back into the repository and
review them before applying.

Product usage references checked: 2026-09-14.
