# Item 3: Chartering workflow

Status: draft | Last updated: 2026-09-28 | Overview item: 3 in `docs/overview.md`

This brief is built from `workflow.md` in this folder, `reference/charter-chain.md` and `docs/hypotheses.md`. The competitors were checked on the web on 2026-09-28; the rest has no new research. The scorecard scores one idea: laytime and demurrage calculation plus claims tracking, which `workflow.md` ranks first. It is one row of the mismatch table in `charter-chain.md`, not the whole chartering workflow.

## Summary

When a ship carries cargo on a voyage charter, the contract allows a set time to load and discharge. If the port call takes longer, the charterer pays demurrage; if it is shorter, the owner pays despatch. The calculation is done by hand from port logs, and a claim is lost if it is filed late. The buyer is whoever carries the cargo: often an operator or pool, but also Greek owners that fix their own ships on voyage charters, mostly tanker and gas owners that trade spot. The competition is stronger than the notes assumed. Marcura sells a claims platform with time-bar tracking to 950+ companies and is buying smaller demurrage firms. Cheap laytime calculators publish prices from about $39 a month. Harbor Lab in Athens owns a demurrage product. No vendor names a Greek customer for laytime or claims, and none says it targets small owners. The item is worth interviews with Greek operations staff, but a new tool would need a clear reason to beat Marcura.

## The problem

Chartering runs in four steps: voyage estimate, fixture, voyage (laytime), claims. `workflow.md` describes each one.

The scored idea covers the last two:

1. **Laytime.** The charter party says how much time the charterer may use in port, when that time starts (after the Notice of Readiness and a notice period), and what does not count (rain, Sundays, shifting berth). The port agent sends a Statement of Facts (SOF): a timed log of the port call, usually as a PDF or scan. Someone builds a timeline, decides for each interval whether it counts, and compares the total with the time allowed. The result is demurrage or despatch (see `reference/glossary.md` section 6).
2. **Claims.** The claim pack (charter extract, NOR, SOF, calculation) must reach the counterparty before the **time bar**, often 60–90 days. Tanker charters demand strict document lists. Claims are tracked in Excel across many voyages, and a missed deadline means the money is lost (`workflow.md`, E).

The documents involved are the fixture recap, the charter party with its rider clauses, the NOR, the SOF, pumping logs for tankers, and port holiday calendars.

An operator has a wider version of the problem. It holds a time charter from the owner and a voyage charter to the cargo owner, and the two treat the same event differently. Waiting, rain and despatch can cost it money that neither contract recovers (`reference/charter-chain.md`, E; [C4](../../hypotheses.md#c4)).

## Who has it in Greece

- **Roles:** the operations department or a demurrage analyst calculates laytime; claims staff or accounts chase payment (`workflow.md`, E). Unknown from Greek sources.
- **Company types:** whoever carries cargo under a voyage charter calculates laytime and claims demurrage. That is often an operator or pool, but it can be a Greek owner that fixes its own ships on voyage charters. A head owner whose ships are all on time charter does not calculate laytime ([X5](../../hypotheses.md#x5), B).
- **Evidence of Greek buyers:** in FY2025 SEC filings (B), Star Bulk earned 33% of revenue from voyage charters, run from Maroussi. Imperial Petroleum had 34% of days on spot voyages, StealthGas 18% of revenue and Tsakos 11% of days. Most other listed Greek owners were near zero. Ships in pools have laytime handled by the pool operator. Trafigura's Athens office handles "claims and payments" for its shipping operations ([E5](../../hypotheses.md#e5), D). Bluepool, an Athens panamax pool, also works from Greece.
- **Company size:** unknown. How many private 10–20 ship owners trade on voyage charters is not known.
- **How many:** unknown. The Naftika Chronika survey counts 572 management companies but does not say which trade on voyage charters.

## Who pays

- **Sign-off:** unknown. Probably the head of operations or the owner (E).
- **Spend today:** staff time; Marcura Claims as software or as a managed service ([C5](../../hypotheses.md#c5), D); FD&D cover for disputes; or a commercial platform such as Veson IMOS.
- **Willingness to pay:** unknown. The value is direct: each recovered claim or avoided time bar is cash. Vendors say the sums are large: Marcura puts dry bulk demurrage at $8–10 billion a year, and the insurer ITIC says single claims "routinely run into tens, and sometimes hundreds, of thousands of dollars" ([C2](../../hypotheses.md#c2), C and D). No Greek company has said how much it loses.

## What they use today

- Small and mid-size operators, brokers and trading houses use Outlook and Excel ([C1](../../hypotheses.md#c1), E).
- Larger operators use Veson IMOS, which covers laytime and claims inside a full commercial platform (`reference/greek-software-vendors.md`, D).
- Some outsource demurrage to a specialist service such as Marcura ([C5](../../hypotheses.md#c5), D).
- Greek ERP users may use the laytime module of Danaos's commercial suite (D).
- No vendor names a Greek customer for laytime or claims. Bluepool, an Athens pool, uses Veson IMOS, but the announcement does not say which modules (D).

## Competitors

Checked on the web on 2026-09-28. Most facts come from vendor pages (D). The list in `workflow.md` was from memory and had several errors; the corrections are below the table.

| Vendor | What it does here | Greek presence or customers | Pricing | Source and level |
| --- | --- | --- | --- | --- |
| Marcura Claims (formerly ClaimsHub) | Laytime and demurrage claims platform with time-bar tracking. Sold as self-serve software, with escalation to specialists, or as a managed service. Claims 950+ companies and 20,000+ claims a year. Bought HubSE (February 2025), Shipdem (February 2026) and Fairway Maritime's assets (July 2026). | Athens office (weak source). No Greek customer named. | Not published | [marcura.com](https://marcura.com/demurrage-software), D; [Smart Maritime, Shipdem](https://smartmaritimenetwork.com/2026/02/18/marcura-acquires-shipdem-to-expand-chemical-tanker-claims-capabilities/), C |
| Veson IMOS (Claims module) | Laytime calculator, claims list and time-bar tasks inside the IMOS commercial platform. AI reads emails and SOFs. Not shown as sold on its own. | Office listed in Piraeus. Bluepool (Athens) adopted IMOS in 2021; modules not named. | Not published | [veson.com](https://veson.com/products/imos/claims/), D; [Bluepool release](https://veson.com/news/bluepool-transforms-risk-management-strategy-with-the-veson-imos-platform/), D |
| Harbor Lab | Port-cost platform. Bought DEMeXchange (demurrage calculation and claim packs) and SOFeXchange (digital SOFs) in November 2023. | Athens head office. Named customer is Indian (Great Eastern Shipping). | Not published | [harborlab.com](https://www.harborlab.com/harbor-lab-acquires-sofexchange-demexchange-2/), D; [Cyprus Shipping News](https://cyprusshippingnews.com/2023/12/13/harbor-labs-bold-leap-into-the-future-acquires-sofexchange-and-demexchange-products-from-osiris-in-a-move-to-digitise-statement-of-facts-and-demurrage-claim-processes/), C |
| Danaos | Laytime module in its commercial suite (reversible, averaged, SHEX terms, SOF statement). No claims tracking found. | Greek, founded 1986. No Greek customer named. | Not published | [danaoscy.eu](https://www.danaoscy.eu/laytime-demurrage-calculator/), D |
| Voyager Portal | Demurrage tool for charterers and traders: reads SOFs, calculates laytime, tracks claims. Not aimed at owners. | Not found | Not published | [voyagerportal.com](https://www.voyagerportal.com/features/demurrage/), D |
| Dataloy VMS (Sedna) | Laytime module in a voyage management system. Sedna bought Dataloy in July 2025. | Not found; customers named are Nordic | Not found | [docs.dataloy.com](https://docs.dataloy.com/release-8.22/voyage-management-system/step-by-step-guides/operations/laytime-calculations/maintain-laytime-calculation/tiered-demurrage-despatch-rate), D |
| Softmar (ION Commodities) | Chartering and operations software with laytime and demurrage calculation. Relaunched in September 2025. | Not found | Not published | [iongroup.com](https://iongroup.com/products/commodities/softmar/), D |
| SHINC (GeoServe) | Both parties and brokers negotiate and agree laytime claims online. German. | Not found | Not found | [shinc.io](https://www.shinc.io/), D (search summary only) |
| LaytimeCalculator.com | Standalone online laytime calculator | Not found | $39–$299 a month, published | [laytimecalculator.com](https://laytimecalculator.com/), D |
| Netpas Tramper | Laytime calculator in a distance and voyage package. Korean. | Not found | About $39 a user a month, published | [netpas.net](https://www.netpas.net/order), D |
| Enqlare, Heisenberg, BV Laytime, ClearVoyage, Base | Other calculators or voyage systems with laytime built in | Not found | Not published | Vendor sites, D (search summaries only) |

Corrections to `workflow.md`:

- Marcura's product is now called Marcura Claims; no current product called "MarDem" was found.
- Shipfix is part of Veson since December 2023. It is a chartering email tool, not a laytime product.
- Sea (Sea/ by Maritech) and Signal Ocean handle pre-fixture work and market data. Neither sells laytime or claims tools.
- Shipnet's own site does not mention laytime; it is still unconfirmed.
- A Greek-language search found no Greek laytime vendor other than Harbor Lab's DEMeXchange.

## Rules and standards

- **Charter party forms:** GENCON, NORGRAIN and AMWELSH for dry bulk voyage charters; ASBATANKVOY, SHELLVOY and BPVOY for tankers; NYPE and SHELLTIME for time charters (`reference/charter-chain.md`, E).
- **Tanker laytime** is usually a fixed number of running hours, often 72, with fewer exceptions than dry bulk (`reference/charter-chain.md`, E).
- **Laytime Definitions for Charter Parties 2013**, published jointly by BIMCO, CMI, FONASBA and INTERTANKO, defines the standard terms when a charter adopts them (E, from memory, not checked).
- **Time bars** are set by each charter, often 60–90 days (`workflow.md`, E).
- **ETS and FuelEU clauses** now appear in voyage charters too, so emissions costs become a line in the voyage result (item 1).

## Size of the opportunity

Not estimated. The method would be: Greek companies that carry cargo on voyage charters × voyages per year × a price per voyage or per ship. The first number is unknown. The listed owners above show the buyers exist, but not how many private companies are like them. Outside Greece the market is larger, because operators and traders are based mainly abroad ([X7](../../hypotheses.md#x7), E).

## Fit for a solo developer

| Question | Answer |
| --- | --- |
| Can I get the data this needs without a partner? | No. Real SOFs, recaps and charter parties come only from an operator or owner ([C3](../../hypotheses.md#c3)). Port holiday calendars can be bought or built. |
| How much domain expertise does it need, and where would it come from? | High. Clause interpretation has many edge cases. It needs a former demurrage analyst or operations manager. |
| How long is the sales cycle likely to be? | Unknown. It may be short, because a single recovered claim can pay for the tool. |
| Could a first version be built in about three months? | Probably: extract SOF events with an LLM, have a person confirm them, compute laytime with a fixed rules engine, and track time bars (`workflow.md`). |
| What would stop an incumbent from copying it? | Nothing. Marcura already sells self-serve claims software, and calculators are cheap. A newcomer would need another edge, such as Greek-language support and presence in Piraeus. |

## Scorecard

Scores are for laytime and demurrage calculation plus claims tracking.

| Criterion | Score | Reason | Evidence level |
| --- | --- | --- | --- |
| Pain is real and costly | 3 | Demurrage is large and claims reach hundreds of thousands of dollars, but no Greek company has said how much it loses, and no figure exists on missed time bars. | D |
| Buyers are in Greece | 3 | Some Greek owners, mostly tanker and gas owners, trade spot on voyage charters, and Trafigura has a claims desk in Athens. Private owners are not counted. | D |
| Competition leaves room | 2 | Marcura sells claims tracking to 950+ companies and keeps buying rivals. Calculators start at about $39 a month. Harbor Lab covers demurrage from Athens. No Greek customer is named, which is the only gap seen. | D |
| Buildable by one developer | 3 | The rules engine is bounded, but clause edge cases need an expert and real documents. | E |
| Reachable through contacts | unknown | Depends on the author's network. | unknown |

## Hypotheses

[C1](../../hypotheses.md#c1), [C2](../../hypotheses.md#c2), [C3](../../hypotheses.md#c3), [C4](../../hypotheses.md#c4), [C5](../../hypotheses.md#c5), [C6](../../hypotheses.md#c6). Related: [X5](../../hypotheses.md#x5) (Greek companies are mostly owners), [X7](../../hypotheses.md#x7) (where operators are based), [E5](../../hypotheses.md#e5) (Trafigura's Athens claims desk). The "Tensions between hypotheses" section of `hypotheses.md` explains why item 3 has more Greek buyers than item 1.

## Open questions and who to ask

The questions at the end of `reference/charter-chain.md` cover operators in more detail.

- [ ] Have you lost a demurrage claim to a time bar or missing documents in the last year, and for how much? — operations manager at a Greek owner that trades spot.
- [ ] Who calculates laytime today, with what tool, and how long does one calculation take? — demurrage analyst or operations staff.
- [ ] Do you outsource demurrage, and to whom, at what price? Have you looked at Marcura Claims or Harbor Lab? — operations manager; Marcura's sales team; Harbor Lab's Athens office.
- [ ] How many of your ships trade on voyage charters rather than time charters? — owners of 10–20 ship companies, or Piraeus brokers.
- [ ] Can you share 5–10 real SOFs and recaps to test extraction on? — a design partner.

## Sources

- `topics/03-chartering-workflow/workflow.md` — E, written from memory
- `reference/charter-chain.md` — E, figures marked as unverified
- `reference/greek-software-vendors.md` — C and D
- [Viewpoint Analysis, Maritime Software Options 2026](https://www.viewpointanalysis.com/post/maritime-software-options-2026) — C
- Vendor pages and trade press linked in the Competitors table, checked 2026-09-28 — C and D
- [Marcura, demurrage spreadsheets vs software](https://marcura.com/resources/blog/demurrage-spreadsheets-vs-software) — D
- [ITIC, demurrage documentation](https://www.itic-insure.com/our-publications/intermediary/demurrage-documentation-dont-miss-the-boat-2826/) — C
- `hypotheses.md`, evidence under X5, E5 and "Tensions between hypotheses", including FY2025 SEC filings — B to D
