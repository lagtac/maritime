# Greek maritime software tools and vendors

Sep 27, 2026 · @dimitris chrysomallis

Greek owner-managers buy software in four separate categories: fleet/technical management, emissions compliance, vessel performance, and light commercial and market data. IMOS is a commercial chartering platform and usually sits beside these, not in place of them.

## Context: who buys software in Greek shipping

Greek-owned shipping is the largest national fleet in the world. The Union of Greek Shipowners' 2025–2026 report puts it at nearly 5,800 vessels and over 19% of global tonnage ([UGS, May 2026](https://ugs.gr/en/press-releases/2026/press-release-20260526/)). Clarksons Research data puts it at 17% of world deadweight, with more than a fifth of all tankers, bulkers and LNG carriers ([Master Mariners summary](https://www.mastermariners.org.au/news-international/6815-greek-shipping-holds-17-of-world-fleet-and-61-of-eu-controlled-tonnage)). The two figures differ because they measure different things.

The typical company is a family-controlled owner-manager in Piraeus, Athens or Glyfada, mostly in tramp shipping (dry bulk, tankers, gas). It usually runs its own technical management (crew, maintenance, safety) and its own commercial management. Many ships are chartered out on time charter, where the charterer runs the voyage and pays fuel and port costs.

**Where IMOS fits.** An independent 2026 buyer's guide splits maritime software into three separate disciplines: technical/fleet management, commercial voyage management, and voyage optimisation/performance. It notes that most fleets buy each separately, and that IMOS normally runs alongside a separate technical management system rather than replacing one ([Viewpoint Analysis, Sep 2026](https://www.viewpointanalysis.com/post/maritime-software-options-2026)). IMOS matters most to operators, traders, pools and owners who run their own voyage chartering. For the typical Greek owner-manager the core system is a fleet management suite, with emissions and performance tools next to it.

**Why emissions land on the owner-manager.** Under EU ETS and FuelEU Maritime the responsible "shipping company" is by default the ISM DOC holder, usually the manager, even when the ship is on time charter. Costs are passed to the charterer through the BIMCO ETS clause, but the monitoring plan, annual reporting and verification stay with the manager.

## 1. Technical / fleet management

This is the owner-manager's core system: planned maintenance (PMS), procurement and inventory, crewing, drydock, QHSE/ISM documents and often vessel accounting. Class societies are major vendors here.

| Vendor | Owner / base | Product | What the sources say |
| --- | --- | --- | --- |
| [Danaos Management Consultants](https://danaos.gr/) | Piraeus, founded 1986 | Danaos Web Enterprise | Integrated maritime ERP: accounting, commercial, maintenance, crewing, performance; now adds an AI agent that turns PDF and free-text reports into records ([danaos.gr](https://danaos.gr/)). Around 700 vessels use its apps ([Danaos DMC](https://dmc.danaos-projects.com/)). |
| [Ulysses Systems](https://www.cbinsights.com/company/ulysses-systems) | Piraeus | Task Assistant 4 | Ship management, maintenance planning, procurement, compliance documents ([CB Insights](https://www.cbinsights.com/company/ulysses-systems)). |
| [DNV ShipManager](https://www.viewpointanalysis.com/post/maritime-software-options-2026) | DNV (class society) | ShipManager | Maintenance, procurement, drydock, compliance, linked to DNV class and survey data. |
| [ABS Wavesight](https://www.viewpointanalysis.com/post/maritime-software-options-2026) | ABS (class society) | Nautical Systems (NS Enterprise, formerly NS5) | Full marine ERP; newer browser-based NS-Web modules. |
| [SpecTec AMOS](https://www.viewpointanalysis.com/post/maritime-software-options-2026) | SpecTec, part of Volaris Group | AMOS-X (relaunched 2025) | Maintenance, inventory, procurement; several thousand vessels; lighter on finance. |
| [SERTICA](https://www.viewpointanalysis.com/post/maritime-software-options-2026) | Logimatic | SERTICA | Maintenance, procurement, HSQE, crewing. |
| [Hanseaticsoft](https://www.hellenicshippingnews.com/?p=914304) | Hamburg, part of Lloyd's Register Group | Cloud Fleet Manager | Cloud ship management; LR planned an Athens sales office when it invested ([Digital Ship](https://thedigitalship.com/?p=6505)). |
| [BASS](https://www.mordorintelligence.com/industry-reports/marine-management-software-market) | Norway | BASSnet | Launched cloud-based BASSnet Web 3.0 in January 2025. |
| [MariApps](https://www.marinelink.com/news/maritime/mergers--acquisitions) | Schulte Group | smartPAL product family | Ship-to-shore sync; acquired EffiaSoft (Hyderabad). |
| [Helm Operations](https://www.viewpointanalysis.com/post/maritime-software-options-2026) | Canada | Helm CONNECT | Mainly workboats, tugs, offshore; little relevance to Greek deep-sea fleets. |

Also on the market but not checked for this doc: Star IPS, ShipNet, Ramco Marine, MACS3. Procurement marketplaces (ShipServ, Mespas, Procureship) plug into these systems. Crewing is consolidating too: Ripple Operations bought Norway's AdonisHR ([MarineLink](https://www.marinelink.com/amp/news/maritime/maritime-software)).

## 2. Emissions compliance (CII, EU/UK ETS, FuelEU, MRV/DCS)

These tools collect fuel data, compute CII, EUAs owed and the FuelEU compliance balance, produce verified statements, and support passing ETS costs to charterers. Verifiers (class societies) have an edge because they also sign off the numbers.

| Vendor | Product | What the sources say |
| --- | --- | --- |
| [DNV](https://www.dnv.com/services/emissions-connect/) | Emissions Connect on Veracity | Launched 2023. Covers EU ETS, UK ETS, CII and FuelEU; ingests data in OVD format; issues verified voyage statements; supports pooling optimisation ([DNV](https://www.dnv.com/services/emissions-connect/)). Bernhard Schulte (670+ ships) uses it for ETS and FuelEU ([Net Zero Compare](https://netzerocompare.com/software/dnv-emissions-connect)). |
| [ZeroNorth](https://psgequity.com/portfolio/zeronorth) | ZeroNorth platform | Copenhagen, PSG Equity-backed. Merged with Alpha Ori Technologies (2023) and bought BTS and Prosmar; offers CII analytics and voyage/vessel optimisation ([CB Insights](https://www.cbinsights.com/investor/zeronorth)). Has an Athens office ([job listing](https://jobbank.dk/job/2702467/zeronorth-as/head-of-monetization)). |
| [Danaos](https://dmc.danaos-projects.com/) | Emissions / ESG modules | Built into the Danaos suite, so often the default for existing Danaos users. |
| [Metis](https://www.naftemporiki.gr/english/995954/more-than-150-vessels-greek-controlled-shipping-using-new-metis-system-platform) | METIS platform | Athens; see section 3. Performance data with regulatory and CP reporting on top. |

Other class societies (ABS, BV, LR) and verifiers such as Verifavia also sell reporting tools; they were not checked for this doc. EUA purchases go through brokers, banks or exchanges, and FuelEU pool partners are found through verifiers, brokers and fuel suppliers, not through software alone.

## 3. Performance monitoring and voyage optimisation

On time charter the owner warrants speed and consumption. These tools compare noon reports and sensor data with those warranties, using weather data, to answer performance claims, track hull fouling and improve CII. Greece has several home-grown players, most now owned by larger industrial groups.

| Vendor | Owner / base | What the sources say |
| --- | --- | --- |
| [StormGeo](https://www.alfalaval.com/media/news/investors/2021/alfa-laval-has-completed-the-acquisition-of-stormgeo/) | Bergen; Alfa Laval since June 2021 | Weather routing and fleet monitoring with 24/7 routing experts ([Viewpoint](https://www.viewpointanalysis.com/post/maritime-software-options-2026)). |
| [ZeroNorth](https://www.viewpointanalysis.com/post/maritime-software-options-2026) | Copenhagen | Voyage and vessel optimisation; adding agentic AI (Propel). |
| [Nautilus Labs](https://www.viewpointanalysis.com/post/maritime-software-options-2026) | USA | ML voyage optimisation with a CII package. |
| [DeepSea Technologies](https://naftemporiki.gr/english/1495813/greek-maritime-technology-companies-attracting-investors) | Athens; 100% owned by Nabtesco (Japan) since July 2023 | AI performance monitoring and routing ([CEE Legal Matters](https://ceelegalmatters.com/greece/24033-zepos-yannopoulos-advises-nabtesco-on-acquisition-of-deepsea-technologies)); pitches shared data between owner and charterer. |
| [Metis Cyberspace Technology](https://gcaptain.com/metis-augmented-routing-optimization-puts-weather-routing-into-ship-performance-analytics/) | Athens, founded 2016; controlled by ERMA FIRST | Sensor data collection plus analytics, including a charter-party performance module ([J-L-A](https://www.j-l-a.com/?p=6784)); ownership per [company brochure, 2022](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RW1c96P). |
| [LAROS (Prisma Electronics)](https://nafsgreen.gr/stefanos-chartomatzidis-beyond-data-collection-laros-and-the-new-era-of-predictive-maritime-intelligence/) | Greece | Wireless onboard sensors and performance platform; integrates with other systems rather than replacing them ([Hellenic Shipping News](https://www.hellenicshippingnews.com/?p=325255)). |
| [OrbitMI](https://www.marinelink.com/amp/news/maritime/maritime-software) | USA | Bought Gale Force (voyage optimisation, compliance advisory). |
| DTN weather routing | Sold to ABB in June 2024 | Per a market report ([Mordor Intelligence](https://www.mordorintelligence.com/industry-reports/marine-management-software-market)); not confirmed from a primary source. |

Not checked for this doc: Weathernews, Kongsberg (Vessel Insight), Wärtsilä, Bearing AI.

## 4. Light commercial, port cost and market data

An owner chartering out on time charter needs hire statements, off-hire tracking, market data and port-cost control, not full voyage estimating. Owners doing their own voyage chartering move up to a commercial platform (IMOS or the commercial module of their ERP) or keep estimates in Excel. The data side is consolidating fast.

| Need | Vendor | What the sources say |
| --- | --- | --- |
| TC accounting, hire statements | Danaos commercial and accounting modules | Part of the Danaos ERP ([danaos.gr](https://danaos.gr/)); Excel remains common. |
| Full commercial platform | Veson IMOS | For chartering, voyage economics, laytime and claims; typically beside a technical system ([Viewpoint](https://www.viewpointanalysis.com/post/maritime-software-options-2026)). |
| Market intelligence | Signal Ocean (Signal Group) | Bought AXSMarine (AXSDry, AXSTanker, Alphaliner) in January 2026 ([Xinde Marine News](https://www.xindemarinenews.com/news/2076577459878502401)). |
| AIS and trade data | Kpler | Owns MarineTraffic and FleetMon (2023) and Spire Maritime (closed April 2025, about $241m) ([Hellenic Shipping News](https://www.hellenicshippingnews.com/?p=1086596), [Ship Technology](https://www.ship-technology.com/news/kpler-acquisition-spire-maritime/)). |
| Port costs (PDA/FDA) | Harbor Lab | Athens, founded 2020; checks disbursement accounts against port tariffs; €6.1m seed round in 2022 ([Maritime Executive](https://maritime-executive.com/corporate/harbor-lab-secures-6-1-million-in-seed-funding-to-help-port-expenses)). |

Not checked for this doc: Dataloy, Clarksons, VesselsValue, distance-table vendors (AtoBviaC, Netpas), RightShip.

## 5. Data flows and where a developer fits

This section is analysis, not sourced fact. All four categories run on the same raw data: noon, arrival and departure reports, bunker delivery notes, fuel on board and cargo figures. The ship sends it once; the office often retypes it into several systems.

### Pain points

- The same report goes into the fleet system, the emissions platform and the charterer's portal.
- Reports arrive as Excel attachments or free-text emails. OVD (Operational Vessel Data) is the standard format DNV's platform ingests ([DNV](https://www.dnv.com/services/emissions-connect/)), but many offices don't produce it natively.
- Mixed time zones (ship's time, local, UTC) break laytime, CII and ETS figures.
- Master data doesn't match: vessel names vs IMO numbers, port names vs UN/LOCODE, fuel grade names.
- ETS cost pass-through to charterers is often done in spreadsheets.

### Opportunities, and who is already there

- Parsing emailed reports into clean records. Incumbents are moving in: Danaos now advertises an AI agent that turns unstructured PDFs and free-text reports into system records ([danaos.gr](https://danaos.gr/)).
- Sync layers between fleet system, emissions platform and verifier (OVD in, verified data out).
- Small internal dashboards: CII projection, EUA exposure, performance vs charter party.
- Automating ETS invoices and hire statement lines.

The hard part is sales, not code. The market is consolidating around class societies and funded platforms, and Greek managers usually already pay a large vendor. Integration and cleanup work around existing systems is a more realistic entry point than a new platform.

## Method and limits

- Web research done on 27 September 2026. Every vendor in the tables is linked to the page its facts came from. Vendors named under "not checked" were not verified.
- Many sources are trade press or vendor pages. Vendor claims (vessel counts, savings) are the vendors' own figures.
- No public data shows market share by vendor among Greek managers. Which systems dominate in Greece is not established here; Danaos and Ulysses are Greek-based, and DNV, LR and ZeroNorth have Athens presence.
- The Greek fleet share differs by source: over 19% of tonnage (UGS) vs 17% of deadweight (Clarksons).

## Sources

- [Union of Greek Shipowners, Annual Report 2025–2026 press release](https://ugs.gr/en/press-releases/2026/press-release-20260526/)
- [Greek shipping holds 17% of world fleet (Clarksons data)](https://www.mastermariners.org.au/news-international/6815-greek-shipping-holds-17-of-world-fleet-and-61-of-eu-controlled-tonnage)
- [Viewpoint Analysis, Maritime Software Options 2026](https://www.viewpointanalysis.com/post/maritime-software-options-2026)
- [Danaos Maritime Software](https://danaos.gr/) and [Danaos DMC](https://dmc.danaos-projects.com/)
- [CB Insights: Ulysses Systems](https://www.cbinsights.com/company/ulysses-systems)
- [Hanseaticsoft, part of LR Group](https://www.hellenicshippingnews.com/?p=914304)
- [Mordor Intelligence, marine management software market](https://www.mordorintelligence.com/industry-reports/marine-management-software-market)
- [MarineLink: mergers and acquisitions](https://www.marinelink.com/news/maritime/mergers--acquisitions) and [maritime software news](https://www.marinelink.com/amp/news/maritime/maritime-software)
- [DNV Emissions Connect](https://www.dnv.com/services/emissions-connect/)
- [CB Insights: ZeroNorth](https://www.cbinsights.com/investor/zeronorth) and [PSG Equity: ZeroNorth](https://psgequity.com/portfolio/zeronorth)
- [Alfa Laval completes StormGeo acquisition](https://www.alfalaval.com/media/news/investors/2021/alfa-laval-has-completed-the-acquisition-of-stormgeo/)
- [Nabtesco acquires DeepSea (Naftemporiki)](https://naftemporiki.gr/english/1495813/greek-maritime-technology-companies-attracting-investors)
- [Metis: 150+ Greek-controlled vessels (Naftemporiki)](https://www.naftemporiki.gr/english/995954/more-than-150-vessels-greek-controlled-shipping-using-new-metis-system-platform)
- [LAROS / Prisma Electronics interview](https://nafsgreen.gr/stefanos-chartomatzidis-beyond-data-collection-laros-and-the-new-era-of-predictive-maritime-intelligence/)
- [Signal Ocean acquires AXSMarine](https://www.xindemarinenews.com/news/2076577459878502401)
- [Kpler completes Spire Maritime acquisition](https://www.hellenicshippingnews.com/?p=1086596)
- [Harbor Lab seed round](https://maritime-executive.com/corporate/harbor-lab-secures-6-1-million-in-seed-funding-to-help-port-expenses)
