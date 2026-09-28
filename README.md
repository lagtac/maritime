# Greek maritime research

Research notes to find a software niche that can be sold to Greek maritime companies. This is not a product codebase.

The notes come from earlier AI sessions and are not verified. Treat every fact as a claim to check until a better source confirms it.

## Where things are

| Path | Holds |
| --- | --- |
| `docs/overview.md` | The work queue: why Greek shipping is tramp shipping, the 7 pain areas, and possible niches. |
| `docs/hypotheses.md` | Every claim that could change the choice of niche, with its evidence and status. |
| `docs/topics/NN-<slug>/` | The research on one pain area. `NN` is its number in the overview list. |
| `docs/templates/topic-brief.md` | The template for each topic's `brief.md`. |
| `docs/reference/` | Background for all topics: glossary, market structure, vendors, players, the charter chain. |
| `docs/assets/` | Images. |

## Progress

`ROADMAP.md` holds the state of the research: which items are started, which follow-up tasks are open, and the decisions made so far. The niche ideas and their status are in `docs/hypotheses.md`. This file repeats neither, so it cannot go out of date.

## Modelling ideas

These are ideas for a product, if one gets built. They are not decided.

- An LLM extracts data from documents, a person confirms it, and a fixed rules engine does the calculations (`docs/topics/03-chartering-workflow/workflow.md`).
- Each company is stored once. Its role (owner, charterer, manager) is stored on the contract or the vessel, not as a company type (`docs/reference/players-and-roles.md`).
- The emissions ledger adds facts and never edits them. It versions its emission factors and rules by year (`docs/topics/01-emissions-compliance/regulations.md`).

## How the research works

Study one pain area at a time. Write it up in the same format as the others. Move every claim that matters into the hypothesis log, where evidence can confirm or reject it. At the end, compare the scorecards and pick a niche.

### Working on one item

1. **Open the item.** Create `docs/topics/NN-<slug>/` with lowercase, hyphenated file names. Copy `docs/templates/topic-brief.md` to `brief.md` in that folder.
2. **Fill the brief.** Answer every heading. Write "unknown" rather than delete a heading, so briefs stay comparable. Deep material can go in extra files next to the brief.
3. **Tag every claim with an evidence level** (see below).
4. **Log the key claims.** A claim that could change which niche you pick goes into `docs/hypotheses.md`. It gets an ID that starts with the item's letter. The brief links to the ID and does not copy its status.
5. **Score the item.** Fill the scorecard: five criteria, each scored 1 to 5. Each score names the weakest evidence level behind it, which shows how much to trust it.
6. **Write the summary last.** Then list the open questions, with the role of the person who could answer each one.
7. **Update the shared files.** Add new terms to `docs/reference/glossary.md`. Update the item's row in `ROADMAP.md`. Add a follow-up task there when you find a problem in the notes.

### Testing a claim

Claims live in `docs/hypotheses.md`, one section each. Its "How to use this log" section has the exact format.

- When you find evidence, add a dated bullet under the claim's **Evidence** field. Name the source and its level.
- Then set the status: `untested`, `supported`, `weakened` or `rejected`.
- Never delete a claim. A rejected claim records why an idea was dropped.

ID letters: `X` applies to all items, `E` is item 1, `P` is item 2, `C` is item 3. A new item gets a new letter.

### Evidence levels

| Level | Meaning |
| --- | --- |
| A | First-hand: an interview, real company data, or a document from a real deal. |
| B | Authoritative: regulation text, an official body (IMO, EU, BIMCO, Union of Greek Shipowners), or shipuniverse.com. |
| C | Independent secondary: trade press, law firm notes, academic papers. |
| D | Vendor claim: a vendor's website or press release about itself. |
| E | An AI note with no source, or "from memory". |

Most notes today are level D or E. Only A and B evidence can mark a claim `supported` or `rejected`.

## Sources

- <https://www.shipuniverse.com/> is the only source treated as authoritative so far.
- <https://tradingeconomics.com/commodity/baltic> gives the Baltic Dry Index, a daily price index for dry bulk freight.

When you add a fact, say where it came from. When a better source contradicts a note, say so and name the source.

## Not yet defined

The workflow above does not yet say how to reach a decision. These are open:

- **When to stop researching an item.** For example: once every scorecard row has evidence at level C or better.
- **How to compare items.** For example: whether one score of 1 rules an item out, or only the total counts.
- **How to get level A evidence.** It needs conversations with people in the sector. The "who to ask" questions sit in each brief, and nothing gathers them into one interview list yet.

## Conventions

- Lint the Markdown with `markdownlint-cli2 "**/*.md"`. The config is `.markdownlint-cli2.jsonc`.
- Commit directly on `main` as `docs: <sentence>`, following [Conventional Commits](https://www.conventionalcommits.org/).
- `CLAUDE.md` holds the rules for Claude Code sessions. It holds no research state: progress lives in `ROADMAP.md`, and claim statuses live in `docs/hypotheses.md`. When a workflow rule changes, change it in both files.
