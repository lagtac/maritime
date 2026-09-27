# Item 2: Vessel performance and noon reports

Status: draft | Last updated: 2026-09-28 | Overview item: 2 in `docs/overview.md`

## Summary

On a time charter the owner promises a speed and a fuel consumption. When the ship misses them, the charterer deducts money from hire in a performance claim, and the owner must defend it. Most Greek owners hire their ships out on time charter (X5). So, unlike the leading ideas for items 1 and 3, the buyer here is the Greek owner in Piraeus. General performance monitoring is already sold to mid-size and large Greek fleets by Greek and foreign vendors, and noon-report capture tools are crowded. The possible opening is narrower: helping owners defend performance claims with clean, well-organised ship records. Nobody has yet shown how often these claims happen or what they cost, so the item is worth testing in interviews but not yet worth building.

## The problem

Every day at noon, the ship sends a **noon report**: position, speed, distance, weather, fuel used and fuel left (see `reference/glossary.md`). The office uses it for three jobs:

1. **Performance claims.** The time charter warrants a speed and consumption "about" a figure, usually in good weather (up to Beaufort 4 and Douglas sea state 3 in NYPE 2015). The charterer often hires a weather-routing company to analyse the voyage. If that report says the ship was slow or burned too much fuel, the charterer deducts the loss from hire. The owner then has to show, from the deck logs and noon reports, that the ship performed or that the weather or currents explain the gap. Arbitrators mostly use the **good weather method**: they judge performance on good-weather days and apply the result to the whole voyage. Source: [West P&I defence guide](https://www.westpandi.com/getattachment/72c4277d-d592-47d5-bb3a-a68da7215f9a/defence-guide_speed_consumption_4pp_v2_lr.pdf) (C).
2. **Technical performance.** Tracking hull fouling (marine growth that slows the ship) and engine condition, to decide when to clean the hull or service the engine.
3. **Emissions reporting.** The same fuel figures feed IMO DCS, EU MRV, EU ETS, FuelEU and CII (item 1).

Claims turn on the quality of the evidence. Tribunals usually prefer the deck logs to routing data. But owners lose when their logs contradict themselves or when they do not produce them (London Arbitration 5/26). Charterers lose when their routing report ignores the charter's own rules, such as how currents are treated (London Arbitration 4/26). Sources are in [P2](../../hypotheses.md#p2).

The data is noisy. A 2013 UCL study found noon-report fuel figures with standard errors of 1–8% on tankers, about the size of the 5% "about" allowance ([Aldous et al.](https://discovery.ucl.ac.uk/1413453/1/Aldous%20et%20al..pdf), C). Ship's time changes make some report periods 23 or 25 hours long.

## Who has it in Greece

- **Roles:** unknown from Greek sources. Outside Greece, claims are handled by the operations department or a marine superintendent, with the FD&D club and outside experts ([P7](../../hypotheses.md#p7), E).
- **Company types:** head owners and managers whose ships are on time charter. The Union of Greek Shipowners says most Greek bulk and tramp ships work on time charter (B, see [X5](../../hypotheses.md#x5)).
- **Company size:** every size that uses time charters. Named Greek customers of monitoring vendors are all mid-size or large.
- **How many:** 572 management companies in Piraeus and Athens run 5,340 ships of 1,000 gt or more. 175 of them run 6–15 ships and 90 run 16 or more ([Naftika Chronika via Mononews, September 2025](https://www.mononews.gr/business/shipping/se-peiraia-kai-athina-leitourgoun-572-naftiliakes-etaireies-pou-diacheirizontai-5-340-ploia-yparchoun-86-monovapores-etaireies), C). How many of them face performance claims each year is unknown.

## Who pays

- **Sign-off:** unknown. Probably the owner or the operations manager in a family company (E).
- **Spend today:** the FD&D cover of the owner's P&I club pays for legal defence. Owners also hire weather-routing firms or consultants. Speed Claim (Istanbul) charges 15% of the reduction it wins, the only published price found ([speedclaim.net](https://speedclaim.net/), D).
- **The club may be the payer:** if the owner's FD&D cover already pays for expert performance analysis, owners may not pay for a tool themselves. Unknown; see the open questions.
- **Willingness to pay:** unknown. A search summary says Britannia settles about 95% of its defence cases within the first USD 7,500 of costs. If true, most claims are small (E, not checked).

## What they use today

- **Noon reports:** "more than 70% of vessels" still send one manual noon report a day, per a vendor-backed report with no method given (D). No Greek figure was found on email, Excel or digital forms.
- **Monitoring:** larger Greek owners use performance platforms: TMS Group uses Ascenz Marorka on 130+ ships, Laskaridis uses Metis and LAROS, Pantheon Tankers uses LAROS, and Seanergy used DeepSea (D).
- **Claims:** FD&D club, weather-routing firms (StormGeo, AWT, Weathernews), and consultants such as Oceanroute (Voula) or Speed Claim (Istanbul) (D).

## Competitors

| Vendor | What it does here | Greek presence or customers | Pricing | Source and level |
| --- | --- | --- | --- | --- |
| Metis (ERMA FIRST) | Sensor data and performance analytics, charter-party module | Athens; Laskaridis; claims 150+ Greek-controlled ships | Not published | [metis.tech](https://www.metis.tech/news/), D |
| LAROS (Prisma Electronics) | Wireless sensors and performance platform | Greek; Laskaridis, Pantheon Tankers; claims 700+ ships | Not published | [laros.gr](https://www.laros.gr/), D |
| DeepSea (Nabtesco) | AI performance monitoring and voyage optimisation | Athens; Seanergy (2021) | Not published | [Offshore Energy](https://www.offshore-energy.biz/seanergy-cuts-fuel-by-up-to-12pct-with-deepsea-ai-platform/), C |
| Ascenz Marorka (GTT) | Performance platform | TMS Group, whole fleet of 130+ ships (2025) | Not published | [GTT](https://www.gtt.fr/news/ascenz-marorka-gtts-smart-shipping-arm-equip-tms-groups-entire-fleet-its-smart-shipping), D |
| Weathernews (WNI) | Routing; OPA audits performance against the charter for owners and charterers | Greek office since 2016; Iolcos testimonial | Not published | [weathernews.com](https://global.weathernews.com/your-industry/shipping/opa/), D |
| ZeroNorth | Optimisation and vessel reporting | Piraeus office since 2021; no named Greek customer | Custom quote | [Seatrade](https://www.seatrade-maritime.com/maritime-technology/maersk-tankers-spin-off-zeronorth-opens-greek-office-to-support-maritime-digitalisation), C |
| StormGeo (Alfa Laval) | Routing, s-Insight performance and claims support | No named Greek customer | Not published | [stormgeo.com](https://stormgeo.com/insights/transka-tankers-optimizes-fleet-performance-with-stormgeo-s-s-insight), D |
| Kongsberg Vessel Insight | Sensor data to cloud, app marketplace | Piraeus office; Propulsion Analytics (Piraeus) sells apps on it | Not published | [Safety4Sea](https://safety4sea.com/kongsberg-maritime-opens-new-office-in-greece/), C |
| Danaos | ERP with a performance module and an AI parser for PDF and free-text reports | Piraeus, founded 1986 | Not published | [danaos.gr](https://danaos.gr/), D. Its size is disputed: `reference/greek-software-vendors.md` says about 700 vessels; a search summary says 650+ clients and 6,500+ vessels. Not resolved: the site shows no figures to a plain download. |
| OrbitMI, Nautilus Labs, Wärtsilä, NAPA, Bearing AI | Performance and voyage optimisation | OrbitMI has a Greek office; Nautilus has a Greek agent; no named Greek customers | Not published | Company sites, D |
| Veson, ZeroNorth, VesselReport, Gelectric, Neptune Zero | Digital noon-report forms or parsers | Neptune Zero is Greek, claims 150+ ships | Not published | Company sites, D |
| Speed Claim, Oceanroute | Claim analysis: Speed Claim for owners, Oceanroute neutral | Oceanroute in Voula; Speed Claim in Istanbul | Speed Claim: 15% of the reduction won | Company sites, D |

The overview lists Signal as a performance competitor. That is wrong: Signal Ocean sells chartering and market data. Its noon-report "energy monitoring" is written for its own pool partners and was not found for sale ([Signal Ocean platform](https://www.thesignalgroup.com/signal-ocean/platform), D).

## Rules and standards

- **NYPE 2015, Clause 12:** a continuing speed and consumption warranty in good weather, up to Beaufort 4 and Douglas sea state 3. Disputes over the deck logs go to an independent expert (BIMCO notes via [SMF](https://www.smf.com.sg/wp-content/uploads/2021/12/22-document-nype-2015-explanatory-notes.pdf), C).
- **BIMCO CII Operations Clause 2022:** keeps the speed and consumption warranty, and obliges owners to give charterers fuel and distance data ([BIMCO](https://www.bimco.org/contractual-affairs/bimco-clauses/current-clauses/cii-operations-clause-2022/), B).
- **BIMCO Hull Fouling Clause 2019:** after agreed idle time, fouling risk moves to the charterer and the warranty is suspended until the hull is cleaned ([West P&I](https://www.westpandi.com/news-and-resources/news/bimco-new-hull-fouling-clause-for-time-charter-par/), C).
- **IMO DCS amendments:** from 1 January 2026, ships record fuel per consumer (main engines, auxiliary engines, boilers) and transport work. First report due in early 2027 ([Bureau Veritas](https://marine-offshore.bureauveritas.com/newsroom/marpol-annex-vi-application-amendments-inclusion-data-transport-work-and-enhanced), C). This raises the detail the noon report must carry.
- **EU "report once":** the July 2026 ETS revision proposal makes the MRV report the single source for MRV, ETS and FuelEU, from 2029 if adopted (trade press, C).
- **CII review:** phase 2 runs to 2028 (C). **IMO Net-Zero Framework:** decision at a session on 4 December 2026 ([DNV](https://www.dnv.com/news/2026/imo-mepc-84-revisiting-the-net-zero-framework/), C).
- **ISO 19030:** the standard for measuring hull and propeller performance. Not researched.

## Size of the opportunity

This is a guess, not an estimate.

- **Method:** Greek management companies with 6 or more ships × ships per company × a price per ship per year.
- **Companies:** 265 companies run 6 or more ships (175 with 6–15 and 90 with 16 or more, Naftika Chronika, C).
- **Ships:** the survey counts 5,340 ships in all. The other 307 companies run up to 5 ships each: 86 run one ship, and 221 run 2 to 5. So they run between 528 ships (86 + 221 × 2) and 1,191 ships (86 + 221 × 5). That leaves 4,149 to 4,812 ships for the 265 larger companies.
- **Price:** EUR 500–1,500 per ship per year for a claim-defence tool. This is a guess; no vendor publishes a price.
- **Result:** about EUR 2.1m–7.2m a year for the Greek market (4,149 × 500 to 4,812 × 1,500). It is a guess, because the price is.
- **Check against claims:** if most claims settle for small sums (P1), owners will not pay per ship. A fee per claim, like Speed Claim's 15%, may fit better.

## Fit for a solo developer

| Question | Answer |
| --- | --- |
| Can I get the data this needs without a partner? | No. Real deck logs, noon reports and charter parties come only from an owner. Weather and current data can be bought or taken from public models such as Copernicus. |
| How much domain expertise does it need, and where would it come from? | A lot. The legal method (good weather method, "about" allowances, currents) needs a former operations manager, master mariner or claims handler. |
| How long is the sales cycle likely to be? | Unknown. It may be short if one lost claim pays for the tool, but family firms buy through relationships (X2). |
| Could a first version be built in about three months? | Probably: parse noon reports and logs, apply the charter's good-weather rules, flag gaps, produce a defence file. Weather reconstruction is the hard part. |
| What would stop an incumbent from copying it? | Little. Weathernews and StormGeo already analyse claims, and Metis has a charter-party module. Speed and Greek presence are the only moats. |

## Scorecard

| Criterion | Score | Reason | Evidence level |
| --- | --- | --- | --- |
| Pain is real and costly | 3 | Clubs call claims common and single claims reach USD 450,000, but there are no frequency figures and most may be small. | E |
| Buyers are in Greece | 4 | Greek owners hire ships out on time charter, so they are the ones who defend claims. Who buys inside the company is unknown. | E |
| Competition leaves room | 2 | Monitoring and noon-report capture are crowded. Owner-side claim defence looks thinner, but that rests on not finding a product. | D |
| Buildable by one developer | 3 | The software is modest, but it needs real owner data and a domain expert on the legal method. | E |
| Reachable through contacts | unknown | Depends on the author's network. | unknown |

## Hypotheses

[P1](../../hypotheses.md#p1), [P2](../../hypotheses.md#p2), [P3](../../hypotheses.md#p3), [P4](../../hypotheses.md#p4), [P5](../../hypotheses.md#p5), [P6](../../hypotheses.md#p6), [P7](../../hypotheses.md#p7). Related: [X5](../../hypotheses.md#x5) (owners charter out), [X6](../../hypotheses.md#x6) (integration work), [E9](../../hypotheses.md#e9) (noon-report fuel data is the weakest link).

The idea of turning noon reports, sensor data and AIS into one clean feed already appears in `overview.md` ("Data plumbing") and in `topics/01-emissions-compliance/market-assessment.md` section 4(d). It is not repeated as a P claim.

## Open questions and who to ask

- [ ] How many performance claims did you receive last year, for how much, and how did they settle? — operations manager at a Greek owner.
- [ ] Who handled the last claim, and who approved the spending? — operations manager or owner.
- [ ] Why do owners lose performance claims? Would better records have changed the result? — FD&D claims handler, Piraeus shipping lawyer.
- [ ] Does your FD&D cover pay for expert performance analysis, and do you ever pay for it yourself? — owner's claims manager, P&I club in Piraeus.
- [ ] How do your ships send noon reports today: email, Excel, a digital form, or sensors? — technical manager at a small owner.
- [ ] What does a routing firm charge for a claim analysis? — Weathernews or StormGeo Athens office.

## Sources

- [West P&I, speed and consumption defence guide](https://www.westpandi.com/getattachment/72c4277d-d592-47d5-bb3a-a68da7215f9a/defence-guide_speed_consumption_4pp_v2_lr.pdf) — C
- [Steamship Mutual, Speed and Performance FAQs, June 2026](https://www.steamshipmutual.com/publications/articles/speed-and-performance-faqs) — C
- [BIMCO NYPE 2015 explanatory notes, via SMF](https://www.smf.com.sg/wp-content/uploads/2021/12/22-document-nype-2015-explanatory-notes.pdf) — C
- [BIMCO CII Operations Clause 2022](https://www.bimco.org/contractual-affairs/bimco-clauses/current-clauses/cii-operations-clause-2022/) — B
- [West P&I on the BIMCO Hull Fouling Clause](https://www.westpandi.com/news-and-resources/news/bimco-new-hull-fouling-clause-for-time-charter-par/) — C
- [Lester Aldridge, London Arbitration 7/25](https://www.lesteraldridge.com/blog/marine/vessel-under-performance-claim-in-time-charters-a-closer-look-at-london-arbitration-7-25/) — C
- [Tank Voyager, London Arbitration 5/26](https://www.tankvoyager.com/london-arbitration-5-26/) — C
- [EGA Legal, London Arbitration 4/26](https://www.egalegal.com/case-summaries/london-arbitration-4/26) — C
- [Aldous et al., UCL, 2013](https://discovery.ucl.ac.uk/1413453/1/Aldous%20et%20al..pdf) — C
- [Safety4Sea, Danelec noon-report figure](https://safety4sea.com/danelec-over-70-of-ships-still-rely-on-once-daily-noon-reports/) — D
- [Bureau Veritas, IMO DCS amendments](https://marine-offshore.bureauveritas.com/newsroom/marpol-annex-vi-application-amendments-inclusion-data-transport-work-and-enhanced) — C
- [DNV, MEPC 84 and the Net-Zero Framework](https://www.dnv.com/news/2026/imo-mepc-84-revisiting-the-net-zero-framework/) — C
- [Mononews, Naftika Chronika survey of 572 companies](https://www.mononews.gr/business/shipping/se-peiraia-kai-athina-leitourgoun-572-naftiliakes-etaireies-pou-diacheirizontai-5-340-ploia-yparchoun-86-monovapores-etaireies) — C
- [e-nautilia.gr, Neptune Zero](https://e-nautilia.gr/i-neptune-zero-sti-lista-thetius-top-150-gia-to-2026/) — C
- Vendor sites and press releases linked in the Competitors table — D
