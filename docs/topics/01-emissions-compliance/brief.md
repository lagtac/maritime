# Item 1: Emissions compliance

Status: draft | Last updated: 2026-09-28 | Overview item: 1 in `docs/overview.md`

This brief is built from the notes already in this folder (`regulations.md`, `market-assessment.md`, `greek-terminology.md`) and from `docs/hypotheses.md`. No new research was done for it. The scorecard scores one idea: a tool that lets a charterer check the ETS and FuelEU invoices it receives, which `market-assessment.md` ranks first.

## Summary

Since 2024, EU rules make ships pay for their emissions, and the bill usually lands first on the Greek manager that holds the ship's ISM Document of Compliance. The manager then passes the cost on to the charterer under a charter party clause. Software that computes the cost and invoices the charterer is crowded: OceanScore, DNV, Veson, ABS and managed-service desks already sell it, including to Greek owners. The idea the notes rank first is the other side: helping charterers check those invoices. No product for that was found, but few charterers work from Piraeus (E5, weakened), so a Greek builder would mostly sell abroad. The item is worth testing with charterer interviews, but its best idea does not fit the Greek market well.

## The problem

Four sets of rules put a price or a grade on a ship's emissions. `regulations.md` explains each one.

- **EU ETS:** the ship's company must hand the EU one allowance (EUA) per tonne of CO₂-equivalent emitted on EU voyages. Coverage reached 100% of in-scope emissions from 1 January 2026. The UK ETS for shipping has been live since 1 July 2026, with its own scope and deadlines (`market-assessment.md`, C).
- **FuelEU Maritime:** grades how dirty a ship's fuel is over a year. A ship above the limit pays a penalty. A ship below it has a surplus it can bank or pool with other ships.
- **CII:** a yearly A to E efficiency grade from the IMO. No fine, but a poor grade hurts chartering and finance.
- **IMO Net-Zero Framework:** a global rule like FuelEU. It is not adopted. The decision was moved to a one-day session on 4 December 2026 ([DNV](https://www.dnv.com/news/2026/imo-mepc-84-revisiting-the-net-zero-framework/), C).

The job is to keep a running ledger of fuel burned, voyages and allowances, and then work out **who pays**. On a time charter the charterer decides where the ship goes and buys the fuel, but the owner's side is the one the regulator bills. BIMCO clauses say how the charterer pays back, usually monthly. The money is large: OceanScore estimates EU ETS costs for the Greek fleet at €837m in 2026 (D, a vendor's own estimate).

The documents involved are noon reports, bunker delivery notes (BDNs), proofs of sustainability for biofuels, the charter party and its ETS and FuelEU clauses, and the monthly settlement statement.

The hard part is not the arithmetic. Disputes are about whether the fuel figures can be trusted, how off-hire periods and FuelEU pools are split, and old charters signed before the clauses existed (`market-assessment.md` section 3, C). Noon-report fuel data is the weakest link ([E9](../../hypotheses.md#e9)).

## Who has it in Greece

- **Roles:** on the owner side, the manager's emissions or performance team; one Greek job title seen is "Performance & Environmental Engineer" ([P7](../../hypotheses.md#p7), E). On the charterer side, the operations or claims team that receives the invoice. Unknown from Greek sources.
- **Company types:** the ETS "shipping company" is by default the ISM DOC holder, usually the Greek manager, even when the ship is on time charter (`reference/greek-software-vendors.md`, C). So the compliance work sits in Piraeus. The invoice audit sits with charterers, and only 4 Athens or Piraeus firms were confirmed to charter ships in ([E5](../../hypotheses.md#e5), C and D).
- **Company size:** the notes disagree. The overview names 10–40 ships as the best target ([X4](../../hypotheses.md#x4), E). `market-assessment.md` names 3–10 ships as the under-served group ([E2](../../hypotheses.md#e2), D). This brief does not pick one.
- **How many:** 572 management companies in Piraeus and Athens run 5,340 ships; 175 run 6–15 ships and 90 run 16 or more ([Naftika Chronika via Mononews, September 2025](https://www.mononews.gr/business/shipping/se-peiraia-kai-athina-leitourgoun-572-naftiliakes-etaireies-pou-diacheirizontai-5-340-ploia-yparchoun-86-monovapores-etaireies), C). Not every ship trades to the EU. How many do is unknown.

## Who pays

- **Sign-off:** unknown. Probably the owner or the technical or operations manager in a family company (E).
- **Spend today:** the allowances themselves, plus verifier fees, plus either a platform subscription, a managed service (Hecla, EmissionLink) or staff time in Excel. No vendor publishes a price ([E7](../../hypotheses.md#e7), E).
- **Willingness to pay:** Greek owners are already buying. OceanScore names Eurotankers, Almi Marine, Eurobulk and Cetus Maritime as customers, and ABS Wavesight names Navios and Navilands (D). For the charterer audit, there is no evidence either way ([E4](../../hypotheses.md#e4), untested).

## What they use today

- **Larger Greek owners and managers:** named platforms. OceanScore, ABS Wavesight and DNV Emissions Connect all list Greek customers (D). Danaos and Metis users may use those vendors' emission modules (D).
- **Smaller owners:** spreadsheets, a verifier-led service, or an ERP module. ZeroNorth and ZERO44 say smaller teams still use spreadsheets, and paid Excel models are sold to them (D). No survey measures this in Greece ([E2](../../hypotheses.md#e2)).
- **Charterers checking invoices:** unknown. The notes found no dedicated tool; LR VERS, DNV Emissions Connect and Veson's "Agreed Rebill" come closest ([E3](../../hypotheses.md#e3), C).

## Competitors

The full map, with more than 20 vendors, is in `market-assessment.md` section 1. This table keeps the ones that matter for the scored idea.

| Vendor | What it does here | Greek presence or customers | Pricing | Source and level |
| --- | --- | --- | --- | --- |
| OceanScore | Owner-side ETS and FuelEU ledger; generates charterer invoices; EUA trading; pooling | Greece office; Eurotankers, Almi Marine, Eurobulk, Cetus Maritime; claims 2,500+ ships and about USD 5m ARR | Quote only | Company press releases, D |
| DNV Emissions Connect | Verified voyage statements shared between owner and charterer | Bernhard Schulte (not Greek) named; DNV has a Piraeus office | Quote only; free trial | [DNV](https://www.dnv.com/services/emissions-connect/), D |
| Veson IMOS | "Agreed Rebill" of emissions costs inside a commercial platform, with DNV data | Used by larger operators | Quote only | Company announcements, D |
| Lloyd's Register VERS | Expert-reviewed per-voyage validation for both sides; claims 70 companies | Not found | Quote only | Company site, D |
| ABS Wavesight | Owner-side ETS and FuelEU reporting | Navios, Navilands | Quote only | Press releases, D |
| Hecla, EmissionLink | Managed compliance desks with a portal | EmissionLink is in Cyprus | Quote only | Company sites, D |
| Siglar Carbon | Neutral EUA statements, aimed at charterers and brokers | Not found | Free ETS analysis | Company site, D |
| Metis, Danaos | ETS and FuelEU modules on top of performance data or an ERP | Greek | Not published | Company sites, D |

No vendor was found that sells a standalone tool for a charterer to check the invoice it receives ([E3](../../hypotheses.md#e3), C). That rests on not finding one.

## Rules and standards

- **EU ETS:** 100% of in-scope emissions from 2026. Allowances for 2025 are due by 30 September 2026 (`regulations.md`, C).
- **UK ETS maritime:** live since 1 July 2026. The first surrender, for 2026 and 2027 together, is due 30 April 2028 (`market-assessment.md`, C).
- **FuelEU Maritime:** first cycle closed in 2026. The target is 2% below the 2020 baseline now and 6% from 2030 (`regulations.md`, C).
- **EU revision proposal, 17 July 2026:** "report once" across MRV, ETS and FuelEU, one "shipping company" definition, and more ship types from 2029. Adoption is targeted for the end of Q1 2027 (`market-assessment.md`, C).
- **CII:** phase 2 of the review runs to about 2028 (C).
- **IMO Net-Zero Framework:** decision at the 4 December 2026 session; earliest entry into force about March 2028 (C).
- **BIMCO clauses:** ETS Allowances Clause for time charters, ETSA for voyage charters, the SHIPMAN ETS clause, the FuelEU Maritime Clause for time charters (2024) and the CII Operations Clause 2022 (`regulations.md`, C).

## Size of the opportunity

This is a guess, not an estimate.

- **Charterer audit (the scored idea):** 4 Greek firms are confirmed to charter ships in, and 4 more have Athens offices ([E5](../../hypotheses.md#e5)). At 4 to 8 customers the Greek market is too small to size. The real market would be charterers abroad, which the notes have not counted.
- **Owner-side ledger, for comparison:** the same method as item 2 gives 4,149 to 4,812 ships in the 265 Greek companies with 6 or more ships. At a guessed EUR 500–1,500 per ship per year, that is about EUR 2.1m–7.2m a year. Not every ship trades to the EU, so the true figure is lower. Incumbents already hold part of it.
- **Not a market size:** OceanScore's €837m is what Greek owners pay in allowances, not what they spend on software.

## Fit for a solo developer

| Question | Answer |
| --- | --- |
| Can I get the data this needs without a partner? | No. An audit needs the owner's statement, the charter party and the fixture dates. The rules and emission factors are public. |
| How much domain expertise does it need, and where would it come from? | Medium. The rules are written down, but voyage scope, off-hire and pool treatment need someone who has settled real invoices, such as a charterer's claims analyst. |
| How long is the sales cycle likely to be? | Unknown. Charterers are larger firms, often abroad, and may already use Veson. |
| Could a first version be built in about three months? | Probably: parse the statement, recompute allowances and scope from the voyage legs, flag differences. `regulations.md` sketches the ledger. |
| What would stop an incumbent from copying it? | Little. Veson, DNV and LR already hold verified data and could add an audit view. Speed is the only moat. |

## Scorecard

Scores are for the charterer-side invoice audit.

| Criterion | Score | Reason | Evidence level |
| --- | --- | --- | --- |
| Pain is real and costly | 3 | Invoices are large and arbitrations have started, but the awards seen so far are small and no charterer has confirmed the pain. | C |
| Buyers are in Greece | 1 | Only 4 firms in Athens or Piraeus are confirmed to charter ships in (E5, weakened). | C |
| Competition leaves room | 3 | No standalone audit tool was found, but Veson, DNV and LR approach the same problem from the data side. | C |
| Buildable by one developer | 4 | The rules are public and the calculation is bounded. It still needs real invoices to test against. | E |
| Reachable through contacts | unknown | Depends on the author's network. | unknown |

If the owner-side ledger were scored instead, "Buyers are in Greece" would rise to about 4, because the Greek DOC-holding manager carries the duty. "Competition leaves room" would fall to about 1, because that market is crowded.

## Hypotheses

[E1](../../hypotheses.md#e1), [E2](../../hypotheses.md#e2), [E3](../../hypotheses.md#e3), [E4](../../hypotheses.md#e4), [E5](../../hypotheses.md#e5), [E6](../../hypotheses.md#e6), [E7](../../hypotheses.md#e7), [E8](../../hypotheses.md#e8), [E9](../../hypotheses.md#e9). Related: [X4](../../hypotheses.md#x4) (target fleet size), [X5](../../hypotheses.md#x5) (Greek companies are mostly owners), [P7](../../hypotheses.md#p7) (who owns performance and emissions data).

## Open questions and who to ask

The eight interviews in `market-assessment.md` under "Recommendations" cover this item in more detail.

- [ ] When you receive an owner's ETS or FuelEU invoice, how do you check it? Have you caught an error? — claims or operations staff at Trafigura's Athens office, Star Bulk or Bluepool.
- [ ] How do you compute and invoice allowances today, and what broke at the April 2026 FuelEU deadline? — emissions lead at a 5–15 ship owner.
- [ ] What share of your clients still send spreadsheets, and where do submissions fail? — a verifier office in Piraeus.
- [ ] How many ETS or FuelEU settlement disputes are you seeing, and what evidence is missing? — a Piraeus marine lawyer or P&I correspondent.
- [ ] What would you pay per ship per year for compliance software? — owner of a 3–10 ship company.

## Sources

- `topics/01-emissions-compliance/market-assessment.md` and its 20 numbered sources — mostly C and D
- `topics/01-emissions-compliance/regulations.md` — C, from memory in parts
- [DNV, MEPC 84 and the Net-Zero Framework](https://www.dnv.com/news/2026/imo-mepc-84-revisiting-the-net-zero-framework/) — C
- [DNV Emissions Connect](https://www.dnv.com/services/emissions-connect/) — D
- `reference/greek-software-vendors.md`, for the DOC holder as the responsible company — C
- [Mononews, Naftika Chronika survey of 572 companies](https://www.mononews.gr/business/shipping/se-peiraia-kai-athina-leitourgoun-572-naftiliakes-etaireies-pou-diacheirizontai-5-340-ploia-yparchoun-86-monovapores-etaireies) — C
- `hypotheses.md`, evidence under E5 and X5 — B to D
