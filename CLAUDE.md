# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

An exploratory research repository. Its goal is to find a niche for a software product that can be sold to Greek maritime companies. It is not a product codebase.

- **The author** is a Greek developer and tech entrepreneur with no background in the maritime sector. The notes are an attempt to get an overview of the industry. Explain shipping terms and mechanisms plainly; do not assume domain knowledge.
- **The notes** come from earlier Claude sessions. They are not verified. That is why most sources are vendor websites and trade press.
- **The focus** is the Greek market and its players: Greek owners, managers, operators, brokers and vendors. When a question has a global answer and a Greek answer, give the Greek one first.
- **Lint:** `markdownlint-cli2 "**/*.md"` checks the Markdown. Its config is `.markdownlint-cli2.jsonc`; line length and table spacing are not checked.
- **Code:** There are no build or test commands. Simulations may be added later to explore specific questions. Any product code will probably move to a separate project.

## Git workflow

This repo does not use the global spec → plan → worktree flow. Commit notes directly on `main` as `docs: <sentence>` (Conventional Commits, no scope). There is no plans index and no test command. The remote is GitHub (`git@github.com:lagtac/maritime.git`), not GitLab, so use `gh` if a remote operation is ever needed. The user pushes.

## Sources

- <https://www.shipuniverse.com/> is the only source the author treats as authoritative so far.
- <https://tradingeconomics.com/commodity/baltic> gives the Baltic Dry Index (a daily price index for dry bulk freight).

Everything else in the notes is a claim to check. Vendor figures (vessel counts, revenue, features) are the vendors' own. When you add a fact, say where it came from. When a better source contradicts a note, say so and name the source.

## Layout of `docs/`

| Path | Holds |
| --- | --- |
| `overview.md` | The research plan: why Greek shipping is tramp shipping (bulk, tankers, gas), the seven pain areas, and possible niches. |
| `hypotheses.md` | Every claim that could change the choice of niche, one section each, with source, evidence level (A to E), status and evidence. |
| `reference/` | Background that applies to every item. |
| `topics/NN-<slug>/` | Research on one item from the overview list. `NN` is the item number. |
| `templates/topic-brief.md` | The template for each item's `brief.md`. |
| `assets/` | Images. `veson-digitalization-infographic.jpg` is from Veson, the vendor of the IMOS commercial platform. |

Reference files:

| File | Covers |
| --- | --- |
| `glossary.md` | Terms and acronyms. Check here before defining a term in a new doc, and add new terms here. |
| `greek-market-structure.md` | Fleet size, family ownership, one-ship companies, where operators are based. |
| `greek-software-vendors.md` | Greek software vendors by category, and the raw data they all share. |
| `players-and-roles.md` | Who the players are, and one way to model them in a database. |
| `charter-chain.md` | Parties, contracts, money and risk along one charter chain. Its figures are marked as unverified. |

## Research workflow

The author works through the numbered list "What Greek tramp owners actually need" in `docs/overview.md`, one item at a time.

| Item | Topic | Folder |
| --- | --- | --- |
| 1 | Emissions compliance | `topics/01-emissions-compliance/`: `regulations.md` (EU ETS, FuelEU, CII, IMO Net-Zero Framework, ledger sketch), `market-assessment.md` (competitors, where a newcomer might enter), `greek-terminology.md` |
| 2 | Vessel performance and noon reports | not started |
| 3 | Chartering workflow | `topics/03-chartering-workflow/`: `workflow.md` (estimate → fixture → laytime → claims, idea for a laytime tool) |
| 4 | Port costs | not started |
| 5 | Crew management | not started |
| 6 | Procurement and technical management | not started |
| 7 | Cybersecurity and connectivity | not started |

When starting an item:

- Create `topics/NN-<slug>/` with lowercase, hyphenated file names.
- Write `brief.md` from `templates/topic-brief.md`. Keep all its headings, including the scorecard, so items can be compared.
- Add the item's claims to `hypotheses.md` with a new ID letter. Each claim is a section with `- **Field:** value` bullets. When research confirms or contradicts a claim, update its status and add the evidence as its usage notes say. Never delete a section.

Items 1 and 3 do not have a `brief.md` yet.

## Working hypotheses in the notes

None of these are decided. They are starting points to test, question or drop. `hypotheses.md` tracks them one by one.

- **Emissions software:** Tools that let owners compute carbon allowances and invoice charterers look crowded (OceanScore, DNV, Veson and others). The notes suggest a tool for charterers that checks the invoices they receive (`market-assessment.md`).
- **Chartering software:** The notes suggest laytime and demurrage calculation plus claims tracking (`workflow.md`).
- **Selling in Greece:** Greek shipping is family-run and buys through personal relationships. The notes suggest finding one design partner, a 10–20 ship owner who shares real data.
- **A tension:** both ideas above sell to charterers and operators, but most Greek companies are ship owners, and most operators are based abroad (hypotheses `X5` and `E5`).
- **Modelling ideas**, if a product gets built:
  - An LLM extracts data from documents, a person confirms it, and a fixed rules engine does the calculations (`workflow.md`).
  - Each company is stored once, and its role (owner, charterer, manager) is stored on the contract or the vessel, not as a company type (`players-and-roles.md`).
  - The emissions ledger adds facts and never edits them, and versions its emission factors and rules by year (`regulations.md`).

## Known problems in the notes

- The notes disagree on when the IMO decides on the Net-Zero Framework. `regulations.md` and `greek-terminology.md` say October 2026. `market-assessment.md` cites sources for a session on 4 December 2026.
- Regulatory dates and vendor positions change often. Check them before relying on them.
