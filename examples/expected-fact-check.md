# Expected Fact-Check Output for `sample-report.md`

This is the kind of result the fact-check skill should produce on the fictional
sample report. It demonstrates each of the five failure modes.

## Fact-Check Report: Acme Robotics Market Brief (FICTIONAL)
**Date:** 2026-05-30  |  **Coverage:** All P0/P1 claims, revenue table, source list

### ❌ Errors Found

| Claim | Reported | Actual | Failure Mode | Source | Impact |
|---|---|---|---|---|---|
| FY2024 revenue | $4,200B | $4.2B (per table) | **Unit/scale error** — 1000× inflation | Internal inconsistency | High |
| App "generated $1.2B in revenue" | revenue | Source describes marketplace GMV | **Source conflation** (GMV ≠ revenue) | N/A | High |

### ⚠️ Unverifiable

| Claim | Reason | Recommendation |
|---|---|---|
| "First consumer robotics company to ship 1M units in a quarter" | Superlative with no independent source | Verify exhaustively or hedge to "among the first" |
| 2019–2023 revenue series | Only FY2024 appears in any cited source; earlier years may be interpolated | **Fabricated interpolation** — cite per-year sources or flag |
| Dubai Airport duty-free entry | Specific named location, no resolving source | Search brand + "Dubai Airport"; if nothing found, remove |
| Store openings "in 2024" | No dated source; could be planned, not completed | Verify verb tense and date against a primary source |

### Broken Links

| URL | Status |
|---|---|
| https://example.invalid/acme/units-q4 | Unreachable (host does not resolve) |
| https://httpstat.us/404 | 404 Not Found |

### Summary
- 0 claims verified against primary sources (sample has no real sources)
- 2 errors found (2 high impact)
- 4 claims unverifiable, 2 source links broken
- Overall reliability: **Low** — do not publish without correction
