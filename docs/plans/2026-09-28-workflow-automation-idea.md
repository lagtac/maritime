# Idea: automate parts of the research workflow

Status: idea, not started | Date: 2026-09-28

An idea for later. Nothing here is decided. The workflow it refers to is in `README.md`, under "How the research works".

## The idea

Automate the bookkeeping steps of the research workflow with Claude Code project skills. A project skill is a Markdown file in `.claude/skills/` that you start with a slash command. It needs no code and no new dependencies.

The skills are interactive. They ask the author before every judgment call: each score, each evidence level, each status change. They do the mechanical steps without asking.

## What not to automate

- **The research itself.** The bottleneck is weak evidence, not bookkeeping. Most notes are level D or E, and only level A or B can mark a claim `supported` or `rejected`. Level A needs conversations with people in the sector.
- **The scores and evidence levels.** These are the author's judgment.

## Candidate skills

1. **`/interview-list`** — the most useful one. It collects the "Open questions and who to ask" lists from every `brief.md` into one interview list, grouped by role (for example operations manager, chartering desk). This list is the route to level A evidence.
2. **`/add-evidence <claim ID>`** — the step that repeats most. It adds a dated evidence bullet to `docs/hypotheses.md`, with the source and its level. Then it asks whether the claim's status should change. It refuses `supported` or `rejected` unless the evidence is level A or B.
3. **`/open-item N`** — the mechanical steps for a new item. It creates `docs/topics/NN-<slug>/`, copies `docs/templates/topic-brief.md` to `brief.md`, picks the next free hypothesis ID letter, updates the item's row in `ROADMAP.md`, and runs `markdownlint-cli2 "**/*.md"`. It saves little time, because only four items are left.

## When to pick this up

After the "Not yet defined" questions in `README.md` are answered: when to stop researching an item, how to compare items, and how to get level A evidence. Automating before then fixes the current steps in place, and the skills would need rewriting.

`/interview-list` is the exception. It depends on none of those questions, so it could be built first.
