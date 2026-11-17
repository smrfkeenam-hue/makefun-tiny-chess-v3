# tiny-chess v3 — make.fun tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/smrfkeenam-hue/makefun-tiny-chess-v3/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/smrfkeenam-hue/makefun-tiny-chess-v3/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A from-scratch 4KB Python chess engine for the
[make.fun tiny-chess-01 bounty](https://make.fun/bounty/tiny-chess-01).

## Architecture

- **Board:** 120-char string board, rank mirror after every move (side to move
  always uppercase). Move ints (`f | t<<7 | flag<<14`).
- **Search:** PVS + null-move pruning (R=3) + LMR + check extensions, merged
  quiescence (captures + promotions, evasions in check, 12-ply cap),
  persistent transposition table, 2 killers per ply, contempt.
- **Eval:** incremental material + piece-square tables, king endgame switch,
  bishop pair, passed pawns, king pawn shield.
- **Budget:** fixed 50,000 nodes per move (deterministic, never the clock).

## Files

- `main.py` — the engine (≤ 4,096 bytes, packed).
- `LICENSE` — MIT.

## License

MIT — see `LICENSE`.
