# Robot series

Jane Street's recurring robot-sport problems. The object is almost always a game against nature or a leaky opponent. The conserved quantity is a threshold or a value function.

In this window:

- [Robot Road Trip](../puzzles/2025-07-robot-road-trip.md) — July 2025. Two-lane highway; minimize lost miles; optimize the lane split *a*.
- [Robot Baseball](../puzzles/2025-10-robot-baseball.md) — October 2025. Strike-zone parameter *p*; maximize P(full count) at Nash.
- [Robot Javelin](../puzzles/2025-12-robot-javelin.md) — December 2025. Keep-or-redraw on [0,1]; information leak; counter-Nash.

CS bridge: these are small extensive-form games. The right tools are indifference, value iteration backward from a terminal count, and (for Javelin) exploiting a known deviation. φ shows up because the fair keep/redraw threshold on U[0,1] vs U[0,1] is the golden ratio.
