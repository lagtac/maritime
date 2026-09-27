# Hypothesis log

Every claim in the notes that could change which niche to pursue. Each hypothesis has its own section, which says where the claim came from, how strong the evidence is, and how to test it.

Last updated: 2026-09-27

## How to use this log

- Add a section when a note makes a claim that matters for the decision. Head it `### <ID>`, write the claim as its first paragraph, and give it the same `- **Field:** value` bullets as the others. Keep each field on one line.
- Never delete a section. Change its status and add the evidence: an `- **Evidence:**` bullet, with one nested, dated bullet per finding that names its source and level.
- For an overview table, run `md-collapse-sections.py docs/hypotheses.md --key ID --fields Level,Status --body Claim --first-sentence`. It prints the table and does not change the file.
- Source paths are relative to `docs/`.
- IDs use the overview item: `X` = applies to all items, `E` = item 1 (emissions), `C` = item 3 (chartering). New items get new letters.

### Status

| Status | Meaning |
| --- | --- |
| untested | Nobody has checked it. |
| supported | Level A or B evidence agrees with it. |
| weakened | Some evidence goes against it, but not enough to reject it. |
| rejected | Level A or B evidence contradicts it. |

### Evidence levels

| Level | Meaning |
| --- | --- |
| A | First-hand: an interview, real company data, or a document from a real deal. |
| B | Authoritative: the regulation text, an official body (IMO, EU, BIMCO, Union of Greek Shipowners), or shipuniverse.com. |
| C | Independent secondary: trade press, law firm notes, academic papers. |
| D | Vendor claim: a vendor's website or press release about itself or its market. |
| E | AI note with no source, or "from memory". |

## Applies to all items

### X1

Greek shipping is almost all tramp shipping (bulk, tankers, gas). Container-liner standards such as DCSA do not reach Greek owners' systems.

- **Source:** `overview.md`, `reference/greek-market-structure.md`
- **Level:** C
- **Status:** untested
- **How to test:** Read the Union of Greek Shipowners annual report directly.

### X2

Greek shipping buys through personal relationships. Cold SaaS sales do not work.

- **Source:** `overview.md`
- **Level:** E
- **Status:** untested
- **How to test:** Ask 3 or more people in the sector how they last chose a software vendor.

### X3

The best way in is one design partner: a 10–20 ship owner who shares real data for a low price.

- **Source:** `overview.md`
- **Level:** E
- **Status:** untested
- **How to test:** Ask owners whether they would do this, and on what terms.

### X4

Mid-size fleets (10–40 ships) are the best target. Large fleets already bought software.

- **Source:** `overview.md`
- **Level:** E
- **Status:** untested
- **How to test:** Ask owners of each size what they use.

### X5

Few Greek companies are pure operators. Most are head owners that charter ships out. The city list in the original claim moved to X7 on 2026-09-27.

- **Source:** `reference/greek-market-structure.md`
- **Level:** E
- **Status:** supported
- **How to test:** Still open: ask Piraeus brokers what share of their Greek clients charter ships in.
- **Evidence:**
  - 2026-09-27, UGS (B): "Most vessels in the bulk/tramp trades operate under time charter contracts. The timecharterer assumes the commercial operation of the vessel." [UGS, characteristics of the Greek-owned fleet (page from 2022)](https://ugs.gr/en/greek-shipping-and-economy/greek-shipping-and-economy-2022/characteristics-of-the-greek-owned-fleet/)
  - 2026-09-27, SEC annual reports for FY2025 (B, audited company filings): of 22 Greek-managed listed companies, only Costamare Bulkers (19 ships chartered in, 31 owned) and Dorian LPG (6 of 27) charter in more than 10% of their fleet to trade. Star Bulk charters in 7 ships long-term against 136 owned (charter-in days 7.7% of the total). Most other "chartered-in" ships are sale-and-leaseback or bareboat with a purchase option, which is financing. The sample is large listed groups, not small family owners. Filings are at `https://www.sec.gov/Archives/edgar/data/` (for example Star Bulk: `1386716/000095015726000397/sblk-20251231.htm`).
  - 2026-09-27, Petrofin Research (C): 588 Greek shipowning companies in 2024, 295 of them with 1–4 ships. It counts owners only, with no operator split. [Petrofin, Key Developments of Greek Shipping in 2024](https://www.petrofin.gr/wp-content/uploads/2025/09/Key-Developments-of-Greek-Shipping-in-2024-and-2025-Prospects.pdf)
  - 2026-09-27, Hellenic Shipping News (C): Bluepool Trading, an Athens panamax operator and pool, was called "the first dry bulk platform of its kind in Greece" at launch. [Hellenic Shipping News](https://www.hellenicshippingnews.com/bluepool-new-dry-bulk-freight-trader-and-pool-launches/)

### X6

Greek managers usually already pay a large vendor. Integration and cleanup work around existing systems is a more realistic entry point than a new platform.

- **Source:** `reference/greek-software-vendors.md`
- **Level:** E
- **Status:** untested
- **How to test:** Ask managers which systems they use and what they retype between them.

### X7

Operators and traders are based mainly in Geneva, Singapore, London, Hamburg and Copenhagen. Split from X5 on 2026-09-27.

- **Source:** `reference/greek-market-structure.md`
- **Level:** E
- **Status:** untested
- **How to test:** Ask Piraeus brokers which cities their charterers fix from.
- **Evidence:**
  - 2026-09-27, Costamare Bulkers 20-F for FY2025 (B): its chartering desks are in Copenhagen, Hamburg, Singapore and Japan.
  - 2026-09-27, company websites (D): Western Bulk is in Oslo, and Cargill Ocean Transportation in Geneva. No source ranks operator hubs. Oslo and Dubai are missing from the claim, and London has almost no evidence.

## Item 1: Emissions compliance

### E1

Software that lets owners compute ETS/FuelEU costs and invoice charterers is saturated.

- **Source:** `topics/01-emissions-compliance/market-assessment.md`
- **Level:** D
- **Status:** untested
- **How to test:** Ask 5–15 ship owners what they use and whether they are satisfied.

### E2

Small owners (3–10 ships) still handle ETS/FuelEU in spreadsheets.

- **Source:** `topics/01-emissions-compliance/market-assessment.md`
- **Level:** D
- **Status:** untested
- **How to test:** Ask small owners and a verifier office in Piraeus what share of clients send spreadsheets.

### E3

No standalone product lets a charterer check the ETS/FuelEU invoices it receives.

- **Source:** `topics/01-emissions-compliance/market-assessment.md`
- **Level:** C
- **Status:** untested
- **How to test:** Ask charterers what they use. Search again for charterer-side tools.

### E4

Charterers want to check these invoices and suspect errors in them.

- **Source:** `topics/01-emissions-compliance/market-assessment.md`
- **Level:** C
- **Status:** untested
- **How to test:** Interview 2 in `topics/01-emissions-compliance/market-assessment.md`: "How do you check an owner's ETS/FuelEU invoice? Have you caught an error?"

### E5

The buyers of a charterer-side audit tool can be reached in Piraeus.

- **Source:** `topics/01-emissions-compliance/market-assessment.md`
- **Level:** E
- **Status:** weakened
- **How to test:** Threshold set before the search: fewer than 15 Athens or Piraeus firms that take ships on time charter weakens E5, and 30 or more supports it. Still open: ask Trafigura's Athens office, Star Bulk and Bluepool who checks the ETS and FuelEU invoices they receive, and ask Piraeus brokers which foreign charterers fix from Athens.
- **Evidence:**
  - 2026-09-27, desk search (C and D): 8 Athens or Piraeus firms found, below the threshold of 15. Confirmed to charter in (4): Star Bulk (7 long-term ships, Maroussi), Bluepool Trading (panamax pool), M/Maritime (three newbuilds on 5–10-year time charters with purchase options), and Trafigura, whose "Athens office manages a large percentage of Trafigura's shipping operations and shipping-related administration including claims and payments" ([trafigura.com/careers](https://www.trafigura.com/careers/)). Athens office but no proof they charter in (4): Oldendorff Carriers Hellas, Hong Glory Bulk (opened April 2026), Heidmar and Navig8. The last two run pools, which may not receive owners' ETS invoices.
  - 2026-09-27, Costamare Bulkers 20-F for FY2025 (B): the largest Greek-linked charter-in platform fixes from Copenhagen, Hamburg, Singapore and Japan, not Athens, and handed most of its chartered-in ships to Cargill under a cooperation agreement. So it is not a Piraeus buyer.
  - 2026-09-27, Riviera (C): Norden opened an Athens office in January 2025 to charter ships in from Greek owners, and closed it after 15 months. [Riviera](https://www.rivieramm.com/news-content-hub/news-content-hub/norden-winds-down-greek-office-after-15-months-88635)
  - 2026-09-27, not found: an Athens chartering desk for Cargill, Vitol, Glencore, Louis Dreyfus, Bunge, ADM, COFCO or the Scandinavian operators. Several of their sites hide office lists, so this is not proof of absence.

### E6

Disputes over ETS/FuelEU settlement between owners and charterers are rising.

- **Source:** `topics/01-emissions-compliance/market-assessment.md`
- **Level:** C
- **Status:** untested
- **How to test:** Ask a Piraeus marine lawyer or P&I correspondent how many cases they see.

### E7

Small owners are kept out by price and effort, because all major platforms quote prices privately.

- **Source:** `topics/01-emissions-compliance/market-assessment.md`
- **Level:** E
- **Status:** untested
- **How to test:** Ask small owners what they would pay per ship per year.

### E8

Being in Piraeus and supporting Greek is an advantage over foreign vendors.

- **Source:** `topics/01-emissions-compliance/market-assessment.md`
- **Level:** E
- **Status:** untested
- **How to test:** Ask owners whether language or location affected a past software choice.

### E9

Fuel consumption from noon reports is the weakest data in the whole chain. Errors there cause most settlement problems.

- **Source:** `topics/01-emissions-compliance/regulations.md`, `topics/01-emissions-compliance/market-assessment.md`
- **Level:** C
- **Status:** untested
- **How to test:** Ask a verifier where submissions fail most often. Also relevant to item 2.

## Item 3: Chartering workflow

### C1

Small and mid-size operators, brokers and trading houses run chartering in Outlook and Excel.

- **Source:** `topics/03-chartering-workflow/workflow.md`
- **Level:** E
- **Status:** untested
- **How to test:** Ask operators and brokers to show how they track a voyage.

### C2

Laytime and demurrage mistakes, and missed claim deadlines (time bars), cost operators real money each year.

- **Source:** `topics/03-chartering-workflow/workflow.md`
- **Level:** E
- **Status:** untested
- **How to test:** Ask operators whether they lost a claim to a time bar or missing documents last year.

### C3

Statements of facts (SOFs) and recaps arrive by email as PDF or text, so an LLM can extract them.

- **Source:** `topics/03-chartering-workflow/workflow.md`
- **Level:** E
- **Status:** untested
- **How to test:** Collect 5–10 real SOFs and recaps and test extraction on them.

### C4

Operators lose money where the time charter in and the voyage charter out treat the same event differently, and they rarely compare the two after a voyage.

- **Source:** `reference/charter-chain.md`
- **Level:** E
- **Status:** untested
- **How to test:** The questions at the end of `reference/charter-chain.md`.

### C5

Marcura and similar firms already sell demurrage management as an outsourced service.

- **Source:** `topics/03-chartering-workflow/workflow.md`
- **Level:** E
- **Status:** untested
- **How to test:** Check which Greek companies use Marcura, and at what price.

### C6

Operators prefer Excel for voyage estimates because enterprise tools such as Veson IMOS are slow for quick scenarios.

- **Source:** `topics/03-chartering-workflow/workflow.md`
- **Level:** E
- **Status:** untested
- **How to test:** Ask chartering desks how they build an estimate during a negotiation.

## Tensions between hypotheses

- **E5 and X5.** The leading emissions idea sells to charterers and operators. X5 is now supported: most Greek companies are owners that charter their ships out on time charter. E5 is weakened: only 8 candidate firms were found in Athens and Piraeus, and only 4 are confirmed to charter ships in. So the charterer-side tool has few buyers in Piraeus, and would have to be sold abroad or to a handful of local desks (checked 2026-09-27).
- **X5 and item 3.** This tension is weaker for item 3 than for item 1. The laytime buyer is whoever carries cargo under a voyage charter, because that party calculates laytime and claims demurrage. That is often an operator or pool, but it can be a Greek owner that fixes its own ships on voyage charters. In the FY2025 SEC filings, Star Bulk earned 33% of revenue from voyage charters, run from Maroussi. Imperial Petroleum had 34% of days on spot voyages, StealthGas 18% of revenue and Tsakos 11% of days. Most other listed Greek owners were near zero, and ships in pools have laytime handled by the pool operator. So item 3 has some Greek owner buyers, mostly tanker and gas owners that trade spot. How many private 10–20 ship owners trade on voyage charters is unknown.
- **E2 and E1.** Both can be true: the market is crowded for larger owners and still open for small ones. The open question is whether small owners will pay enough (E7).
