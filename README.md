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

## Install

### Pi Agent

```bash
mkdir -p ~/.pi/agent/skills/efc-standalone
cp SKILL.md ~/.pi/agent/skills/efc-standalone/SKILL.md
```

### Claude Code

Copy `SKILL.md` into your project's `.claude/skills/` directory or any skill folder your agent scans.

### OpenClaw / Hermes / Others

Place `SKILL.md` wherever your agent loads skill definitions from. The file is self-contained — no scripts, no schemas, no dependencies.

## Why a standalone version?

The full [everything-fact-checked](https://github.com/Nlai741533/everything-fact-checked) repo includes Python scripts, JSON schemas, a CLI (`efc`), a GitHub Action, and a Claude Code plugin. That's great for CI pipelines and automated workflows.

But most AI agents just need the **protocol** — the structured thinking about what to check and how. That's what this is: one Markdown file that teaches any agent to be a rigorous fact-checker.

## Difference from the full repo

| | Full repo | Standalone |
|---|---|---|
| Files | 20+ | 1 |
| Dependencies | Python 3.11+ | None |
| CLI | `efc` command | No |
| CI integration | GitHub Action | No |
| Schema enforcement | JSON Schema + validator | No |
| Core protocol | ✅ | ✅ |
| Agent compatibility | Claude Code | Any |

## License

[MIT](LICENSE) — use it, fork it, ship it.

## Related

- **Full repo:** [everything-fact-checked](https://github.com/Nlai741533/everything-fact-checked) — CLI, schemas, CI, plugin
- **Feedback / Issues:** Open an issue on either repo
