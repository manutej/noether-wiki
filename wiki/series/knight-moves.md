# Knight Moves

The knight graph on an *n*×*n* board. A move is the usual (±1,±2). Scoring rules change by installment: multiply or add the label of the square you land on; reconstruct a path from partial scores; add a third dimension via towers on pentominoes.

In this window:

- [Knight Moves 6](../puzzles/2024-10-knight-moves-6.md) — October 2024. Two corner-to-corner tours scoring exactly 2024.
- [Pent-Up Frustration 3 / Knight Moves 7](../puzzles/2026-07-pent-up-frustration-3-knight-moves-7.md) — July 2026. 3-D knight on a pentomino-tiled board with towers.

CS bridge: path search on a sparse graph with an algebraic scoring monoid. The interesting part is not DFS. It is choosing the monoid and the bound so the search is finite.
