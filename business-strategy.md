# Collector's Corner Philippines — Business Strategy & North Star

> **Purpose:** Persistent strategic context. Load this **first** (with `company.md` for
> operating facts) before any Collector's Corner task. Every recommendation, build, and
> analysis is evaluated against the North Star below. Act as Lead Business Development &
> Strategist — blunt, options + one clear recommendation, no sycophancy.

---

## 1. North Star

**Be the #1 TCG store in the Philippines and Russel's most profitable business ever:
₱1,000,000/month NET profit.**

### The Math (sanity-check every plan against this)
| Blended Net Margin | Required Monthly Revenue |
|---|---|
| 15% | ₱6.67M |
| 20% | ₱5.0M |
| 25% | ₱4.0M |

- **Net** = after COGS, freight/landed cost, fees (payment processing, marketplace), ads,
  payroll, rent, dispute losses.
- **Do not conflate two different floors** (see `company.md` §4): the ~₱741K/mo *survival
  break-even* covers only the ₱200K staff+ads fixed cost at ~27% gross margin. The ₱1M NET
  North Star is a different, higher bar requiring **₱4–6M/mo revenue**.
- Prior assessment: the North Star is **not achievable through organic margins alone in 12
  months** — realistic horizon is 30–36 months organically, faster only if the leverage plays
  below compound. Community/content leadership IS achievable in 12 months and feeds everything.
- Any plan that doesn't move revenue toward ₱4–6M/month or expand blended margin is a
  distraction. Say so.

---

## 2. Who We Are

- **Owner:** Russel ("Rev"), Las Piñas, Metro Manila. Asia/Manila, PHP.
- **Core business:** Collector's Corner Philippines — Pokémon & One Piece TCG retail. Online
  at **collectorscorner.store**, physical presence at **Dibs Pack**.
- **Personal brand:** RevEarnsDaily — documents the multi-business journey; content flywheel
  for the store.
- **Other brands (DEPRIORITIZED — no strategic effort unless explicitly asked):** South Locker
  (sneakers), Nice Dae Studio (photo booth), Kura Cases (B2B accessories), vending beyond One Ayala.
- **Structure plan:** Regular Domestic Corporation (not OPC) for the multi-brand umbrella.

### Team
- **Jacob** — backend manager; acceptance-testing sign-off authority on dev work.
- **Melanie** — part-time sales. **Sheila** — part-time graphics. **CJ** — video editor.
- **Eugene** — marketer/decision maker. **Lawrence** — partner/co-owner on some inventory
  (50/50 co-deal precedent for syndicate structure).
- **Kyle** — outgoing developer; freelance replacement being hired (fixed-scope, 3 milestones,
  work-for-hire IP non-negotiable).

---

## 3. The Four Leverage Plays (ranked)

Everything built or planned should serve one of these.

1. **TikTok Live selling** — no clear PH competitor. Highest ceiling revenue channel. Needs
   tooling: live claim tracking → invoice → real-time inventory decrement, post-stream reconciliation.
2. **Card syndicate structure** — deploy outside capital (Lawrence 50/50 precedent) so growth
   isn't limited by Russel's own cash. Margin on other people's money.
3. **Oripa scaling** — mystery packs as a repeatable, calculated machine (oripa-calc governs
   profitability; grand-prize replenishment math is the constraint).
4. **Buyback/Kaitori board** — sourcing flywheel. Cheapest inventory acquisition channel;
   spec exists from the June 2026 architecture review.

---

## 4. Platform Roadmap (dev context)

- **Stack:** Angular 19, Node.js/Express, Sequelize, PostgreSQL, 5 repos. PWA-first (no native iOS).
- **Known debt:** 615-line monolithic order controller, 16 duplicated service files,
  **untested money paths** (highest risk).
- **Chosen path:** fix-and-refactor modular monolith (3–6 mo), not full rebuild.
- **Phase 0 critical gaps:** automated payments (PayMongo), unified inventory ledger, SEO/crawlability.
- **Milestones:** M1 = unified inventory ledger + delivery overhaul + PayMongo. M2 = buyback
  board + sales history + marketplace improvements. M3 = admin QoL, singles quick-add, slabs DB.
- **Fraud rule:** fake-claim disputes require continuous unedited unboxing video with tamper seal visible.

---

## 5. Operating Rules & Decision Principles

1. **Margin before volume.** Every SKU/batch runs through landed cost (Vikings freight basis)
   and, for raw cards, the PSA ROI formula: `R = P10 / ((Craw + Cgrade) ÷ G)`.
2. **Protect the money paths.** Payments, disputes, inventory accuracy are existential — test
   coverage and reconciliation before new features.
3. **Content compounds.** Every event, trade, and Oripa run is content material for
   RevEarnsDaily + Collector's Corner accounts. Ship the content.
4. **Fixed scope, business-observable acceptance criteria** on all outsourced work. IP is
   work-for-hire, always.
5. **Cash discipline.** Consignor payouts (JB, Gibbs) and multi-currency event cash reconcile
   per event — no floating balances.
6. **Focus is the strategy.** Core card-and-content path wins. New opportunities are judged
   against the four leverage plays; if they don't feed one, decline.

---

## 6. KPIs to Track Toward ₱1M/Month

- Monthly net profit (the only number that ultimately counts)
- Blended gross margin % by channel (store, TikTok Live, Oripa, events, marketplace)
- Oripa: profit per circulation, sell-through days, grand-prize replenishment cost
- Buyback: intake volume, spread captured on resale
- Meta Ads: ROAS by campaign (account `act_549260347455113` via Supermetrics)
- Dispute loss rate as % of revenue
- Inventory turns and dead stock aging

---

## 7. How the Squad Should Use This File

- Load at session start for any Collector's Corner work (alongside `company.md`).
- When asked "what should we build/do next," rank options by impact on the North Star math and
  the four leverage plays — then give ONE clear recommendation.
- Push back when a request drifts to deprioritized brands or doesn't serve a leverage play.
- Keep this file updated: when strategy shifts, edit this file — don't let it go stale.

*Last updated: 2026-07-17*
