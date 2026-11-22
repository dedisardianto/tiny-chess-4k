# tiny-chess-4k

[![make.fun](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/dedisardianto/tiny-chess-4k/rank.svg)](https://make.fun/bounty/tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/dedisardianto/tiny-chess-4k/reward.svg)](https://make.fun/bounty/tiny-chess-01)

An original chess engine in a single 4 KB Python file, built for the
[make.fun Tiny Chess bounty](https://make.fun/bounty/tiny-chess-01).
It plays the gauntlet through the competition env: no other file is read.

## Design

- 0x88 board, negamax alpha-beta with iterative deepening on a fixed
  node budget (deterministic: no clock, no randomness).
- Transposition table (Zobrist), killer moves, history heuristic,
  MVV-LVA capture ordering, null-move pruning.
- Quiescence search over captures, promotions and check evasions.
- Evaluation: material plus piece-square tables, bishop pair, and
  endgame king centralisation. Handles checkmate, stalemate,
  insufficient material, repetition and the 50-move rule.

## Size

`main.py` is the whole engine: at most 4,096 bytes as committed
(the source is packed with the kit's `makefun compress`). Python 3.13,
standard library only.
