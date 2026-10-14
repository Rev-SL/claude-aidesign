# Collector's Corner: Roadmap to ₱50,000 Daily Gross

_Prepared 14 Oct 2026 (Asia/Manila). Based on the Notion orders database (630 rows, May–Sep 2026). Collector's Corner does not sell through Shopify. Sales come in through FB/IG DMs, Lives, Shopee, meetups, walk-ins and card shows._

---

## 1. Where you actually are (from your own data)

| Signal | What the data shows | What it means |
|---|---|---|
| Order logging | Last Notion order was **24 Sep**. Nothing logged for the past 3 weeks. | Orders are being missed or logged late. |
| Order status | **144 of 630 orders (23%) have no status.** | Nobody can tell what has shipped. |
| "Total Paid" field | Free text. A ₱1,185 item is logged as **₱1,185,000**, and there's a ₱2,600,000 cash meetup row. | Revenue totals are unusable, so the true daily gross isn't known yet. |
| Payment methods | 18 different options (GCash, Gotyme, BPI, BDO, Maya, Cash, CO Link, PayMongo…). | Money lands in too many places to check against orders. |
| Sales pattern | Jul: 265 orders (185 preorders). Aug: 43. Sep: 103 (59 preorders). | Sales come from drops, not a steady daily flow. |
| Preorders | **103 orders sit "on hold pre-orders"**. | That's a large CS and cash liability to track. |

**The diagnosis:** sales aren't the first problem. You can't count your sales, so you can't scale them. Getting to ₱50K a day needs one place every peso and every card goes through, and a steady daily selling rhythm in place of drop spikes.

---

## 2. The ₱50K/day math

₱50,000/day = **₱1.5M/month**. At a ~₱2,500 average basket that's **about 20 orders a day**. (Confirm the real average basket once Phase 0 data is clean.)

| Channel | Target / day | How |
|---|---|---|
| FB Live / TikTok Live selling | ₱22,000 | 4 scheduled Lives a week, about ₱38K per Live |
| FB page, groups and DMs (posted stock, price lists, preorders) | ₱12,000 | Daily "New in" posts, fast DM replies, preorder windows |
| Shopee + TikTok Shop | ₱8,000 | Sealed products and low-ticket singles |
| Oripa / Dibs packs | ₱4,000 | Weekly runs (use `oripa-planner` for odds and filler cost) |
| Events, consignment, B2B | ₱4,000 | Card shows averaged across the month, plus Kura Cases cross-sell |
| **Total** | **₱50,000** | |

No single channel has to carry it. The plan fails if you depend on one big drop a month.

---

## 3. The core fix: one front door for every sale (Google Sheets)

**Recommendation: every sale is logged once, the moment it's paid, through one Google Form that feeds one Google Sheet.** That covers DM, Live, Shopee, meetup, event and preorder sales.

- **Sale closed in a DM or Live** → CS opens the "Log a Sale" form on their phone and fills it in before replying "confirmed" to the buyer. It takes about 30 seconds.
- **At events or walk-ins** → the same form, or an **AppSheet app** built on the same Sheet. It can scan barcodes on sealed products and PSA slabs with the phone camera. AppSheet is free to build, and Workspace plan pricing decides how many people can use it.
- **Shopee / TikTok Shop** → export orders weekly and paste them into the ORDERS tab. Don't retype them.
- **The form forces clean data:** amount is a number field, and status, payment account, channel and location are dropdowns. The ₱1,185,000 typo can't happen.
- **Cut payment accounts to 3:** GCash, one bank (BDO or BPI), and cash. That way Jacob can check each day's inflows against the Sheet in 10 minutes. (High-value sales above ₱30K go to bank transfer or GCash, not PayPal.)

Then split the tools by job:

| Tool | Job | Who updates it |
|---|---|---|
| **Google Sheets** ("CC Ops Ledger") | Source of truth: orders, inventory, expenses, purchases, preorders, dashboard | Fed by Google Forms or AppSheet. Nobody types directly into the tabs. |
| **Notion** | Work: tasks, SOPs, content calendar, event calendar, trend board, customer wishlist | Everyone |

The Notion orders database becomes **read-only history** once the Sheet takes over. Two places logging orders means neither one is right.

### Google Sheets layout ("CC Ops Ledger")

1. **DASHBOARD**: today's gross vs ₱50K, 7-day average, orders, average basket, open preorders, cash per account, unshipped orders.
2. **ORDERS** (Form: "Log a Sale"): date and time, channel, customer, items, qty, amount, payment account, status, delivery method, tracking number, handler.
3. **INVENTORY**: one row per SKU per location (Pilar, Sven, Greenhills, Festival). Stock in comes from PURCHASES, stock out comes from ORDERS, giving live quantity on hand, cost basis, margin and **aging** (stock older than 60 days gets flagged).
4. **PURCHASES** (Form): date, supplier, items, qty, USD/JPY cost, Vikings weight, **landed cost per unit** (auto-calculated).
5. **EXPENSES** (Form): date, category (ads, shipping, supplies, salaries, rent, event fees), amount, paid via, receipt photo.
6. **PREORDERS**: deposits collected vs supplier payments due vs ETA, per release.

**Rules that keep it clean:**
- Each sale is logged once, through the form only.
- Every dropdown is fixed.
- An **"Unlogged" check** each night has Jacob compare that day's GCash/bank/cash totals against the ORDERS tab. Any gap gets fixed before bed. The target is 0.

---

## 4. Your 8 "always urgent" items, each with an owner and a system

| Need | System | Owner | Standard |
|---|---|---|---|
| Always answer customers | Meta Business Suite inbox with saved replies, plus an auto-reply FAQ (prices, payment, shipping, preorder ETA) | Jacob (day), Melanie (evening and Lives) | First reply in **under 15 minutes** during 9AM–11PM |
| Track orders | ORDERS tab, with a status dropdown and tracking number. A filtered "Unshipped" view on the dashboard. | Jacob | No order without a status after 24h |
| Track expenses | Google Form → EXPENSES tab | Whoever spends | Logged the same day, with a receipt photo |
| Track purchases | Google Form → PURCHASES tab (landed cost auto-calculated) | Russel | Logged before stock is listed |
| Log all 3 | DASHBOARD pulls them together | Jacob reviews nightly | 0 unlogged inflows |
| Seamless | One form per action, phone-friendly; no double entry into Notion | Russel sets up, Jacob runs it | Each sale typed once |
| Update inventory | INVENTORY tab updates from sales and purchases, with an AppSheet barcode scan for sealed products and slabs | Jacob | Friday stock count; under 2% variance |
| Check trends | Monday 30-minute Trend Review in Notion: JP release calendar, Card Ladder/PriceCharting movers, Shopee bestsellers, customer wishlist log | Russel + Eugene | Every buy decision ties to a trend note or deposits |

**Preorder rule:** only commit supplier money when deposits cover at least 50% of the order. This keeps the 103 on-hold preorders from becoming a cash trap.

---

## 5. Roadmap

### Phase 0: Foundation (Weeks 1–3, now to early Nov)
**Goal: know the real daily gross.**
- Build the CC Ops Ledger Sheet (6 tabs) and 3 Google Forms (Log a Sale, Purchase, Expense).
- Move order history: export the Notion orders database to CSV, fix the Total Paid typos, and import it into ORDERS.
- Back-log every order from 24 Sep to today. Fill the 144 blank statuses.
- Do a full stock count per location and load it into INVENTORY.
- Cut payment accounts down to 3.
- Write 3 SOPs in Notion: "How to log a sale", "How to ship", "How to answer DMs". (Use `sop-writer`.)
- **Exit check:** 7 straight days with 0 unlogged sales, and a trustworthy daily gross number.

### Phase 1: Daily selling engine (Weeks 4–8, Nov to mid-Dec)
**Goal: ₱20–25K/day average, with no reliance on one big drop.**
- **Lives:** fixed schedule, e.g. Tue/Thu/Sat/Sun 8PM. Melanie runs CS and logs Live sales on the form in real time. CJ clips highlights the next day.
- **Daily FB posting:** a "New in" post every day and a weekly price list. Sheila builds reusable templates so posting takes minutes.
- **Content:** CJ makes 1 short a day from Lives, pulls and unboxings.
- **Ads:** Facebook placements only (avoid IG), with Messenger as the destination so ads land in the DM inbox. Retarget Live viewers and page engagers. Run `ads-reviewer` weekly.
- **Marketplaces:** list sealed products on Shopee and TikTok Shop. Update stock from the INVENTORY tab twice a week.
- **AppSheet:** add barcode scanning for stock in and out once the Sheet is stable.
- **Christmas push:** gift bundles, starter decks, ₱999/₱1,999/₱4,999 mystery boxes and an oripa run.

### Phase 2: Scale (Months 3–6, Jan to Apr 2027)
**Goal: ₱35K/day by month 4, ₱50K/day by month 6.**
- **Eugene starts:** owns ads, content calendar and the Monday trend review output. KPI: blended ROAS and new customers per week.
- **Hire one packer/CS** when orders average 20 a day for 2 weeks, so Jacob moves from doing CS to managing it.
- **Repeat buyers:** keep a customer list in the Sheet (built from ORDERS). Use it for a VIP tier (early preorder access, Live-only slots), plus a monthly pack subscription for predictable revenue.
- **Sourcing:** Japan/Asia buying trips (Asia Tour) driven by the trend board, not gut feel. Run `sourcing-analyst`, then `grading-desk`, on big buys.
- **Revisit a webstore only when** the Sheet runs clean and DM volume is more than CS can handle. A store is a channel, not the fix.

---

## 6. Team: roles and the one number each person owns

| Person | Role | Owns this number |
|---|---|---|
| **Russel** | Sourcing, trends, final decisions | Gross margin %, stock aging |
| **Jacob** | Ops manager, CS lead, ledger hygiene | Unlogged sales = 0, ship within 48h |
| **Melanie** | CS (evenings), Live co-host | First-reply time, Live sales |
| **CJ** | Video: Live clips, shorts, unboxings | Posts per week, views |
| **Sheila** | Graphics: templates, product images, ad creatives | Turnaround under 24h |
| **Eugene** (incoming) | Marketing | ROAS, new customers per week |

---

## 7. Weekly scorecard (Monday, 15 minutes)

| Metric | Target |
|---|---|
| Daily gross (7-day average) | Month 1: ₱15K → Month 2: ₱25K → Month 4: ₱35K → Month 6: ₱50K |
| Orders per day | Month 6: 20+ |
| Unlogged sales | 0 |
| First-reply time | Under 15 minutes |
| Orders shipped within 48h | 95%+ |
| Inventory variance (Friday count) | Under 2% |
| Stock older than 60 days | Under 15% of inventory value |
| Preorder deposits vs supplier commitment | At least 50% |

---

## Next Actions

1. **Russel:** build the CC Ops Ledger Sheet and the 3 Google Forms. From that day, every sale goes through "Log a Sale". _(By 24 Oct)_
2. **Jacob:** back-log all sales since 24 Sep, fill the 144 blank statuses, and do a full stock count by location. _(By 24 Oct)_
3. **Russel:** cut payment accounts to GCash + one bank + cash, and tell the team which ones to give buyers. _(This week)_
