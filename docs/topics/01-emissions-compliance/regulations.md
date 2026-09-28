# Shipping emissions compliance framework

Context: this is item 1 from the Greek tramp-owner list in our earlier chat. Here's where the rules stand today and what that means for the ledger.

## Where the four regimes stand (September 2026)

**EU ETS.** Coverage phased in during 2024–2025 and reaches 100% of covered emissions from 1 January 2026, with methane and nitrous oxide added alongside CO₂. The geographic boundary is 100% of intra-EU voyages, 100% at berth in EU ports, and 50% of voyages between an EU and a non-EU port. For the 2025 compliance year, companies must submit verified emissions by 31 March 2026 and surrender allowances covering 70% of their 2025 emissions by 30 September 2026, so every ETS office is mid-surrender right now. Two new things: the United Kingdom has run its own ETS for shipping since 1 July 2026 (see `market-assessment.md` section 5), and the European Commission's July 2026 EU ETS revision for shipping proposal adds offshore operations to EU ETS, brings more ship categories into the reporting system, consolidates MRV and FuelEU reporting, aligns the responsible entity across regimes. Still a proposal, but it signals the direction: one "shipping company" entity, one reporting pipeline.

**FuelEU Maritime.** Caps the well-to-wake greenhouse-gas intensity of the energy a ship uses, for vessels of 5,000 GT and above calling at EU ports. The first cycle just finished: shipowners must submit vessel reports by 31 January 2026 and complete third-party verification by 31 March. Verified compliance must then be logged by 30 April. By 30 June 2026, penalties will be issued where applicable, and FuelEU Documents of Compliance will be provided. Target is −2% vs 2020 baseline now, −6% from 2030, with pooling, banking and borrowing of compliance balances.

**CII.** A vessel rated D for three consecutive years, or E for a single year, must submit a corrective action plan. The required intensity tightens every year — roughly 11% below the 2019 baseline by 2026, heading toward about 21.5% by 2030. No direct cost, but a bad rating hits chartering and financing. EEXI is a one-off technical certificate; it's done for most ships.

**IMO Net-Zero Framework.** Not adopted. Delegates voted 57 to 49 in favour of the delay. As a result, the session has been adjourned for 12 months. It resumes at a one-day extraordinary session on 4 December 2026, after MEPC 85 (30 November to 3 December 2026), per [DNV](https://www.dnv.com/news/2026/imo-mepc-84-revisiting-the-net-zero-framework/) and [National Law Review](https://natlawreview.com/article/imo-net-zero-framework-mepc-84-advances-negotiations-amid-political-headwinds). An earlier version of this note said October 2026. The NZF is unlikely to enter into force before March 2028. A July report says nations are "back on track" after MEPC 84. Structurally it's a global copy of FuelEU (fuel-intensity standard plus a pricing/credit mechanism), so a ledger built for FuelEU maps onto it.

## What the ledger has to model

The four regimes pull from the same raw data but compute different things. That's the whole product: one fact table, four calculators, one settlement engine.

**Facts (append-only, event-sourced):**

- Vessel: IMO number, GT, DWT, ship type, CII reference line, which company holds the ETS account (registered owner, or ISM/DoC manager if contractually assigned).
- Voyage legs: departure/arrival port and time, cargo on board, at-berth periods. Each leg gets a scope tag per regime (EU 100/50/0, UK 100/50/0, at-berth). This is harder than it looks: outermost regions, the anti-evasion transshipment port list, and split voyages.
- Bunkering: BDN, fuel grade, mass, LCV, supplier, and for bio/e-fuels the Proof of Sustainability. Without the PoS, FuelEU uses fossil default factors.
- Consumption: per day (noon report) or per leg, per consumer (ME/AE/boiler), per fuel, with ROB reconciliation. This is where the data is dirty.
- Emission factors: versioned tables for CO₂, CH₄, N₂O tank-to-wake (ETS) and well-to-wake (FuelEU). Factors change; you need the version pinned to the reporting year.

**Derived:**

- ETS: emissions per leg per gas → CO₂e × scope share → EUAs owed. UK ETS same shape, different scope and currency.
- FuelEU: energy used in scope × actual GHG intensity vs target → compliance balance (positive or negative), then pooling/banking/borrowing decisions across the fleet.
- CII: attained CII from annual fuel and distance → rating trajectory, projected year-end letter.
- NZF later: same as FuelEU with different factors and targets.

**Allowances and money:**

- EUA holdings in the Maritime Operator Holding Account: purchases (price, date, hedge), transfers received from charterers, surrenders. Same for UK allowances.
- FuelEU penalty exposure, banked surplus, pool agreements.

**Contracts and allocation (the part with thin competition):**

- Charter party per vessel per period, with clause type and parameters. The industry standard clauses are BIMCO's: ETS Allowances Clause for Time Charter Parties (charterer transfers EUAs or cash, usually monthly), ETSA for voyage charters, the SHIPMAN ETS clause (owner ↔ manager), the FuelEU Maritime Clause for Time Charters (charterer compensates the deficit they cause, gets credit for surplus), and the CII Operations Clause.
- Allocation engine: every emission event maps to a cost bearer by time window (TC: delivery to redelivery, minus off-hire) or by voyage (VC). Edge cases that break spreadsheets: redelivery mid-leg, off-hire during an EU leg, a sub-charter chain, fuel bunkered by one charterer and burned by the next, biofuel bought by the owner to fix FuelEU while the TC charterer pays ETS.
- Output: settlement statements per counterparty per month (EUAs due, cash due at agreed price basis, FuelEU credit/debit), and a reconciliation against what the counterparty actually transferred.

**Compliance workflow:** monitoring plan, annual report to the verifier, THETIS-MRV submission, surrender deadline, FuelEU DoC. Mostly deadlines and evidence, not math.

## Hard parts, in order of pain

1. Fuel consumption per leg from noon reports. Everything downstream is only as good as this. Budget for ROB reconciliation and manual correction with an audit trail.
2. Scope classification of a voyage. Codify it as a pure function with a test suite; the rules have exceptions and they change (UK ETS added a second set this July).
3. Contract-driven allocation with overlapping time windows. Model it as intervals over the event stream, not per-voyage totals.
4. Versioning. Emission factors, targets, scope rules and clause wording all change by year. Never recompute an old year with new tables.
5. Bio-fuel evidence. The PoS chain of custody is paper, and it's worth real money under FuelEU.

## What I'd validate before building

- Whether mid-size Greek owners still run this on Excel or have bought OceanScore/BetterSea/similar in the last 12 months. Both vendors above are marketing the same 2026 changes, so the space is not empty; the owner↔charterer settlement layer is where I'd look for the gap.
- Which side of the settlement your design partner sits on. An owner mostly wants to invoice charterers correctly; a charterer wants to audit those invoices. Same data, opposite UX.
- Whether the IMO Net-Zero Framework is adopted at the 4 December 2026 session. If it is, "one ledger, four regimes" becomes "one ledger, five", and the pitch gets stronger.

If you want, next step is a concrete schema (tables, the interval-allocation logic, and the scope-classification function with test cases).

## Simplified exposition of the analysis

Sure. Start from zero.

## What a ship company actually is

A ship is a big machine that burns fuel to move cargo. In Greece most ships are "tramp" ships: bulk carriers (grain, coal, iron ore) and tankers (oil, gas). The owner usually doesn't own the cargo. They rent the ship out to someone who does, under a contract called a **charter party**. Two common flavours:

- **Time charter**: the charterer rents the ship for a period (say 12 months) and decides where it goes. They pay for fuel.
- **Voyage charter**: the owner agrees to carry a cargo from A to B for a fixed price. The owner pays for fuel.

Remember this, because "who pays for fuel" is the root of "who pays for emissions".

Often a third company, a **ship manager**, runs the ship day to day (crew, maintenance, paperwork) on the owner's behalf.

## Why emissions suddenly cost money

Ships burn dirty fuel and emit CO₂. For decades nobody paid for that. Since 2024, regulators have started charging. There are four rulebooks, made by two different regulators:

**1. EU ETS (the EU's carbon tax, in effect)**
Every tonne of CO₂ a ship emits near Europe needs a permit called an **allowance** (an "EUA"). One allowance = one tonne. The company buys allowances on a market (currently roughly €75–80 each) and hands them over to the EU once a year. That's called "surrendering". A large ship can owe millions of euros a year.

The EU counts emissions like this: trips between two EU ports count fully, trips between an EU port and a non-EU port count half, time sitting in an EU port counts fully. Trips with no EU port don't count. It started at 40% in 2024, then 70%, and since January 2026 it's 100%, and they now also count methane and nitrous oxide, not only CO₂. The UK started its own copy in July 2026.

**2. FuelEU Maritime (the EU's fuel-quality rule)**
This one doesn't tax the amount you burn; it grades *how dirty* the fuel is, on average, over the year. Every year the maximum allowed dirtiness drops a little. If your average is too dirty, you pay a penalty. If it's cleaner than needed, you have a surplus you can save for next year, or share with another ship in your fleet ("pooling"). Burning some biofuel is the usual way to get under the line.

**3. CII (the UN's report card)**
The UN's shipping body (the IMO) gives every ship a yearly grade A–E for fuel efficiency. No fine, but a D or E grade means you must file a fix-it plan, and banks and charterers don't like renting or financing bad-grade ships. The bar rises every year, so a ship that was a C can drift to a D by doing nothing. EEXI is a related one-off technical check, already done.

**4. IMO Net-Zero Framework (the global version, not yet law)**
The IMO wants a worldwide rule that works like FuelEU: a global limit on fuel dirtiness plus a fee. In October 2025, after strong US opposition, a vote put the decision off for a year. The decision is now due at a session on 4 December 2026. If it passes, it starts around 2028. If your software handles FuelEU, it can handle this too, because it's the same kind of calculation.

## Why this is a mess in practice

All four rules need the same raw numbers: how much fuel, of what type, burned where, when. But every ship reports fuel with a daily email from the captain (the "noon report") that's typed by hand and often doesn't match the tank measurements. Then:

- Each rule does different math on those numbers.
- The numbers, the price of allowances, and the rules themselves change every year.
- And then someone has to decide **who pays**. If the owner has to hand allowances to the EU, but the charterer was the one deciding where the ship went and buying the fuel, the owner needs to bill the charterer. The contracts for that exist (an industry body called BIMCO writes the standard clauses), but the accounting is done by hand: figure out which emissions happened during whose rental period, at what price, send an invoice, chase the allowances or the cash, argue about the edge cases (ship changed hands mid-trip, ship was broken down for three days, etc.).

Today most mid-sized offices do this in spreadsheets, and the money involved is large enough that mistakes hurt.

## What the software would be

A **ledger**: a running, dated record of every fuel event and every trip, from which the system computes what each rulebook wants, tracks the allowances bought and handed over, and, using the contract terms, works out who owes whom and produces the monthly statement. Think of it like accounting software, where the "transactions" are fuel burned and the "accounts" are the four regulators plus each charterer.

The hard technical parts, in plain terms:

1. Cleaning up the captain's fuel reports so the numbers are trustworthy.
2. Deciding, for each trip, which rules apply and at what percentage (the port lists have exceptions).
3. Splitting emissions between overlapping rental contracts correctly.
4. Keeping old years frozen with the old rules while new years use the new rules.
5. Tracking the paperwork that proves a biofuel was really "green", because that paperwork is worth money.

## The business angle from the earlier chat

Big fleets have already bought software for this. Small and mid-sized Greek owners (10–40 ships) largely haven't, and the "who pays whom" settlement part is where existing products are weakest. That's the opening. The thing to check before building is whether that's still true in late 2026, and whether your first customer would be an owner (wants to send correct invoices) or a charterer (wants to check the invoices they receive).
