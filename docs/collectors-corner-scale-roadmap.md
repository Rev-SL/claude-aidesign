# Collector's Corner: Roadmap to ₱50,000 Daily Gross

_Prepared 14 Oct 2026 (Asia/Manila). Based on the Notion orders database (630 rows, May–Sep 2026) and Shopify analytics._

---

## 1. Where you actually are (from your own data)

| Signal | What the data shows | What it means |
|---|---|---|
| Order logging | Last Notion order was **24 Sep**. Nothing logged for the past 3 weeks. | Orders are being missed or logged late. |
| Order status | **144 of 630 orders (23%) have no status.** | Nobody can tell what has shipped. |
| "Total Paid" field | Free text. A ₱1,185 item is logged as **₱1,185,000**, and there's a ₱2,600,000 cash meetup row. | Revenue totals are unusable, so the true daily gross isn't known yet. |
| Shopify | **3 orders in 6 months** (₱27,990). | The website isn't selling. Sales happen in DMs, Lives, meetups and preorders. |
| Sales pattern | Jul: 265 orders (185 preorders). Aug: 43. Sep: 103 (59 preorders). | Sales come from drops, not a steady daily flow. |
| Preorders | **103 orders sit "on hold pre-orders"**. | That's a large CS and cash liability to track. |

**The diagnosis:** sales aren't the first problem. You can't count your sales, so you can't scale them. Getting to ₱50K a day needs one place every peso and every card goes through, and a steady daily selling rhythm in place of drop spikes.

---

## 2. The ₱50K/day math

₱50,000/day = **₱1.5M/month**. At a ~₱2,500 average basket that's **about 20 orders a day**. (Confirm the real average basket once Phase 0 data is clean.)

| Channel | Target / day | How |
|---|---|---|
| FB Live / TikTok Live selling | ₱20,000 | 4 scheduled Lives a week, about ₱35K per Live |
| Shopify website (singles, sealed, preorders) | ₱12,000 | Automated payment, restock alerts, Klaviyo flows |
| Shopee + TikTok Shop | ₱8,000 | Sealed products and low-ticket singles |
| Oripa / Dibs packs | ₱5,000 | Weekly runs (use `oripa-planner` for odds and filler cost) |
| Events, consignment, B2B | ₱5,000 | Card shows averaged across the month, plus Kura Cases cross-sell |
| **Total** | **₱50,000** | |

No single channel has to carry it. The plan fails if you depend on one big drop a month.

---

## 3. The core fix: one front door for every sale

**Recommendation: every sale becomes a Shopify order, whatever the channel.** That covers DM, Live, meetup, event and preorder sales.

- Sale in a DM or Live → CS creates a **Shopify draft order**, then sends the **payment link** (GCash/card through Shopify Payments or PayMongo).
- At events or walk-ins → **Shopify POS** on a phone. It scans barcodes and takes cash or GCash.
- Result: orders, customer records, payment status and **inventory deduction** all happen automatically. Nobody types "Total Paid" by hand again.

Then split the tools by job:

| Tool | Job | Who updates it |
|---|---|---|
| **Shopify** | Orders, inventory, customers, payments (source of truth) | Jacob, Melanie (CS) |
| **Google Sheets** | Money: daily dashboard, expenses, purchases, landed cost, P&L | Pulled from Shopify via Matrixify; expenses and purchases come in through Google Forms |
| **Notion** | Work: tasks, SOPs, content calendar, event calendar, trend board | Everyone |

The Notion orders database becomes **read-only history** once Shopify takes over.

### Google Sheets layout ("CC Ops Ledger")

1. **DASHBOARD**: today's gross vs ₱50K, 7-day average, orders, average basket, open preorders, cash on hand, unshipped orders.
2. **ORDERS**: daily Matrixify export from Shopify. Nobody types in this tab.
3. **PURCHASES** (Google Form): date, supplier, items, qty, USD/JPY cost, Vikings weight, **landed cost per unit** (auto-calculated).
4. **EXPENSES** (Google Form): date, category (ads, shipping, supplies, salaries, rent, event fees), amount, paid via, receipt photo.
5. **INVENTORY**: Shopify stock levels plus cost basis from PURCHASES, giving margin per SKU and **aging** (stock older than 60 days gets flagged).
6. **PREORDERS**: deposits collected vs supplier payments due vs ETA, per release.

**Rules that keep it clean:**
- Money columns are numbers only, with data validation (no "2,600,000" typed as text).
- Every dropdown is fixed: status, payment method, location.
- An **"Unlogged" counter** on the dashboard compares GCash/bank inflows to Shopify orders. The target is 0.

---

## 4. Your 8 "always urgent" items, each with an owner and a system

| Need | System | Owner | Standard |
|---|---|---|---|
| Always answer customers | Meta Business Suite inbox with saved replies, plus an auto-reply FAQ (prices, payment, shipping, preorder ETA) | Jacob (day), Melanie (evening and Lives) | First reply in **under 15 minutes** during 9AM–11PM |
| Track orders | Shopify order status, with an auto-notification once a tracking number is added | Jacob | No order without a status after 24h |
| Track expenses | Google Form → EXPENSES tab | Whoever spends | Logged the same day, with a receipt photo |
| Track purchases | Google Form → PURCHASES tab (landed cost auto-calculated) | Russel | Logged before stock is listed |
| Log all 3 | Sheets DASHBOARD pulls them together | Jacob reviews daily | 0 unlogged inflows |
| Seamless | One front door (Shopify) + Forms; no double entry | Russel sets up, Jacob runs it | Each sale typed once |
| Update inventory | Shopify locations (Pilar, Sven, Greenhills, Festival), with POS barcode scan in and out | Jacob | Friday stock count; under 2% variance |
| Check trends | Monday 30-minute Trend Review in Notion: JP release calendar, Card Ladder/PriceCharting movers, Shopee bestsellers, customer wishlist log | Russel + Eugene | Every buy decision ties to a trend note or deposits |

**Preorder rule:** only commit supplier money when deposits cover at least 50% of the order. This keeps the 103 on-hold preorders from becoming a cash trap.

---

## 5. Roadmap

### Phase 0: Foundation (Weeks 1–3, now to early Nov)
**Goal: know the real daily gross.**
- Back-log every order from 24 Sep to today. Fill the 144 blank statuses.
- Turn on Shopify Payments/PayMongo, draft-order payment links and Shopify POS.
- Create Shopify locations and do a full stock count. Scan sealed products and slabs with POS.
- Build the CC Ops Ledger Sheet (6 tabs) and the 2 Google Forms.
- Write 3 SOPs in Notion: "How to log a sale", "How to ship", "How to answer DMs". (Use `sop-writer`.)
- **Exit check:** 7 straight days with 0 unlogged sales, and a trustworthy daily gross number.

### Phase 1: Daily selling engine (Weeks 4–8, Nov to mid-Dec)
**Goal: ₱20–25K/day average, with no reliance on one big drop.**
- **Lives:** fixed schedule, e.g. Tue/Thu/Sat/Sun 8PM. Melanie runs CS, CJ clips highlights the next day.
- **Content:** CJ makes 1 short a day from Lives, pulls and unboxings. Sheila makes reusable templates (price lists, "New Arrivals", "Sold Out", preorder cards) so posting takes minutes.
- **Ads:** Facebook placements only (avoid IG). Retarget Live viewers and website visitors. Run `ads-reviewer` weekly.
- **Klaviyo:** restock alert, abandoned checkout, preorder-arrival flows, and a weekly "New in" email.
- **Marketplaces:** list sealed products on Shopee and TikTok Shop, synced from Shopify inventory.
- **Christmas push:** gift bundles, starter decks, ₱999/₱1,999/₱4,999 mystery boxes and an oripa run.

### Phase 2: Scale (Months 3–6, Jan to Apr 2027)
**Goal: ₱35K/day by month 4, ₱50K/day by month 6.**
- **Eugene starts:** owns ads, content calendar and the Monday trend review output. KPI: blended ROAS and new customers per week.
- **Hire one packer/CS** when orders average 20 a day for 2 weeks, so Jacob moves from doing CS to managing it.
- **Repeat buyers:** VIP tier (early preorder access, Live-only slots), plus a monthly pack subscription for predictable revenue.
- **Singles catalog growth:** bulk-list singles via Matrixify, with condition as a structured field. More SKUs online means more daily web sales.
- **Sourcing:** Japan/Asia buying trips (Asia Tour) driven by the trend board, not gut feel. Run `sourcing-analyst`, then `grading-desk`, on big buys.

---

## 6. Team: roles and the one number each person owns

| Person | Role | Owns this number |
|---|---|---|
| **Russel** | Sourcing, trends, final decisions | Gross margin %, stock aging |
| **Jacob** | Ops manager, CS lead, Sheets/Shopify hygiene | Unlogged sales = 0, ship within 48h |
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

1. **Russel:** turn on Shopify Payments/PayMongo and Shopify POS. Rule from today: every sale gets a Shopify order. _(This week)_
2. **Jacob:** back-log all sales since 24 Sep and fill the 144 blank statuses in Notion, then do a full stock count by location. _(By 24 Oct)_
3. **Russel:** set up the CC Ops Ledger Google Sheet and the Expenses and Purchases Google Forms. _(By 31 Oct)_
