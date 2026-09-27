# Tramp Shipping: Players, Roles and How to Model Them

Sep 27, 2026 · @dimitris chrysomallis

## The core idea

In tramp shipping, every contract is a decision about who carries which risk: market price, time, fuel, delay, damage, and the other party not paying. A ship is an expensive asset that earns only when it moves cargo. Cargo owners need goods moved but mostly don't want to own ships. A chain of contracts connects the two.

Shipping splits by how a ship is employed, not by what it carries. **Tramp shipping** has no fixed route or schedule: a ship goes wherever a cargo is, hired per voyage or per period. This is mainly bulkers and tankers. **Liner shipping** runs fixed routes on published schedules and sells space to many shippers; today that is mostly container ships, but also ro-ro and breakbulk services. **Industrial shipping** is a cargo owner running its own fleet for its own cargo, such as a miner moving its ore. This document focuses on tramp, where most of the commercial complexity lives, and most of Greek shipping. The last sections show how the same model extends to the other two.

The document builds one argument. It starts with the players, then the contracts that connect them and the risks each carries. It ends with the practical consequence for software: players are best modelled as **roles in relationships**, not as fixed types of company.

## The players

Each player wants something different from a voyage and fears a different failure. The table lists them by function; later sections show that one company often plays several of these parts.

| Player | What they do | What they want | What they fear |
| --- | --- | --- | --- |
| Registered / head owner | Owns the ship, usually through a one-ship company | Steady hire, rising asset value | Idle ship, falling rates, unpaid hire, big repair bills |
| Ship manager | Runs the ship technically: crew, maintenance, certificates | Management fee, clean safety record | Detentions, accidents, failed inspections |
| Operator (disponent owner) | Charters ships in and employs them; may own few or none | Earn more per day from cargoes than it pays in hire | Paying hire in a falling market, delays it can't pass on |
| Charterer | Hires the ship: trader, miner, oil major, or another operator | Cheap, reliable, compliant transport | Delays, demurrage, cargo damage |
| Commodity trader | Buys and sells the cargo and charters ships to move it | Margin on the commodity; freight is a cost | Demurrage mismatches, freight spikes, sanctions exposure |
| Broker | Matches ships to cargoes and negotiates | Commission, about 1.25% per broker | Deals failing, losing clients |
| Port agent | Handles the port call | Fees, funded in advance | Not being paid |
| Bunker supplier / trader | Sells fuel | Margin, payment | Credit losses, quality claims |
| Stevedores / terminal | Load and discharge cargo | Throughput | Congestion |
| Insurers (P&I, H&M) | Cover liabilities and damage to the ship | Premiums with few claims | Casualties, pollution, sanctions breaches |
| Financier | Funds the ship | Repayment | Ship value falling below the loan |
| Class society / surveyor / vetting | Certify and inspect | Fees, reputation | Approving a ship that then fails |
| Regulators (IMO, EU, flag, port state) | Set and enforce rules | Safety, lower emissions | Non-compliance |

## What a "shipping company" is

"Shipping company" is a loose term. Most often it means a shipowner that owns ships, usually one single-ship company per vessel under a parent group, and either charters them out or operates them itself. Most Greek shipping companies are this type. But the term covers several business models:

| Type | Owns ships? | Core business |
| --- | --- | --- |
| Owner | Yes | Earns hire or freight from its own fleet |
| Owner-operator | Yes, plus chartered-in ships | Mixes own and hired tonnage to serve cargoes |
| Pure operator | No, or very few | Charters ships in and employs them; earns the spread |
| Ship manager | No | Runs ships technically for owners, for a fee |
| Commercial manager / pool | No | Finds employment for other owners' ships |
| Liner company | Owned and chartered | Sells container space on fixed routes |

Regulation adds one more meaning. Under ISM, EU ETS and FuelEU, the "shipping company" is the **DOC holder**: the company responsible for safe operation. That is often the ship manager, not the owner, which decides who must buy emissions allowances.

### The Greek terms

Greek separates ownership from operation more precisely than everyday English. **Πλοιοκτήτης** is the legal owner in the registry. **Εφοπλιστής** comes from *εφοπλίζω*, "to fit out a ship". In Greek maritime law (Κώδικας Ιδιωτικού Ναυτικού Δικαίου) it is whoever exploits the ship for their own account, whether or not they own it. It matches French *armateur* and German *Reeder*.

| Greek term | Meaning | English equivalent |
| --- | --- | --- |
| Πλοιοκτήτης | Legal owner in the registry | Registered owner |
| Εφοπλιστής | Runs the ship for own account | Owner-operator (legal sense) |
| Ναυλωτής | Hires the ship | Charterer |
| Διαχειριστής | Manages the ship for someone else | Ship manager |

When an owner runs its own ship, it is both πλοιοκτήτης and εφοπλιστής, which is why everyday speech blurs the two. Under a bareboat charter, the charterer becomes the εφοπλιστής because it mans and runs the ship. Under a time or voyage charter, the owner usually stays the εφοπλιστής, since it still crews and navigates. In contracts and court cases the distinction matters, because liability follows the εφοπλιστής.

## Contracts and who carries which risk

The contract type decides who pays for time. The four main types run from the owner keeping most of the risk to the owner giving most of it away:

| Contract | Deal | Owner pays | Charterer pays | Time and market risk |
| --- | --- | --- | --- | --- |
| Voyage charter (VC) | Carry cargo A to B for freight per tonne | Ship, crew, fuel, ports | Freight; demurrage if port time exceeds laytime | Owner |
| Contract of affreightment (COA) | Carry a volume over a period, ship not named | As for VC, repeated | As for VC | Owner, who must find ships at future market rates |
| Time charter (TC, TCT) | Hire the ship per day; charterer directs it | Crew, maintenance, insurance (OPEX) | Hire, fuel, ports, canals | Charterer, since idle days still cost hire |
| Bareboat | Charterer takes over the ship entirely | Capital only | Everything else, including crew | Charterer, fully |

Under a voyage charter, time is the owner's problem, except port time beyond laytime, which the charterer pays as **demurrage**. Under a time charter, time is the charterer's problem, except breakdowns and owner faults, which stop hire as **off-hire**. Most disputes are about which of these exceptions applies to a given hour.

## The charter chain and operator economics

The operator earns the spread between what cargo pays and what the ship costs per day. A typical chain: the head owner charters the ship on time charter to an operator at $15k/day; the operator charters it out on a voyage charter to a trader at $22/t and pays the fuel and port costs itself.

&#91;embedded content: charter chain · owner, operator, trader\]

The operator is **long a ship and short a cargo**. It measures each voyage by its time charter equivalent (TCE), then compares TCE with the hire it pays:

```latex
\text{TCE} = \frac{\text{freight} - \text{fuel} - \text{port costs} - \text{commissions}}{\text{voyage days}}
```

If TCE is $18k/day and hire is $15k/day, the operator makes $3k/day. A slow voyage, a fuel price jump, or waiting time the voyage charter doesn't cover can erase that margin. Each link in the chain tries to lock in a spread while pushing risk to the next link.

The operator is also where contract mismatches land. If the time charter in and the voyage charter out word laytime, speed warranties, bunker clauses or emissions clauses differently, the operator pays the difference. That is why operators are the heaviest users of estimate, operations and claims software such as IMOS.

## The life of one voyage

A voyage runs in seven stages, and its financial result is often settled months after the ship has sailed on.

1. **Position.** The ship will be open at a place and date. Brokers circulate it, and cargo lists come back.
2. **Estimate.** Model the voyage: distances, speed, fuel, port costs, days, and the resulting TCE.
3. **Negotiate.** Offer, counter, firm offer, then subjects such as board or receiver approval.
4. **Fixture.** Subjects are lifted and the deal binds. The broker sends a recap, and the charter party (CP) is drafted from it.
5. **Execution.** Voyage instructions go to the master, fuel is bought, agents are appointed. The ship arrives, tenders Notice of Readiness, loads, gets bills of lading, sails, and sends daily noon reports.
6. **Settlement.** Freight or hire invoices, the laytime calculation (demurrage or despatch), final port costs, and emissions costs passed through.
7. **Claims.** Demurrage, performance (more fuel burned than warranted), cargo shortage or damage, off-hire disputes.

## Where the risk sits

Time is the biggest silent cost, but eight kinds of risk run through every voyage:

| Risk | What goes wrong | Main protection |
| --- | --- | --- |
| Market | Freight rates can double or halve within months; a TC-in without cargo cover, or a COA without ships, is exposed | FFAs, bunker swaps, matched contracts |
| Time | Congestion, weather, strikes, canal queues, failed hold inspections | Laytime and off-hire wording in the CP |
| Fuel | Price swings, off-spec deliveries, ship burning more than warranted | Bunker hedges, fuel testing, performance claims |
| Counterparty | Unpaid hire or freight, insolvency along the chain | Liens, withdrawal clauses, credit limits |
| Operational | Collision, grounding, breakdown, cargo liquefaction, piracy, war zones | H&M and P&I insurance, vetting |
| Documents | Bills of lading are documents of title; releasing cargo without the original makes the owner liable | Letters of indemnity, strict B/L procedures |
| Regulatory | EU ETS allowances, FuelEU penalties, poor CII ratings, sanctions breaches, port state detentions | Emissions clauses, sanctions screening, compliance tooling |
| Asset | Ship values fall with rates, squeezing indebted owners | Conservative leverage, period charters |

## Roles, not companies

The players are roles, not companies. One entity can hold several roles, and each role can be held by a separate entity.

**Fully integrated.** A Greek group owns a ship through a single-ship company, manages it through an in-house management company, and charters it in and out through its own operating arm. It holds every role, spread across several legal entities in one group.

**Fully separated.** A bank finances the ship, a one-ship company owns it, a third-party manager runs it, an operator charters it in, a trader charters it from the operator, and the trader's buyer receives the cargo. Six unrelated parties.

**In between.** Most real cases mix the two. An owner-operator charters in extra ships when it has more cargo than fleet. A trader charters ships for its own cargo and relets spare capacity. An operator with no ships holds TC-in contracts against voyage or COA commitments.

Two consequences follow:

- **Roles are per contract.** In the chain above, the same operator is charterer on the TC and owner on the VC. The role depends on which side of that contract you are on.
- **The legal entity matters more than the brand.** A group is usually many companies. Liability, sanctions exposure, emissions responsibility and payment risk attach to the specific entity on the contract or in the registry, not to the group name.

## Modelling players in software

Store each legal entity once, and store its role on the relationship it takes part in, never as a fixed attribute of the company.

### Why a company type column fails

The naive model gives each company a type:

```sql
companies (id, name, type)  -- 'owner' | 'charterer' | 'operator' ...
```

It breaks immediately. An operator is charterer on its TC-in and owner on its VC-out. A trader is a charterer today and an owner tomorrow after a relet. A group is not one company: one entity signs the contract, another is on the registry, a third manages the ship.

### The model

Separate who the entity is, what the relationship is, and what role the entity plays in it. The schema below is written from the operator's point of view, as a single-company system like an IMOS install. Each contract is stored from our side, so its kind and direction set both our role and the counterparty's.

```sql
groups               (id, name)
counterparties       (id, legal_name, lei, country, group_id, credit_limit)
vessels              (id, imo, name, type, dwt, gt, built, flag, scrubber)
vessel_roles         (vessel_id, counterparty_id, role, valid_from, valid_to)
                     -- role: 'registered_owner' | 'technical_manager' | 'doc_holder'
                     --       | 'pi_club' | 'hm_insurer' | 'mortgagee' | 'class'
contracts            (id, kind, direction, counterparty_id, cp_date, cp_form, status, currency)
                     -- kind: 'TC' | 'CARGO' | 'COA' ; direction: 'in' | 'out'
contract_commissions (contract_id, counterparty_id, type, pct)   -- addcomm, brokerage
tc_terms             (contract_id, vessel_id, delivery_range, redelivery_range, min_days, max_days, ...)
                     -- only TC contracts name a ship; cargo contracts are often fixed with the ship TBN
```

| Contract | Our role | Counterparty's role |
| --- | --- | --- |
| TC in | Charterer | Owner |
| TC out | Owner | Charterer |
| Cargo in | Owner (carrier) | Charterer |
| Cargo out | Charterer | Owner (carrier) |

In the chain above, the operator's system holds two contracts: a TC in with the head owner as counterparty, and a cargo in with the trader as counterparty. The operator itself is not a counterparty; it is the system's own company. Brokers on either contract sit in `contract_commissions` with their percentage.

### The multi-party alternative

A platform serving many companies, such as a broker's system or a marketplace, cannot store contracts from one side. It stores each contract once, neutrally, and records every party with its role:

```sql
contract_parties (contract_id, counterparty_id, role, commission_pct)
                 -- role: 'owner' | 'charterer' | 'broker' | 'guarantor'
```

"In" and "out" are then derived from which side the viewing company is on. Guarantors fit naturally here; in the operator model they need their own table (e.g. `contract_guarantees`) if required.

### Where each player attaches

Not every role belongs to a charter contract. Some attach to the vessel with dates, some to a port call or fuel purchase, and regulators are not counterparties at all:

| Player | Role attaches to | Stored as |
| --- | --- | --- |
| Registered owner | Vessel, dated | `vessel_roles.registered_owner` |
| Ship manager | Vessel, dated, backed by a management contract | `vessel_roles.technical_manager`, `doc_holder` |
| Operator | Contract | The system's own company; its role follows the contract's direction |
| Charterer | Contract | `counterparty on a cargo-in or TC-out contract` |
| Commodity trader | Contract and cargo | counterparty on a cargo contract; shipper or receiver on the B/L |
| Broker | Contract | `contract_commissions` with commission |
| Port agent | Port call | `port_calls.agent_id` |
| Bunker supplier | Fuel purchase | `bunker_stems.supplier_id` |
| Surveyor | Survey event | `surveys.surveyor_id` |
| Insurers, financier, class | Vessel, dated | `vessel_roles` |
| Regulators | Nothing | Reference data: flag state, ETS authority, port state regime |

### What this buys

- **Group exposure.** Sum what all entities in a group owe, even when invoices go to different legal entities.
- **Sanctions screening.** Screen the legal entity and its group, not a trading name.
- **Emissions responsibility.** ETS and FuelEU costs belong to the DOC holder on the voyage date: a dated lookup in `vessel_roles`.
- **History.** A sale or a new manager adds `vessel_roles` rows; past voyages still point to the right parties.

IMOS follows the same idea: one address book, with types or roles assigned per counterparty and per contract.

## Beyond tramp: industrial and liner shipping

The same principle covers the other two models; only the set of relationships changes.

### Industrial shipping fits as-is

The cargo owner holds several roles through its own group entities. A miner's shipowning subsidiary is `registered_owner` and its management company is `technical_manager` in `vessel_roles`. There is often an intra-group time charter from the shipowning subsidiary to the trading entity, since group companies contract formally for tax and liability reasons. The same group then appears as shipper, and often as receiver.

No new objects are needed. The `group_id` link shows that the "owner" and the "charterer" are one economic party, which matters for exposure and for separating internal from external P&L.

### Liner shipping fits upstream and adds objects downstream

Chartering ships in is identical to tramp. A non-operating owner, such as Costamare or Danaos, time-charters a container ship to a liner company such as Maersk or MSC: a `TC` contract with owner and charterer roles, plus the usual `vessel_roles`.

Selling space is different. There is no charter per cargo: one sailing carries thousands of bookings from hundreds of customers, and carriers share space on each other's ships. That needs objects tramp doesn't have:

| New object | What it is | Roles on it |
| --- | --- | --- |
| Service / route | A fixed loop of ports, e.g. Asia to North Europe weekly | operator, alliance partners |
| Sailing | One rotation of a service by a specific ship | vessel, operator |
| Vessel sharing / slot charter agreement | Carriers share space on each other's ships | slot provider, slot user |
| Booking | Space reserved for containers on a sailing | shipper, forwarder, consignee, notify party |
| Container | The box itself, tracked across moves | owner or lessor, current user |
| Service contract | Negotiated rate for a customer's volume over a period | carrier, customer |

For a tramp-operator scope, the liner objects can be left out entirely.

## Summary

Tramp shipping is a market for renting ships by the day or the tonne. Money is made or lost in the gap between the agreed price and what the voyage actually cost in time, fuel and claims. The players are functions that companies take on per contract, so software should model legal entities once and attach roles to the relationships they enter.

The model extends beyond tramp: industrial shipping needs nothing new, and liner shipping adds objects for selling space while reusing the tramp model for chartering ships in.
