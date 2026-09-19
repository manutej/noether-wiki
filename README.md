# noether-wiki

Typed wiki for reconnecting working programmers with the mathematics that actual computer science is made of.

This instance indexes **Jane Street monthly puzzles, September 2024 – September 2026** — twenty-five problems. It is an index, a trainer, and a sheaf package. It is not a republication of Jane Street's statements or solutions.

## Live trainer

Open `public/index.html` (or the Vercel deploy of this repo).

- Problems are shown as our short framing plus a link to the official page, where the figures live.
- Solutions stay closed until you log an attempt.
- Random draw prefers unopened problems.
- Progress is a rank on a poset, stored in `localStorage`. Not XP. Not badges.

## Layout

```
data/jane-street/puzzles.json    source catalog (links, images, tags, CS bridge)
data/jane-street/triples.jsonl   observed wiki triples
wiki/                            markdown stalks
skills/sheaf-ingest/             skill: folder → index + lattice + package
docs/examples/                   sheaf graph drop-in for stalks-and-sections
public/index.html                editorial dashboard
```

## Rebuild

```bash
# sheaf-port walker, if you have that repo checked out next door
PYTHONPATH=../sheaf-port/src python -m sheaf_port ingest wiki --out out/jane-street
```

Or follow `skills/sheaf-ingest/SKILL.md`.

## Copyright

Puzzle statements, figures, and official write-ups belong to Jane Street Group, LLC.
Official archive: https://www.janestreet.com/puzzles/archive/
This repo stores URLs, short original framing, and a progress trainer.
