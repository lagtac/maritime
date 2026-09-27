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

Few Greek companies are pure operators. Most are head owners that charter ships out. Operators and traders are based mainly in Geneva, Singapore, London, Hamburg and Copenhagen.

- **Source:** `reference/greek-market-structure.md`
- **Level:** E
- **Status:** untested
- **How to test:** Ask Piraeus brokers what share of their Greek clients charter ships in.

### X6

Greek managers usually already pay a large vendor. Integration and cleanup work around existing systems is a more realistic entry point than a new platform.

- **Source:** `reference/greek-software-vendors.md`
- **Level:** E
- **Status:** untested
- **How to test:** Ask managers which systems they use and what they retype between them.

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
- **Status:** untested
- **How to test:** Count charterers and operators with a Piraeus office. See the note on E5 and X5 below.

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

- **E5 and X5.** The leading emissions idea sells to charterers and operators. But X5 says most Greek companies are owners, and most operators and traders are based outside Greece. If both hold, the charterer-side tool has few buyers in Piraeus. Test X5 first. The same tension applies to item 3, where the buyer is also an operator.
- **E2 and E1.** Both can be true: the market is crowded for larger owners and still open for small ones. The open question is whether small owners will pay enough (E7).
