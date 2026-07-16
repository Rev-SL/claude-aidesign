# Collector's Corner — Ops Squad

The one-person-company operating system for Russel's multi-brand operation. One human in the
decision seat; Claude runs the execution layer as a Squad Lead routing to specialized agents.

## Structure

```
.
├── CLAUDE.md              # Squad Lead instructions + routing table (read first)
├── company.md             # Durable business memory: model, margins, suppliers, sites, cadence
├── .claude/
│   └── agents/            # The specialized subagents CLAUDE.md routes to
│       ├── sourcing-analyst.md    # landed cost, arbitrage, buy verdicts
│       ├── grading-desk.md        # PSA grade-vs-raw, batch ROI
│       ├── oripa-planner.md       # pack-rip / oripa run design
│       ├── ads-reviewer.md        # Meta Ads scale/pause/budget
│       ├── content-engine.md      # hooks, scripts, captions, repurposing
│       ├── dispute-handler.md     # chargebacks, scams, refunds
│       └── event-tracker.md       # card show P&L, consignor payouts
├── skills/                # Reusable skills (see SOURCES.md for vetted external packs)
└── SOURCES.md             # External skill repos, vetted for safety
```

## How it works

1. A task comes in. The Squad Lead (`CLAUDE.md`) reads `company.md` for context and routes to
   the right agent per the routing table.
2. Agents return options + one blunt recommendation, PHP / Asia-Manila, mobile-first, ending
   in owner-tagged Next Actions.
3. Standing constants (freight rates, FX, ROI formulas) live in `company.md` §8 so nothing is
   re-derived.

## Keeping it current

`company.md` is the single source of truth for business facts. Update it when a rate, supplier,
margin, or standing constant changes. The financial figures are dated — refresh from the Notion
sales database when re-running analysis.
