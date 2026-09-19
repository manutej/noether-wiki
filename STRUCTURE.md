# STRUCTURE

Assumption: this folder is a markdown wiki plus a JSON catalog, not a codebase.

## Rebuild

```bash
PYTHONPATH=../sheaf-port/src python -m sheaf_port ingest wiki --out out/jane-street
```

Drop `docs/examples/jane-street-puzzles.json` into [stalks-and-sections](https://github.com/manutej/stalks-and-sections) `docs/examples/`.

## Parts

- `data/jane-street/puzzles.json` — one part per puzzle, locator `catalog#<id>`
- `wiki/INDEX.md` and `wiki/puzzles/*.md` — locators `wiki/<page>#heading`
- `skills/sheaf-ingest/SKILL.md` — the reusable procedure

## Observed links only

Edges come from:
- `belongs_to_series` declared in the catalog
- `successor_of` inside a named series
- markdown `[text](path)` in wiki pages
- official Jane Street URLs (`sourced_from`)

No complete graph. No invented "related to" edges.

## Skipped

- Official Jane Street HTML (copyright; link, do not ingest)
- Solution essays (gated in the trainer; not wiki parts)
- `node_modules`, `.git`, binaries
- Embeddings of statement paragraphs
