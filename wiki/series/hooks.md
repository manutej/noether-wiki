# Hooks

An *n*-hook is an L-shaped region that would be the border of an *n*×*n* square minus the inner *(n-1)*×*(n-1)* square, bent into an L. The classical Jane Street hook puzzle asks you to partition a square into hooks of sizes *n, n-1, …, 1* and fill hook *k* with the digit *k* under extra constraints.

In this window:

- [Hooks 11](../puzzles/2025-09-hooks-11.md) — September 2025. Pentomino overlay + empty-region product.

Related earlier (outside this window): Hooks 10, March 2024.

CS bridge: this is exact cover plus a local-to-global consistency condition. The 2×2 "at least one empty" rule is a local section constraint; the pentomino decomposition is a second sheaf on the same underlying cells. Failure to glue is a wrong hook placement.
