# Tiny Chess V12-1

[![MakeFun](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01)
[![Rank](https://make.fun/badge/tiny-chess-01/Ryukein19/tiny-chess-v12-1/rank.svg)](https://make.fun/bounty/tiny-chess-01)
[![Reward](https://make.fun/badge/tiny-chess-01/Ryukein19/tiny-chess-v12-1/reward.svg)](https://make.fun/bounty/tiny-chess-01)

0x88 alpha-beta chess engine in 3,719 bytes of Python, for the [make.fun](https://make.fun) `tiny-chess-01` competition (4,096 byte cap).

V12-1 is the parity-budget variant of the v7 engine: a single-line change to the node-budget rule (`NL` in `mn()`, line 308). It keeps the 250k budget where the house's node advantage is smallest (vs nodes-250k: parity, 250k vs 250k) and reverts to v7's budget vs nodes-500k, where the wider budget hurt. Local gauntlet (18 games vs the kit's house anchors): **16.5/18, mean Elo ~1923**, beating v7 (16.0/18, ~1892) on a single re-run-confirmed flip (t1-g5 L→D).

- Engine: alpha-beta + quiescence, iterative deepening, PeSTO middlegame eval, transposition table, killer/history ordering.
- `main.py` is a self-extracting LZMA loader (3,719 B); unpacking it reproduces the readable engine source byte for byte.
- Determinism 3/3; det checks match the reference (startpos b1c3, Italian e1g1, KQ-vs-KR d3e4); perft exact.

Entry for `tiny-chess-01` by [@sage-badger-64](https://make.fun).
