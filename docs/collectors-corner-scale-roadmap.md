# Collector's Corner: Roadmap to ₱50,000 Daily Gross

_Updated 16 Oct 2026 (Asia/Manila). Built on the live tracker "Collector's Corner – Sales & Inventory Tracker" (Google Sheets, synced hourly from the Notion orders database by Apps Script) and the team's stock locations._

---

## 1. The real numbers

The dashboard says **₱13.33M all-time revenue and ₱26,086 average order**. Both are inflated. 8 orders of ₱300K or more make up **₱6.8M, half the total**. Some are real (the ₱2.6M PSA 10 Nika Luffy pair, ₱480K PSA 10 Pikachu). Some are almost certainly typos:

| Row | Logged | Why it's suspect |
|---|---|---|
| John Paulo Manuel, 30th ETB preorder (28 Jul) | ₱1,185,000 | Price ₱1,185, so it's off by ×1,000 |
| Vlade Mark Navarro, 30th ETB preorder (30 Jul) | ₱592,500 | Same ETB; 500 units is unlikely |
| Nicole Syjuco, Ascended Heroes bundle (24 and 25 May) | ₱300,000 ×2 | Same item on consecutive days: possible duplicate |
| Santos Manuel (14 Jun) | ₱903,350 | Multi-item total. Verify it isn't double-counted with item rows |

**Monthly gross, excluding the ₱300K+ rows:**

| Month | Gross | Orders | Per day |
|---|---|---|---|
| May | ₱898,893 | 56 | ₱29K |
| Jun | ₱2,257,786 | 133 | **₱75K** |
| Jul | ₱2,384,815 | 228 | **₱77K** |
| Aug | ₱586,430 | 40 | ₱19K |
| Sep | ₱392,800 | 43 | ₱13K |
| Oct (to 16th) | ₱0 logged | 0 | — |

**What this means:**
1. **You've already done ₱50K a day.** June and July ran at ₱75K+/day, carried by the 30th Anniversary hype and high-ticket slabs. The goal isn't to discover how to get there. It's to stop the drop-off that follows each hype cycle.
2. **Sales fell 75–85% after July.** The steady daily engine isn't there yet, so revenue follows release hype.
3. **Nothing has been logged since 24 Sep.** The Notion sync is set up, so the gap means sales stopped being entered, not that the sync broke. October is invisible.
4. **The typical order is ₱5,140 (median), and the average is ~₱13,000 without the big outliers.** At those numbers, ₱50K/day is **4–10 orders a day**, not 20.

---

## 2. What's broken in the tracker today

| Problem | Effect | Fix |
|---|---|---|
| **Inventory, Stock Log, Auto Log, Unmatched and Consignee Settlement tabs are empty** | Dashboard shows #REF! for inventory value and reorder alerts | Rebuild those tabs (layout in section 4) |
| Notion "Total Paid" is a text field | Typos like ₱1,185,000 flow straight into revenue | Add a **number** field "Amount ₱" in Notion. Make it required in the template. |
| No sanity check on amounts | Big typos look like big sales | Add a **"Check"** column in Orders that flags any amount over ₱100K, or over 20× the item price. Jacob clears the flags weekly. |
| 144 orders with no status | Can't tell what's shipped or paid | Jacob fills them in. Make Status required in the Notion template. |
| 155 orders with no delivery method | Can't track shipping cost or what's in transit | Make Delivery required |
| Notion "Location of item" only has Pilar, Sven, Festival, Greenhills | Can't tell which location or partner sold the item | Update the options (section 3) |
| Sales don't deduct stock | Inventory is never right | Phase 1: match product names to SKUs (the Auto Log and Unmatched tabs were set up for this) |

**Keep the Notion → Sheets setup.** The team already logs in Notion, and the sync works. Don't introduce a new form. Tighten the Notion template so bad data can't get in, and let the Sheet do the maths.

---

## 3. Stock locations and consignment

Update the Notion **"Location of item"** options and the Sheet's location list to these 8 places.

| Location | Type | Owner of stock | Sale gets logged… |
|---|---|---|---|
| **Pilar Main HQ** (website stock) | Owned, main warehouse | CC | As it happens, in Notion |
| **One Ayala glass cabinet** | Owned, cabinet | CC | From the weekly cabinet sales report |
| **Festival Mall glass cabinet** | Owned, cabinet | CC | From the weekly cabinet sales report |
| **Sven glass cabinet** | Owned, cabinet | CC | From the weekly cabinet sales report |
| **RGB Toyzone** | Consigned out | CC | From the partner's sales report, with payment "Partner – pending" |
| **Anti Hero** | Consigned out | CC | Same |
| **Metromart** | Consigned out | CC | Same |
| **Tokyo Mikin items** (held at HQ) | Consigned in | **Tokyo Mikin** | As it happens, with Owner = Tokyo Mikin |

Greenhills stays as an option if it's still used; otherwise retire it.

### Consigned out (RGB Toyzone, Anti Hero, Metromart)
- **Every delivery:** a Stock Log row (OUT from HQ, IN to partner) plus a photographed, signed delivery list.
- **Per partner, record:** commission they keep, payout schedule, who pays for loss or damage.
- **Every 2 weeks:** get their sales report and log each sale in Notion.
- **Monthly:** settle the remittance against "Partner – pending" sales and count what's on their shelf. Anything unsold after 30 days comes back or gets swapped.

### Glass cabinets (One Ayala, Festival Mall, Sven)
- Refill weekly from HQ with fast movers only, logged in Stock Log.
- Photo of the cabinet at every visit.
- Cabinet rent goes in expenses under the cabinet's name. A cabinet that doesn't cover rent plus margin for 2 months running gets closed or moved.

### Consigned in (Tokyo Mikin): first time, so put it in writing
**Their stock isn't your inventory.** It must stay out of your inventory value and your cost of goods. Only your commission is CC revenue.

Before selling a single piece, agree on 1 page:
1. Item list with condition, photos and **minimum price** for each.
2. **Commission** CC keeps. (Your default for individual consignors is 10%. Decide whether that covers Live, CS and shipping work for a store.)
3. Who sets the final price, and whether you can discount in Lives or bundle.
4. **Payout schedule** (e.g. 15th and month-end).
5. Who absorbs loss or damage, and when unsold items go back (e.g. after 60 days).
6. Who pays payment fees and shipping.

In the Sheet, the **Consignee Settlement** tab shows each Tokyo Mikin sale split into **their payout** and **CC commission**, with a running "Owed to Tokyo Mikin" balance. Paying on time is what makes other stores consign with you.

### What the ₱50K target counts
The dashboard shows two numbers:
- **Gross sales:** everything sold, including Tokyo Mikin items. This is the ₱50K target.
- **CC revenue:** gross minus consignor payouts.

---

## 4. Tracker tabs

**Built 16 Oct 2026:** Inventory, Stock Log and Consignee Settlement are live with formulas, dropdowns and frozen headers. Location and partner lists, plus how-to notes, are in the Setup tab. Dashboard rows 11–14 now show inventory value, reorder count, money owed to consignors, and money partners owe CC. Auto Log and Unmatched are left for the Apps Script SKU matching. Expenses and Purchases are still to build.


| Tab | One row per… | Key columns |
|---|---|---|
| **Inventory** | Product × location | SKU, name, owner (CC / Tokyo Mikin), location, cost, price, opening qty, in, out, **on hand** (formula), value at cost (col J), reorder level, status "REORDER" (col L), days since last sale |
| **Stock Log** | Movement | Date, SKU, location, type (IN / OUT / TRANSFER / ADJUST), qty, by whom, note |
| **Auto Log** | Sale the script matched to a SKU | Notion ID, SKU, qty, location (stock-out written automatically) |
| **Unmatched** | Sale the script couldn't match | Notion ID, item text. Jacob maps these weekly. |
| **Consignee Settlement** | Consignor sale | Date, consignor, item, sale price, commission %, payout due, paid date |
| **Expenses** (new) | Expense | Date, category, amount, paid via, location/cabinet, receipt link |
| **Purchases** (new) | Buy | Date, supplier, items, qty, cost (USD/JPY), Vikings weight, landed cost per unit |

The dashboard already expects inventory value in Inventory column J and "REORDER" flags in column L. The rebuilt tab keeps those positions, so the #REF! errors clear.

---

## 5. The ₱50K/day plan: steady sales between hype cycles

At a ~₱13K average order, **₱50K/day ≈ 4 orders a day, or 120 a month**. June did 133 and July did 228. The target is to hold that through quiet months.

| Channel | Target / day | How |
|---|---|---|
| FB Lives (4 a week) | ₱17,000 | Fixed schedule. Day Live 3 (16 Sep) sold 9 × 30th booster boxes at ₱12,500 in one session: repeat that format weekly. |
| High-ticket slabs and sealed (meetup or bank transfer) | ₱10,000 | 1 high-value sale every 3–4 days. Post PSA 10s and cases weekly to the VIP buyer list. |
| FB page and DMs, website (Pilar HQ) | ₱8,000 | Daily "New in" post; every post links to the website |
| Glass cabinets: One Ayala, Festival Mall, Sven | ₱6,000 | ₱2K/day each; weekly refill with fast movers |
| Consignment partners: RGB Toyzone, Anti Hero, Metromart | ₱3,000 | Restock what sells; 30-day pull rule |
| Preorders (deposits for the next release) | ₱4,000 | Always one preorder window open. Only pay suppliers when deposits cover 50%+. |
| Shopee, oripa, events | ₱2,000 | Fill-in channels |
| **Total** | **₱50,000** | |

**Repeat buyers are the lever.** Kerstie Dimple Barillo has 23 orders and ₱1M+ in spend. Build a **VIP list of the top 30 buyers** from the Orders tab. They get first access to slabs, sealed and preorders through a private group chat before anything goes public.

---

## 6. Roadmap

### Phase 0: Clean data (now to 31 Oct)
- Jacob logs every sale since 24 Sep in Notion, and fills the 144 blank statuses and 155 blank delivery methods.
- Jacob verifies or fixes the 4 suspect rows in section 1.
- Add "Amount ₱" (number, required) to the Notion template. Make Status and Delivery required. Update the Location options to the 8 locations.
- Rebuild the Inventory, Stock Log and Consignee Settlement tabs. Count stock at all 8 locations and enter it as the opening qty.
- Sign the Tokyo Mikin agreement. Confirm terms with RGB Toyzone, Anti Hero and Metromart.
- **Exit check:** the dashboard shows real October numbers with no #REF! and no unverified ₱100K+ rows.

### Phase 1: Daily engine (Nov to mid-Dec)
**Goal: ₱30K/day average, with no month below ₱25K/day.**
- Lives 4× a week. Melanie runs CS and logs in Notion during the Live. CJ clips highlights the next day.
- VIP group chat launched with the top 30 buyers.
- Sheila builds templates: "New in", price list, PSA slab feature, preorder card, Live schedule.
- Facebook-only ads with Messenger as the destination, retargeting Live viewers. Run `ads-reviewer` weekly.
- Auto stock-out: product-name → SKU matching in the Apps Script (Auto Log / Unmatched).
- Christmas push: bundles, mystery boxes (₱999 / ₱1,999 / ₱4,999), an oripa run.

### Phase 2: Scale (Jan to Apr 2027)
**Goal: ₱50K/day held for 3 straight months.**
- Eugene owns ads, content calendar and the Monday trend review. KPI: new buyers per week and ROAS.
- Hire a packer/CS once orders hold above 6 a day for a month.
- A monthly pack subscription for predictable base revenue.
- Japan/Asia sourcing trips driven by the trend board and VIP requests. Run `sourcing-analyst`, then `grading-desk`, on big buys.

---

## 7. Your 8 "always urgent" items

| Need | System | Owner | Standard |
|---|---|---|---|
| Always answer customers | Meta Business Suite saved replies + auto-reply FAQ | Jacob (day), Melanie (evening, Lives) | First reply under 15 min, 9AM–11PM |
| Track orders | Notion status (required) → Orders tab | Jacob | No blank status after 24h |
| Track expenses | Expenses tab | Whoever spends | Same day, with receipt |
| Track purchases | Purchases tab with landed cost | Russel | Logged before stock is listed |
| Log all 3 | Dashboard | Jacob, nightly | 0 sales missing vs GCash/bank inflows |
| Seamless | Log once in Notion; the Sheet does the maths | Russel | No double entry |
| Update inventory | Stock Log + auto stock-out | Jacob | HQ every Friday, cabinets weekly, partners monthly |
| Check trends | Monday 30-min trend review in Notion | Russel + Eugene | Every buy ties to a trend note, VIP request or deposits |

---

## 8. Weekly scorecard (Monday, 15 minutes)

| Metric | Target |
|---|---|
| Daily gross (7-day average) | Nov ₱30K → Jan ₱40K → Mar ₱50K |
| Orders per day | 4+ |
| Days with zero sales logged | 0 |
| Rows flagged for checking | 0 at week end |
| First-reply time | Under 15 minutes |
| Stock older than 60 days | Under 15% of inventory value |
| Owed to Tokyo Mikin / partners, overdue | ₱0 |

---

## Next Actions

1. **Jacob:** log all sales since 24 Sep in Notion, fill the blank statuses, and verify the 4 suspect rows. _(By 24 Oct)_
2. **Russel:** sign the Tokyo Mikin agreement before selling any of their items. _(This week)_
3. **Russel:** approve rebuilding the Inventory, Stock Log and Consignee Settlement tabs, then have Jacob count stock at all 8 locations. _(By 31 Oct)_
