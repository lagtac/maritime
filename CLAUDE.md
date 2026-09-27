# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

An exploratory research repository. Its goal is to find a niche for a software product that can be sold to Greek maritime companies. It is not a product codebase.

- **The author** is a Greek developer and tech entrepreneur with no background in the maritime sector. The notes are an attempt to get an overview of the industry. Explain shipping terms and mechanisms plainly; do not assume domain knowledge.
- **The notes** come from earlier Claude sessions. They are not verified. That is why most sources are vendor websites and trade press.
- **The focus** is the Greek market and its players: Greek owners, managers, operators, brokers and vendors. When a question has a global answer and a Greek answer, give the Greek one first.
- **Code:** There are no build, lint or test commands. Simulations may be added later to explore specific questions. Any product code will probably move to a separate project.

## Git workflow

This repo does not use the global spec → plan → worktree flow. Commit notes directly on `main` as `docs: <sentence>` (Conventional Commits, no scope). There is no plans index and no test command. The remote is GitHub (`git@github.com:lagtac/maritime.git`), not GitLab, so use `gh` if a remote operation is ever needed. The user pushes.

## Sources

- <https://www.shipuniverse.com/> is the only source the author treats as authoritative so far.
- <https://tradingeconomics.com/commodity/baltic> gives the Baltic Dry Index (a daily price index for dry bulk freight).

Everything else in the notes is a claim to check. Vendor figures (vessel counts, revenue, features) are the vendors' own. When you add a fact, say where it came from. When a better source contradicts a note, say so and name the source.

## The documents in `docs/`

The number prefix groups documents by topic. Suggested reading order:

| File | Covers |
| --- | --- |
| `00-maritime-shipping-glossary.md` | Terms and acronyms. Check here before defining a term in a new doc, and add new terms here. |
| `1-Greek-maritime-shipping-overview.md` | Why Greek shipping is tramp shipping (bulk, tankers, gas), not container liners. Seven pain areas and possible niches. |
| `2a-Shipping-emissions-compliance-framework.md` | EU ETS, FuelEU, CII and the IMO Net-Zero Framework (NZF), plus a sketch of an emissions ledger. |
| `2b-Market-Opening-...-Compliance-Product.md` | Competitor map for emissions software and where a newcomer might enter. |
| `2c-...-Greek-terminology.md` | Greek terms for the emissions rules. |
| `3a-Chartering-workflow.md` | Estimate → fixture → laytime → claims, and an idea for a laytime tool. |
| `3b-Charter chain map ....md` | Parties, contracts, money and risk along one charter chain. Its figures are marked as unverified. |
| `4a-Tramp Shipping Players, Roles ....md` | Who the players are, and one way to model them in a database. |
| `5a-Greek maritime market structure and reputation.txt` | Fleet size, family ownership, one-ship companies, where operators are based. |
| `5b-Greek maritime software tools and vendors.md` | Greek software vendors by category, and the raw data they all share. |

`Veson-Digitalization-Infographic.jpg` is a reference image from Veson, the vendor of the IMOS commercial platform.

## Working hypotheses in the notes

None of these are decided. They are starting points to test, question or drop.

- **Emissions software:** Tools that let owners compute carbon allowances and invoice charterers look crowded (OceanScore, DNV, Veson and others). The notes suggest a tool for charterers that checks the invoices they receive. `2b` lists interviews that would confirm or reject this.
- **Chartering software:** The notes suggest laytime and demurrage calculation plus claims tracking (`3a`).
- **Selling in Greece:** Greek shipping is family-run and buys through personal relationships. The notes suggest finding one design partner, a 10–20 ship owner who shares real data.
- **Modelling ideas**, if a product gets built:
  - An LLM extracts data from documents, a person confirms it, and a fixed rules engine does the calculations (`3a`).
  - Each company is stored once, and its role (owner, charterer, manager) is stored on the contract or the vessel, not as a company type (`4a`).
  - The emissions ledger adds facts and never edits them, and versions its emission factors and rules by year (`2a`).

## Known problems in the notes

- The notes disagree on when the IMO decides on the NZF. `2a` and `2c` say October 2026. `2b` cites sources for a session on 4 December 2026.
- Regulatory dates and vendor positions change often. Check them before relying on them.
