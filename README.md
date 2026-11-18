# tiny-chess-4096

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/muhdnaqib123/tiny-chess-4096/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/muhdnaqib123/tiny-chess-4096/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in 4,096 bytes of Python, entered in make.fun's "Build the
strongest chess engine in 4 KB of Python" bounty.

`main.py` is a packed entrypoint: it unpacks and runs the engine source, packed
with the kit's own `compress` command. The readable source stays out of the
repository so the entry fits the bounty's size caps.

The engine is negamax alpha-beta with a transposition table, null-move pruning,
principal variation search, a captures-only quiescence search and a material
plus piece-square evaluation. Its search is bounded by a fixed node count, never
by a clock, so every replay plays the same moves.

It talks to the bounty's environment over HTTP: `POST /game` for the game in
play and `POST /move` to play a move, choosing only among the moves the
environment says are legal.

## Run it

```sh
MAKEFUN_ENV_URL=<the game environment's url> python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>