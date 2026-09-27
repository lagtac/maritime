# Greek maritime shipping industry and opportunities for tech entrepreneurs

Greece controls the largest fleet in the world (~20% of global tonnage, ~60% of the EU's), but it's tramp shipping: bulk carriers, tankers, LNG/LPG carriers. DCSA is a container-liner standard. Greek owners in containers (Danaos, Costamare, Capital, Euroseas, Navios) are lessors: they charter the ship to Maersk or MSC, who run the cargo side. Booking, eBL, Track & Trace don't touch a Greek owner's systems. Only Port Call/JIT and the reefer/IoT work overlap, and even those go through the charterer.

So if you want to build for Greek shipping, the standards that matter are BIMCO (charter parties, eBL for bulk), IMO/EU emissions rules, and class societies, not DCSA. The DCSA opportunities I listed are real, but their customers are forwarders and liners in Rotterdam, Hamburg, Singapore, not Piraeus.

**What Greek tramp owners actually need (and pay for)**

1. Emissions compliance. EU ETS for shipping (phased in from 2024), FuelEU Maritime (2025), CII/EEXI ratings, IMO net-zero framework. Every ship needs a running ledger of fuel, voyage, carbon allowances, and who pays (owner vs. charterer under the charter party). This is spreadsheet hell in most offices right now. Mid-size fleets (10–40 ships) are the sweet spot; the big ones already bought something.
2. Vessel performance and noon reports. Sensor data, fuel consumption, hull fouling, speed optimization. Crowded (DeepSea, Metis, Signal), but crowded with premium products.
3. Chartering workflow: fixture recaps, laytime/demurrage calculation, voyage estimation, claims. Still email + Excel in a lot of offices.
4. Port costs. Disbursement accounts, agent invoices. Harbor Lab is the proof: it raised €14.7M in a Series A led by Atomico by attacking a costly, document-heavy process with international customers.
5. Crew management, payroll, certificates, training records, port-state-control prep.
6. Procurement and spare parts, and the whole technical-management stack (planned maintenance, dry-dock planning).
7. Cybersecurity and connectivity (IMO cyber rules, Starlink on ships changed everything: ships now have real bandwidth, which opens up shipboard SaaS that was impossible three years ago).

**The ecosystem you'd be entering**

- Signal Ocean is the flagship. It has since acquired AXSMarine, a well-known provider of vessel and cargo tracking tools. Signal also runs a corporate VC arm.
- DeepSea Technologies was acquired by Nabtesco (Japan). MarineTraffic (Greek-founded) was acquired by Kpler earlier.
- Roughly 54 Greek maritime-tech startups, eight funded and four at Series A or later, per one 2026 count.
- Investors: Signal Ventures (strategic), VentureFriends, Big Pi, plus global maritime funds like Motion Ventures.
- Posidonia (June, biennial, just happened in 2026) is where you meet every owner in the country in one week.

**How to actually get a customer**

Shipping in Greece runs on relationships and family-owned companies. The buyer is usually the technical manager, operations manager, or the owner's son who came back from an MBA. Cold SaaS sales don't work; a warm intro from a ship manager, a broker, or a class society does. Best entry is a design partner: one 10–20 ship owner who lets you build against their real data in exchange for a cheap/free deal.

**What's still open, in my view**

- ETS/FuelEU cost allocation and settlement between owner and charterer (a legal-plus-accounting problem, thin competition).
- "Starlink-native" shipboard tools: things that assume the ship is online (crew welfare, remote inspections, live PMS sync).
- Small-owner ERP: the 3–8 ship owners that are too small for Danaos/Veson and still run on Excel.
- Data plumbing: normalizing noon reports, sensor data, and AIS into one clean feed that other vendors can build on. Unsexy, sticky.
- Ship finance and insurance data rooms: banks and P&I clubs re-key the same vessel data endlessly.

