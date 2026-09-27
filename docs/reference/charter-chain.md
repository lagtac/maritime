# Charter chain map: parties, contracts, money, risk

Sep 27, 2026 · @dimitris chrysomallis

## Purpose

The operator sits in the middle of the charter chain, holds two contracts per voyage, and carries the market and mismatch risk between them. This map lays out who the parties are, which contracts link them, where money flows, and who carries which risk, so it can be checked against a real operator before picking a product.

Focus segment: small and mid-size Greek tramp operators (dry bulk and tankers). Figures and examples are from general knowledge and not verified against sources; treat them as approximate.

## Parties

Only the cargo owner owns cargo; everyone else sells ships, transport or services.

| Party | Owns ships | Charters ships in | Owns cargo | Role in the chain |
| --- | --- | --- | --- | --- |
| Head owner | Yes | No | No | Top of the chain. Lets ships out on time charter, earns hire. |
| Owner-operator | Yes | Yes | No | Runs own ships plus chartered-in ships, sells transport. |
| Charter-in operator | Few or none | Yes | No | Hires ships in, fixes cargoes or relets. Lives on the spread. |
| Cargo owner (charterer) | Sometimes | Yes | Yes | Trader, miner, refiner, industrial buyer. Needs goods moved. |
| Shipbroker | No | No | No | Negotiates fixtures, sends the recap, earns commission (about 1.25% per broker). |
| Port agent | No | No | No | Handles the port call, issues the SOF and disbursement accounts. |
| Ship manager | No | No | No | Runs crew and maintenance for the owner. Often the ISM DOC holder, so often the ETS/FuelEU shipping company. |

One company can play several roles. An operator is a charterer toward the head owner and an owner toward the cargo side, on the same voyage.

## Chain diagram

&#91;embedded content: charter chain · 4 parties, 3 contracts\]

Each link is a separate contract with its own terms. The operator is the only party with a contract on both sides of the same voyage, so any difference between the two lands on it. Brokers sit on each link (commission) and agents sit at each port call; they are left out of the picture.

## Contracts

The operator typically sits on a time charter going in and a voyage charter or COA going out; the two use different forms and are priced differently.

| Contract | Between | Priced as | Who pays fuel and port costs | Common forms | Key terms for the operator |
| --- | --- | --- | --- | --- | --- |
| Time charter (TC) | Owner and operator | Hire, $/day | Operator | NYPE, BALTIME | Delivery/redelivery, speed and consumption warranty, off-hire, bunkers on delivery/redelivery, ETS/FuelEU clauses |
| Trip time charter (TCT) | Owner and operator | Hire, $/day, one trip | Operator | NYPE | Same as TC, for one voyage |
| Voyage charter (VC) | Operator and cargo owner | Freight, $/tonne or lumpsum | Operator | GENCON, NORGRAIN, AMWELSH | Laycan, laytime, demurrage/despatch, freight payment terms |
| COA | Operator and cargo owner | Freight per shipment | Operator | GENCON-based | Volume, number of shipments, nomination rules |
| Relet (TC out) | Operator and another charterer | Hire, $/day | The new charterer | NYPE | Mirror of the TC in, at a higher rate |
| Sales contract | Seller and buyer of the goods | Commodity price | Depends on Incoterm | FOB, CFR, CIF | Its own laytime and demurrage terms |

The recap fixes the main terms for each contract; the formal charter party is drafted later from it.

Tankers use the same contract types with different forms and pricing:

| Item | Dry bulk | Tankers |
| --- | --- | --- |
| Voyage charter forms | GENCON, NORGRAIN, AMWELSH | ASBATANKVOY, SHELLVOY, BPVOY |
| Time charter forms | NYPE, BALTIME | SHELLTIME, BPTIME |
| Freight quoted as | $/tonne or lumpsum | Worldscale points (a % of a flat rate per route) |
| Laytime basis | Load/discharge rate per day, many exceptions | Fixed total hours (often 72 running hours), fewer exceptions |
| Charterer approval | RightShip rating | Oil-major vetting (SIRE inspections) |

## Money flows

On a TC-in / VC-out voyage the operator pays hire, fuel and port costs, and earns freight; everything else is an adjustment on one side or the other.

| Item | Operator pays | Operator receives | Based on |
| --- | --- | --- | --- |
| Hire | Owner, 15 days in advance | From relet charterer, if relet | Hire statement |
| Freight | Sub-contracted carrier, if VC in | Cargo owner | Freight invoice, B/L quantity |
| Demurrage | None to the owner; port time is already paid as hire | Cargo owner, if laytime exceeded | SOF, NOR, laytime calculation |
| Despatch | Cargo owner, if cargo work finishes early | None | Laytime calculation |
| Bunkers | Suppliers; owner for fuel on board at delivery | Owner for fuel on board at redelivery | BDNs, on/off-hire surveys |
| Port costs | Agents (PDA advance, FDA settlement) | Owner, for owners' items | Disbursement accounts |
| Canal dues | Canal authority, via agent | None | Canal tonnage |
| Emissions (EU ETS, FuelEU) | Owner or ship manager, via pass-through clause | Cargo owner, only if the VC says so | Verified emissions per voyage |
| Commissions | Brokers, address commission | None | Percentage of hire or freight |
| Off-hire, performance claims | None | Owner (hire deducted) | Noon reports, CP warranties |

On a time charter the operator bears waiting time directly through hire, so demurrage from the cargo side is its main way to recover time lost in port.

## Risks by party

The operator carries the most freight-market and mismatch risk per dollar of capital; the owner carries asset risk and the cargo owner carries commodity price risk.

| Risk | Head owner | Operator | Cargo owner |
| --- | --- | --- | --- |
| Freight market | Low while chartered out at fixed hire | High: fixed hire in, market freight out | Medium: freight is one cost line |
| Contract mismatch | Low | High: two contracts per voyage with different terms | Medium: CP vs sales contract demurrage |
| Counterparty | Charterer fails to pay hire | Both sides: owner default and charterer non-payment | Operator or seller default |
| Bunker price | None on TC | High unless hedged or passed on | Indirect, via freight |
| Emissions cost | Pays first as shipping company, recovers via clause | Absorbs whatever its VC does not pass on | Pays if its CP passes it on |
| Asset value and running costs | High: ship value, debt, OPEX | None on chartered-in ships | None |
| Commodity price | None | None | High |

Tools operators use against these: FFAs for freight, bunker swaps for fuel, matching contract terms, counterparty credit checks. Small operators often manage these in Excel or not at all.

## Operator mismatch points

Money leaks wherever the TC-in and the VC-out treat the same event differently. Each row is one event seen through both contracts.

| Event | Under the TC in (vs owner) | Under the VC out (vs cargo owner) | How the operator loses |
| --- | --- | --- | --- |
| Waiting at anchorage | Hire keeps running | Counts only after NOR and turn time, minus exceptions | Waiting before laytime starts is unrecovered |
| Rain, strikes, holidays in port | Hire keeps running | Often excepted from laytime (SHEX, WWD) | Excepted time is paid as hire, not recovered |
| Cargo work finishes early | Nothing changes | Operator pays despatch | Despatch paid while hire still runs |
| Ship slower or burns more than warranted | Performance claim against owner | Voyage takes longer, costs more fuel | Claim needs noon-report evidence; often settled low |
| Breakdown | Off-hire, hire stops | Laytime may still run, or cargo owner claims delay | Off-hire deduction smaller than the knock-on costs |
| EU ETS and FuelEU costs | Owner passes them on under the ETS/FuelEU clause | Recovered only if the VC has a matching clause | Cost absorbed on older or silent fixtures |
| Time bars | Owner's claims have their own deadlines | Demurrage claim must be filed within the CP time bar (often 60 to 90 days) | Missed deadline = claim lost |

Tanker-specific mismatch points on top of the rows above:

| Event | Under the TC in (vs owner) | Under the VC out (vs cargo owner) | How the operator loses |
| --- | --- | --- | --- |
| Slow discharge pumping | Pumping warranty claim against owner, if in the TC | Terminal blames the ship; time may not count as laytime | Time lost at hire unless the pumping logs prove the ship performed |
| Weather or strike delays | Hire keeps running | Tanker forms often count them at half demurrage | Half the time is unrecovered |
| Cargo shortage (outturn vs B/L) | Owner liable only beyond the transit-loss tolerance | Cargo owner claims against freight | Claim deducted from freight, recovery from owner uncertain |
| Tank cleaning and heating | Time and fuel at operator's cost | Paid only if the VC prices them in | Absorbed when last and next cargo don't fit |
| Demurrage documents | None | Strict document lists and short time bars (often 90 days) | Claim rejected for a missing pumping log or NOR |

The product question for operators: can one view per voyage put both contracts side by side and show where each dollar leaked? Laytime and demurrage is one row of this table, not the whole problem.

## Worked example

Four days of unrecovered port time cut the operator's profit on this voyage by about a fifth. Numbers are illustrative, not market data.

Setup: a Supramax chartered in on a trip time charter at $14,000/day, fixed out on a voyage charter carrying 55,000 t of grain at $25/t. Planned voyage: 40 days.

| Line | As estimated (USD) | With 4 days unrecovered waiting (USD) |
| --- | --- | --- |
| Freight earned (55,000 t × $25) | 1,375,000 | 1,375,000 |
| Commissions (3.75%) | −51,563 | −51,563 |
| Bunkers (600 t × $600, plus 12 t in port) | −360,000 | −367,200 |
| Port costs | −120,000 | −120,000 |
| Hire (40 or 44 days × $14,000) | −560,000 | −616,000 |
| Operator profit | 283,437 | 220,237 |

The waiting falls in time the VC excludes from laytime (for example rain under SHEX terms), so no demurrage is recovered, while hire and port fuel keep running. The same pattern applies to an ETS cost the VC does not pass on: it comes straight off the spread.

## Questions to validate with operators

The aim is to confirm the map and find the mismatch rows that cost the most.

- [ ] What share of your voyages are on chartered-in ships vs your own?
- [ ] Do you compare the TC-in and the VC-out for the same voyage after it closes? Where: IMOS, another system, Excel, nowhere?
- [ ] Which mismatch rows above cost you most per year: waiting time, weather exceptions, despatch, performance, off-hire, emissions, time bars?
- [ ] Have you lost a demurrage or performance claim to a time bar or missing documents in the last year?
- [ ] How do you pass EU ETS and FuelEU costs to cargo owners on voyage charters, if at all?
- [ ] Who in the office owns the voyage result after fixing: chartering, operations or accounts?
- [ ] What would make you pay for a tool here, and what do you use today instead?
- [ ] Is anything in the chain diagram wrong for how you work?

- [ ] For tanker operators: how often are demurrage claims cut for pumping performance, half-demurrage events or missing documents?
