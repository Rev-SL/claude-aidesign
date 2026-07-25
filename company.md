# Collector's Corner — Company Memory

> Operating memory for the one-person company. The Squad Lead (and every agent in
> `.claude/agents/`) reads this to avoid re-deriving how the business works. Update it
> whenever a standing fact changes. Numbers dated to **July 2026**.
>
> **Read `business-strategy.md` first** — it holds the North Star (**₱1M/month NET**), the
> four leverage plays, and the dev roadmap. This file is the operating facts underneath it.

---

## 1. What the business is

**Collector's Corner Philippines** — the primary business. Buys sealed Pokémon and One
Piece TCG (mostly Japanese/Chinese exclusives) sourced in Japan, sells in the Philippines.
Tagline: *"Sourced in Japan. Sold in the Philippines."* Online at **collectorscorner.store**,
physical presence at **Dibs Pack**. Channels: Shopify store, Notion-run manual orders/
pre-orders, card shows, meetups. **RevEarnsDaily** = personal brand / content flywheel.

**North Star:** #1 TCG store in PH and **₱1M/month NET profit** (see `business-strategy.md`).
The four leverage plays that get there: (1) TikTok Live selling, (2) card syndicate / outside
capital, (3) Oripa scaling, (4) buyback/kaitori board.

**Deprioritized brands (no strategic effort unless asked):** Nice Dae Studio (photo booth,
OPPO PH), South Locker (sneakers, supplier Jingfeng), Kura Cases (B2B accessories), vending.

**Team:** Jacob (backend/ops sign-off, non-technical), Eugene (marketing decision maker),
CJ (video), Melanie (part-time sales), Sheila (part-time design), Lawrence (inventory
co-owner, 50/50 syndicate precedent), Kyle (outgoing dev, being replaced).

---

## 2. Money reality (as of 2026-07-16)

Source of truth for sales = Notion **"Collector's Corner Sales and Preorders"** database
(data source `collection://37aa701e-331d-81b3-a3b7-000bc30474ea`). Cash is logged as free
text in `Total Paid` ("php 6,800", "dp 3,600").

Source of truth for **cost** = Notion **"Collector's Corner — COGS & Landed Costs"** database
(data source `collection://1f6a9879-22d0-48a2-a75b-32f4062c165e`,
[link](https://app.notion.com/p/abd72c6cf23f481583ccf4f12f9eab6a)). One row per purchase lot:
buy price + Vikings freight → landed cost (PHP) and gross margin per unit, related back to the
sales orders. **Intake workflow:** Russel drops a payment screenshot + product list + tracking
number in chat; the Squad Lead adds the row (Buy Price USD, Weight kg, Handling, FX, Qty, Sell
Price, Tracking #, Payment Proof). This is what finally makes true per-order margin readable.

**Revenue (net cash collected):**

| Month | Revenue | Notes |
|---|---|---|
| May 2026 (ramp from 5/22) | ₱2.41M | 70% from mega-orders ≥₱100K |
| June 2026 (full) | ₱3.21M | ₱107K/day; 51% mega-orders |
| July 2026 (to 15th) | ₱692K → run-rate ₱1.43M | only 16% mega; core retail ₱38.8K/day |

**Mega-orders (≥₱100K, bulk/wholesale/consignor) are the biggest single driver:** 8 orders
= ₱2.77M of ₱6.3M total (44%) in <3 months. They land irregularly and are relationship-
driven, not ad-driven. Treat wholesale prospecting as a core profit engine, not luck.

**Pre-order deposit pipeline (collected, not yet fulfilled — this is a liability until
delivered):** Pitch Black ₱145K, Prismatic ₱35K, OP-18 ₱17K, First Series 3 ₱11K.

---

## 3. Unit economics & margin (estimated — replace with real COGS ASAP)

Landed cost model = **Japan/US buy price + Vikings freight ($13.50/kg, 5.01–50kg tier,
÷6000 volumetric, $3/parcel handling, DDP) × FX ₱62/USD**.

| SKU (case wholesale) | Buy USD | Landed ₱ | Typical sell ₱ | Gross margin |
|---|---|---|---|---|
| JP Pokémon box, cheap set | ~$62 | ₱4,323 | 6,800 | **36%** |
| JP Pokémon box, Mega Symphonia m1S | $79.9 | ₱5,475 | 6,800 | **20%** |
| JP Pokémon box, Mega Brave m1L (hype) | $97.9 | ₱6,591 | 6,800 | **3% (near breakeven!)** |
| One Piece ENG box | $119.8 MSRP | ₱8,239 | must sell >₱9K | thin unless hype markup |
| One Piece JP box (imported) | ~$46 | ₱3,289 | 5,000–6,800 | 35–52% |
| ETB / half box | ~$40 | ₱2,875 | 3,600 | 20% |

Cross-brand anchor (South Locker sneakers, real cost→resell): **avg 25.4% GM**.

**The key lesson:** sealed-box margin is dictated almost entirely by *which set you buy at
what wholesale*. The same ₱6,800 sell price is 36% margin on a cheap set and 3% on a hype
set. Buying hype boxes at case price and selling at "normal" retail is a near-loss. Fat
margin lives in: singles/chase cards, graded slabs (PSA), oripa/pack rips, accessories
(Kura), and pre-orders where FX + price are locked early.

**Blended working assumption: ~27% gross margin** (range 20% sealed-heavy → 40% value-add).

---

## 4. Break-even & target margin

Fixed cost envelope = **₱200,000/month** (staff + ads + subscriptions). Real breakdown:

| Line | Monthly |
|---|---|
| Melanie (sales, ₱500/day × 26) | ₱13,000 |
| Jacob (backend, ₱880/day × 30; 28d → ₱24,640) | ₱26,400 |
| Sheila (graphics, fixed) | ₱15,000 |
| CJ (video, ₱15,000 cash + ₱5,000 sealed) | ₱20,000 |
| Subscriptions (combined) | ₱6,000 |
| **Non-ad fixed** | **₱80,400** |
| **Ads headroom (₱200K − fixed)** | **~₱119,600** |

Notes: non-ad fixed ≈ **₱80K/mo** (of which **₱75,400 is cash** — CJ's ₱5K is paid in sealed
product, not pesos). Subscriptions sit *inside* the ₱200K. The **~₱120K ad budget is the
scalable lever**; the ₱80K people/tools cost is fixed and lean. This ₱200K envelope is the
survival fixed cost only — it excludes COGS/landed cost (see §3) and the other variable lines
(payment fees, rent, disputes) that also reduce true NET.

| Blended GM | Break-even revenue/mo |
|---|---|
| 20% | ₱1,000,000 |
| 25% | ₱800,000 |
| **27%** | **₱741,000** |
| 30% | ₱667,000 |
| 35% | ₱571,000 |

Net profit at 27% GM: June ₱667K, July run-rate ₱186K, July core-only (ex-mega) ₱124K.

**Target: hold blended GM ≥ 30% and revenue ≥ ₱1M/mo.** That keeps ≥₱100K/mo net even in a
weak, mega-order-free month. The risk case is a month of ₱800K revenue at 20% GM (all thin
sealed, no mega) = ₱160K gross < ₱200K fixed = **loss**. The cushion is thinner than the
top-line suggests; protect it by mix, not just volume.

---

## 5. Suppliers, freight, payments

- **Freight:** Vikings Global (US→PH, account VGE000136). $13.50/kg (5.01–50kg), ÷6000
  volumetric, $3/parcel, DDP included.
- **FX:** ₱61–63/USD — confirm spot before finalizing any P&L. Wise for USD moves.
- **Payments in:** GCash, bank transfers (BDO/BPI/Gotyme/Maribank/Maya), CO Link, cash,
  PayMongo/credit card. **High-value >₱30K → steer to bank/GCash, never PayPal.**
- **Sneaker supplier (South Locker):** Jingfeng.

---

## 6. Reference websites it follows

**Pricing / market data:**
- TCGplayer (`tcgplayer.com`) — US market price reference
- PriceCharting (`pricecharting.com`) — sealed + singles price history
- Card Ladder (`cardladder.com`) — trade valuation weights (used in pro-rata trade costing)

**Japan/Asia sourcing (sealed):**
- Zenpan Japan (`zenpan-japan.com`) — JP box + case wholesale
- PokeUnlimited (`pokeunlimited.com`), Japan Trading Card Store (`japantradingcardstore.com`)
- Pocket Collection (`pocketcollection.ca`), Card Binder (`card-binder.com`) — CN/JP exclusives

**Release calendars:** One Piece official (`en.onepiece-cardgame.com/products`), Pokémon
Center for ENG set dates.

**Grading:** PSA (ROI rule `R = P10 / ((Craw + Cgrade) ÷ G)`).

**Sneakers (South Locker):** GOAT (`goat.com`), Revolve.

---

## 7. Known gaps / data upgrades (priority order)

1. ~~Add a COGS/landed-cost ledger.~~ **DONE (2026-07-17)** — the "COGS & Landed Costs"
   database now exists (§2). Populate it going forward so estimates become actuals.
2. **Standardize `Total Paid`** — one clean numeric field + a separate deposit field. Free
   text ("php 6,810 w/ shipping fee php 300 (downpayment) php 21,500 total") is unparseable
   without heuristics.
3. **Fix Supermetrics** (Meta Ads `act_549260347455113`) — no valid CLAUDE subscription on
   team `russelmilanesramos`. Until fixed, no defensible ad scale/pause decision.
4. **Backfill** the COGS ledger with recent buys (Vikings invoices) so the blended-margin
   estimate in §3 can be replaced with real numbers.

---

## 8. Standing constants (do not re-derive)

- Vikings: $13.50/kg (5.01–50kg), ÷6000, $3/parcel, DDP.
- FX: ₱61–63/USD.
- PSA ROI: `R = P10 / ((Craw + Cgrade) ÷ G)`.
- Consignor default commission: 10% (JB, Gibbs).
- Facebook historic ROAS ~6.9; Instagram ~0.84 (avoid IG spend by default).
- Meta primary demo: M25–34.
- Never route Collector's Corner transactions through the South Locker MID (compliance).
