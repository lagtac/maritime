# Item 3: Chartering workflow

Status: draft | Last updated: 2026-09-28 | Overview item: 3 in `docs/overview.md`

This brief is built from `workflow.md` in this folder, `reference/charter-chain.md` and `docs/hypotheses.md`. No new research was done for it. The scorecard scores one idea: laytime and demurrage calculation plus claims tracking, which `workflow.md` ranks first. It is one row of the mismatch table in `charter-chain.md`, not the whole chartering workflow.

## Summary

When a ship carries cargo on a voyage charter, the contract allows a set time to load and discharge. If the port call takes longer, the charterer pays demurrage; if it is shorter, the owner pays despatch. The calculation is done by hand from port logs, and a claim is lost if it is filed late. The buyer is whoever carries the cargo: often an operator or pool, but also Greek owners that fix their own ships on voyage charters, mostly tanker and gas owners that trade spot. Veson IMOS and Marcura already sell this, but the notes list them from memory, so the competition has not been checked. The item is worth a proper competitor search and interviews with Greek operations staff before any building.

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
- **Spend today:** staff time; an outsourced demurrage service such as Marcura's ([C5](../../hypotheses.md#c5), E); FD&D cover for disputes; or a commercial platform such as Veson IMOS.
- **Willingness to pay:** unknown. The value is direct: each recovered claim or avoided time bar is cash. But nobody has yet said how much they lose ([C2](../../hypotheses.md#c2), E).

## What they use today

- Small and mid-size operators, brokers and trading houses use Outlook and Excel ([C1](../../hypotheses.md#c1), E).
- Larger operators use Veson IMOS, which covers laytime and claims inside a full commercial platform (`reference/greek-software-vendors.md`, D).
- Some outsource demurrage to a specialist service ([C5](../../hypotheses.md#c5), E).
- Greek ERP users may use the commercial module of Danaos (D).

## Competitors

Every row except Veson IMOS and Danaos comes from `workflow.md`, which says its list is from memory. None has been checked. That makes this the weakest section of the brief.

| Vendor | What it does here | Greek presence or customers | Pricing | Source and level |
| --- | --- | --- | --- | --- |
| Veson IMOS | Full commercial platform: estimates, operations, laytime, claims | Used by larger operators; no Greek customer named in the notes | Quote only | [Viewpoint Analysis](https://www.viewpointanalysis.com/post/maritime-software-options-2026), C |
| Marcura (MarDem and others) | Demurrage management, often as an outsourced service | Not checked | Not checked | `workflow.md`, E |
| Dataloy, Shipnet, Softmar | Operations and ERP systems with commercial modules | Not checked | Not checked | `workflow.md`, E |
| Danaos | ERP with commercial and accounting modules | Piraeus, founded 1986 | Not published | [danaos.gr](https://danaos.gr/), D |
| Shipfix, Sea, Voyager Portal | Fixture data, email parsing, voyage collaboration | Not checked | Not checked | `workflow.md`, E |
| Signal Ocean | Market data and chartering tools; bought AXSMarine in January 2026 | Athens | Not published | `reference/greek-software-vendors.md`, C |

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
| What would stop an incumbent from copying it? | Veson already covers laytime inside IMOS. The gap would be price and ease of use for firms too small for IMOS. |

## Scorecard

Scores are for laytime and demurrage calculation plus claims tracking.

| Criterion | Score | Reason | Evidence level |
| --- | --- | --- | --- |
| Pain is real and costly | 3 | Demurrage is cash, and missed time bars lose claims outright, but no one has said how much they lose each year. | E |
| Buyers are in Greece | 3 | Some Greek owners, mostly tanker and gas owners, trade spot on voyage charters, and Trafigura has a claims desk in Athens. Private owners are not counted. | D |
| Competition leaves room | 3 | Veson and Marcura cover this, but the whole competitor list is from memory and unchecked. | E |
| Buildable by one developer | 3 | The rules engine is bounded, but clause edge cases need an expert and real documents. | E |
| Reachable through contacts | unknown | Depends on the author's network. | unknown |

## Hypotheses

[C1](../../hypotheses.md#c1), [C2](../../hypotheses.md#c2), [C3](../../hypotheses.md#c3), [C4](../../hypotheses.md#c4), [C5](../../hypotheses.md#c5), [C6](../../hypotheses.md#c6). Related: [X5](../../hypotheses.md#x5) (Greek companies are mostly owners), [X7](../../hypotheses.md#x7) (where operators are based), [E5](../../hypotheses.md#e5) (Trafigura's Athens claims desk). The "Tensions between hypotheses" section of `hypotheses.md` explains why item 3 has more Greek buyers than item 1.

## Open questions and who to ask

The questions at the end of `reference/charter-chain.md` cover operators in more detail.

- [ ] Have you lost a demurrage claim to a time bar or missing documents in the last year, and for how much? — operations manager at a Greek owner that trades spot.
- [ ] Who calculates laytime today, with what tool, and how long does one calculation take? — demurrage analyst or operations staff.
- [ ] Do you outsource demurrage, and to whom, at what price? — operations manager; Marcura's sales team.
- [ ] How many of your ships trade on voyage charters rather than time charters? — owners of 10–20 ship companies, or Piraeus brokers.
- [ ] Can you share 5–10 real SOFs and recaps to test extraction on? — a design partner.

## Sources

- `topics/03-chartering-workflow/workflow.md` — E, written from memory
- `reference/charter-chain.md` — E, figures marked as unverified
- `reference/greek-software-vendors.md` — C and D
- [Viewpoint Analysis, Maritime Software Options 2026](https://www.viewpointanalysis.com/post/maritime-software-options-2026) — C
- `hypotheses.md`, evidence under X5, E5 and "Tensions between hypotheses", including FY2025 SEC filings — B to D
