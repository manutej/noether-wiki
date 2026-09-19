---
name: sheaf-ingest
description: >-
  Take a folder, repo, wiki, or knowledge base and build a typed index of its
  parts, a lattice you can open, and a reusable package so the next folder
  uses the same structure. Extended here for a puzzle corpus: each puzzle is a
  part, series/technique/structure are typed fields, official URLs are the only
  allowed external edges. Use when the user says "ingest this wiki", "create a
  sheaf from this catalog", "index Jane Street puzzles", or "build a lattice
  knowledge base." Do not invent links. Do not ingest copyrighted solution essays.
---

# sheaf-ingest

The product sentence:

> Take this folder / repo / knowledge base. Build a typed index. Draw it as a lattice. Leave a structure you can run on the next folder.

## What you emit (always these four)

| User said | File | What it is |
|---|---|---|
| create a sheaf | `index` / bound parts | parts with locators + typed fields + observed links only |
| lattice knowledge base | `lattice.json` / `docs/examples/<id>.json` | drop into stalks-and-sections `docs/examples/` |
| reusable structure | `domain.package.yaml` | what a part is, shared fields, how links are observed |
| repeatable | `STRUCTURE.md` | rebuild command + what was skipped |

## Puzzle-corpus grain

When the folder is a puzzle wiki (this repo):

1. One part per puzzle. Locator: `catalog#<id>` or `wiki/puzzles/<id>.md#statement`.
2. Typed fields: `{page, title, year_month, series, technique, structure}`.
3. Prose (`cs_bridge`, `statement_excerpt`) is evidence, never a field and never a part.
4. Links only if observed: `belongs_to_series`, `successor_of` in the same series, markdown links, `sourced_from` Jane Street.
5. Do not pull official solution HTML into the index. Store `solution_url` as a field on the part.
6. Images: store the official index URL as `figure_source`. Do not invent `.png` paths.

## Procedure

1. Infer kind in one line (here: markdown wiki + JSON catalog).
2. Walk parts with locators you can open. Skip `.git`, `node_modules`, binaries, official mirrored HTML.
3. Walk overlaps only with evidence. No complete graph.
4. Write the four files. `residualMeaning` is one domain sentence.
5. Tell the user how to point the same `domain.package.yaml` at a sibling corpus (IBM Ponder This, Project Euler, Advent of Code theoretical days).

### Speedups

```bash
PYTHONPATH=../sheaf-port/src python -m sheaf_port ingest wiki --out out/jane-street
```

TypeScript monorepo path lives in stalks-and-sections: `npm run sheaf:ingest`.

## MUST NOT

- Treat a paragraph or embedding as a part
- Invent related-to edges so the lattice looks connected
- Fill sections with random numbers
- Dump Jane Street solution text into the wiki
- Ask the user questions — infer grain and proceed

## Done when

- Two locators can be opened and the edge between them has evidence
- `domain.package.yaml` applied to a sibling folder yields the same field names
- `lattice.json` has a one-sentence `residualMeaning`
- `STRUCTURE.md` lists what was skipped
