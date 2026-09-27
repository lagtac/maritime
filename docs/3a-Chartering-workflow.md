# Chartering workflow: how the work actually flows

The main parties are the **shipowner/operator**, the **charterer** (a commodity trader, miner, oil major, or another operator), **shipbrokers** in between, **port agents** at each port, and sometimes **P&I/FD&D clubs** and lawyers when there's a dispute.

The four pieces you listed happen in this order: **estimate → fixture → voyage execution (laytime) → claims**.

## 1. Voyage estimation (before fixing)

The operator or charterer works out whether a voyage makes money.

**Inputs:**
- **Vessel data:** speed and fuel consumption (laden, ballast, eco speed, port idle and working), deadweight, draft, grain/bale capacity.
- **Cargo:** quantity, stowage factor, load/discharge rates.
- **Route:** distances, canal choice (Suez, Panama, or Cape), ECA zones (which need more expensive low-sulphur fuel), and load line zones (which limit draft and therefore how much cargo fits).
- **Costs:** bunker prices at candidate ports, port disbursement estimates, canal dues, broker commissions, and now emissions costs. EU ETS applies to shipping and FuelEU Maritime is in force, so carbon cost is now a real line item.
- **Revenue:** freight rate (per tonne or lumpsum), or a hire rate if it's a time charter.

**Output:** TCE (time charter equivalent, net $/day). This is the number people compare across options.

**Why Excel wins here:** it's fast during live negotiation, easy to tweak for "what if", and every desk has its own tweaks. Structured systems like Veson IMOS feel slow for quick scenarios.

**Pain points:**
- Distance tables and bunker prices are copied in by hand.
- Intake calculations (draft limits, load line zones) are error-prone.
- The estimate rarely links to the actual voyage result, so there's little estimate-vs-actual learning.

## 2. Fixture and recap

Negotiation happens over email, chat (ICE, WhatsApp, Teams), and phone. It runs as offer → counter → "firm" → **subjects** (conditions such as board approval, shipper/receiver approval, stem confirmation) → subjects lifted → fixed.

The broker then sends a **fixture recap**, which is the agreed terms in text:
- vessel, cargo, and laycan (the window when the ship must arrive)
- ports and freight
- laytime terms (e.g. "10,000 MT per weather working day SHINC, reversible")
- demurrage and despatch rates, commissions
- "otherwise as per GENCON 94 / NYPE / ASBATANKVOY + charterers' rider clauses, logical amendments"

The formal **charter party (CP)** gets drafted later, sometimes weeks later.

**Pain points:**
- Recaps are free text, and each broker formats them differently.
- Amendments are written as "Cl. 23 delete, replace with…", so you have to reconstruct the effective clause yourself.
- The CP drifts from the recap.
- The same data gets retyped into ops systems, accounting, and the laytime sheet.
- There's no single source of truth for "what did we agree on laytime".

## 3. Laytime and demurrage

This is the most mechanical, highest-value, and most error-prone step.

**Inputs:**
- **CP laytime terms:**
  - allowed time (fixed hours or a rate per day), and whether it's reversible or averaged between load and discharge
  - SHINC/SHEX/FHEX variants (whether Sundays and holidays count)
  - when laytime starts: NOR tender rules and turn time (e.g. 6 or 12 hours after NOR)
  - exceptions: rain, shifting berths, strikes, breakdowns, bunkering, waiting for berth, "WIBON/WIPON" clauses
  - "once on demurrage, always on demurrage"
  - the demurrage rate and the despatch rate (often half demurrage)
- **Statement of Facts (SOF)** from the port agent: a timestamped log of arrival, NOR, berthing, start and stop of cargo work, rain stoppages, and so on. It usually arrives as a PDF or scan. The ship's version and the agent's version often differ.
- **Supporting documents:** the NOR, pumping logs (for tankers), and holiday calendars per port.

**Calculation:**
1. Build a timeline.
2. For each interval, decide whether it counts as laytime, and at what percentage (e.g. shifting counted at 50%, rain excluded).
3. Sum the time used and compare it with the time allowed.
4. The result is demurrage (the charterer pays) or despatch (the owner pays).

**Pain points:**
- Retyping SOFs.
- Interpreting clauses correctly.
- Port holidays.
- Different terms in the back-to-back contract. A trader has a CP with the owner and a sales contract with the buyer, each with its own laytime terms, so the same port call gets calculated twice with different rules.

## 4. Claims

This covers demurrage claims plus off-hire, bunker, performance/speed, and cargo shortage claims.

**Flow:**
1. Build the claim pack (CP extract, NOR, SOF, laytime calculation).
2. Submit it before the **time bar**, often 60–90 days, with full documents required.
3. The counterparty reviews and disputes line items.
4. Back-and-forth, then settlement, often at a discount.

**Pain points:**
- Claims are tracked in Excel across hundreds of voyages.
- Time bars get missed, which means real money lost.
- Documents are scattered across email.
- There's no view of recovery rate or aging.
- Disputes argue about the same recurring clause interpretations every time.

## Existing software

These are from memory; the market has consolidated recently, so verify before relying on it.
- **Veson IMOS:** dominant, enterprise, expensive, heavy.
- **Dataloy, Shipnet, Softmar, Danaos:** ops/ERP style systems.
- **Marcura (MarDem and others):** demurrage management, often outsourced as a service.
- **Shipfix, Sea, Voyager Portal, Signal Ocean:** fixture, market data, and email parsing, plus voyage collaboration.

Small and mid-size operators, brokers, and many trading houses still run on Outlook plus Excel. Enterprise tools are too costly or rigid for them, and Excel matches how they think.

## Where I'd focus

**Laytime/demurrage plus claims tracking is the best wedge:**
- **Clear ROI.** Every hour miscalculated or time-barred claim is direct dollars, and users can see money recovered.
- **Bounded problem.** The inputs (CP terms and SOF) and the output (a calculation plus a claim pack) are well defined.
- **The inputs already arrive by email** as PDFs and text, which suits LLM extraction.
- **It sits downstream of the recap,** so you naturally expand upstream later: parse recaps into structured terms, then do estimates.

**Architecture principles:**
- **LLMs extract, a deterministic engine calculates.**
  - An LLM turns the SOF and recap/CP clauses into structured events and terms.
  - A human reviews and confirms, with each value linked back to its source line.
  - A plain rules engine computes laytime. Every line in the result must be explainable ("rain 14:20–16:05 excluded per Cl. 8"), because the counterparty will dispute it.
- **Model laytime terms as a versioned rule set per contract.** The same port call can then be run against the CP and the sales contract.
- **Build an Outlook/Gmail add-in or email forwarding.** Don't make users leave their inbox.
- **Keep Excel import/export first-class.** Counterparties will send and expect Excel sheets.

The hard parts aren't technical. They are clause interpretation edge cases (you'll need a domain expert, e.g. an ex-demurrage analyst) and trust: users must be able to audit every minute.

Which angle are you coming from: building a product, or building an internal tool for a specific office?
