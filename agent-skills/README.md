# Agent skills — canonical home

Reusable skills and pinned agents for AI-assisted development across my
projects. The novel `polymerase-review` strand model is mine; the rest is
synthesized from this ecosystem survey (addyosmani/agent-skills,
rockscy/shipcrew, AfterRealm/blunt-cake, obra/superpowers, and others) plus
battle-tested practice in [Anastomosis](https://github.com/AzalDaniel/Anastomosis).

**This repo is the canonical copy.** Projects carry working copies under
their own `.claude/skills/` and `.claude/agents/`; when the two drift, this
copy wins and projects re-sync from here.

## Install

- Globally (all projects on a machine): copy `skills/*` into
  `~/.claude/skills/` and `agents/*` into `~/.claude/agents/`.
- Per project: copy into the repo's `.claude/skills/` and `.claude/agents/`.

## Contents

| Path | What it is |
| --- | --- |
| `skills/model-hierarchy/` | Time-indifferent model routing: Orchestrator/Builder/Scout/Grunt roles — the newest frontier model orchestrates and does all main thinking; cheaper tiers research, build, and grind. Re-derive the name mapping whenever model lineups change. |
| `skills/polymerase-review/` | Two-strand code review modeled on DNA replication: leading strand reviews the new change forward (intent → code, dedup against existing "enzymes"), lagging strand walks backward from the existing codebase in Okazaki fragments verifying retro-compatibility, with proofreading, mismatch repair, and a ligase gate. Taxonomy: MISMATCH / BULGE / NICK / SILENT. |
| `skills/quality-gate/` | Mandatory pre-commit pipeline: scope triage (tests-first), exact mechanical gate, two-stage adversarial review (compliance halts first), evidence + confidence rules, no-approval-authority reviewers, severity taxonomy, repair + fresh-instance re-review. |
| `agents/` | Role-pinned subagent definitions (researcher=scout tier, implementer=builder, qa-reviewer=builder-adversarial, grunt=cheapest). These are flavored for Anastomosis (its gate command, its PHI rules) — adapt the invariants block per repo. |

## Notes

- `quality-gate` references `bash tools/check.sh` — substitute your repo's
  single all-gates command (the rule that matters: pipefail, never masked
  through `tail`).
- Skills follow the standard format: `SKILL.md` with YAML frontmatter
  (`name`, third-person `description` containing the trigger conditions),
  body under 500 lines, progressive disclosure via sibling files if needed.
