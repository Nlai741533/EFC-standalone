# EFC Standalone — Fact-Check Skill for AI Agents

**One file. Zero dependencies. Any AI agent.**

Drop `SKILL.md` into your agent's skill directory and it gains a rigorous fact-checking protocol — catching hallucinated numbers, fabricated data points, and exaggerated claims in AI-generated research reports.

## What it does

EFC (Everything Fact-Checked) gives your agent a structured 6-step workflow to audit reports:

1. **Inventory** every specific, checkable claim
2. **Triage** by risk (P0 critical → P3 cosmetic)
3. **Verify** P0/P1 claims against primary sources
4. **Cross-check** charts and tables for consistency
5. **Audit** source links and attribution chains
6. **Report** with verdicts, evidence, and a reliability rating

It's trained to catch the **five systematic failure modes** that LLMs produce at scale:

| Failure Mode | Example |
|---|---|
| Unit/scale errors | $5.3B → $530M (dropped conversion) |
| Fabricated interpolation | 6-point chart where only 2 were sourced |
| Source conflation | GMV reported as revenue |
| Stale data as current | 2023 figures presented as 2025 |
| Attribution laundering | Blog cited as regulatory filing |

## Requirements

- **Best results:** Agent with **web browsing** capability, so it can open cited URLs and verify claims against source content.
- **Minimum:** Agent that can read the document. Without browsing, the skill degrades to an internal consistency review (cross-checking figures within the document, verifying table totals, flagging unsupported claims). All external claims are marked "unverifiable."
- **No code, no install, no API keys.** This is a protocol, not a script.

## Install

The skill name is `fact-check`. Install it under a folder with the same name:

### Pi Agent

```bash
mkdir -p ~/.pi/agent/skills/fact-check
cp SKILL.md ~/.pi/agent/skills/fact-check/SKILL.md
```

### Claude Code

```bash
mkdir -p .claude/skills/fact-check
cp SKILL.md .claude/skills/fact-check/SKILL.md
```

### OpenClaw / Hermes / Other agents

Place `SKILL.md` in `<agent-skill-dir>/fact-check/SKILL.md`. The file is self-contained — no scripts, no schemas, no dependencies.

> **For agents that don't support skill files:** copy the entire content of `SKILL.md` into your system prompt or custom instructions.

## Example

See [`examples/sample-report.md`](examples/sample-report.md) — a deliberately flawed fictional report with one of each failure mode — and [`examples/expected-fact-check.md`](examples/expected-fact-check.md) for the target output.

## Why a standalone version?

The full [EFC-Plugin](https://github.com/Nlai741533/EFC-Plugin) repo includes Python scripts, JSON schemas, a CLI (`efc`), a GitHub Action, and a Claude Code plugin. That's great for CI pipelines and automated workflows.

But most AI agents just need the **protocol** — the structured thinking about what to check and how. That's what this is: one Markdown file that teaches any agent to be a rigorous fact-checker.

| | [EFC-Plugin](https://github.com/Nlai741533/EFC-Plugin) | EFC-Standalone |
|---|---|---|
| Files | 25+ | 1 (SKILL.md) |
| Dependencies | Python 3.11+ | None |
| CLI | `efc` command | No |
| CI integration | GitHub Action | No |
| Schema enforcement | JSON Schema + validator | No |
| Core protocol | ✅ | ✅ |
| Agent compatibility | Claude Code | Any |

## License

[MIT](LICENSE) — use it, fork it, ship it.

## Related

- **Full plugin + CLI:** [EFC-Plugin](https://github.com/Nlai741533/EFC-Plugin) — CLI, schemas, CI, GitHub Action
- **Feedback / Issues:** Open an issue on either repo
