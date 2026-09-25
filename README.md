# GM Opening Books

[![Stars](https://img.shields.io/github/stars/TitisBuyutKusumo/gm-opening-books?style=social)](https://github.com/TitisBuyutKusumo/gm-opening-books/stargazers) [![License](https://img.shields.io/github/license/TitisBuyutKusumo/gm-opening-books)](LICENSE)


Polyglot chess opening books built from real super-GM games. Point your engine at one and it opens like them.

- **magnus.bin** (7 MB, 444,067 positions) — Magnus Carlsen
- **hikaru.bin** (45 MB, 2,916,754 positions) — Hikaru Nakamura

## Where the data comes from

Every game pulled from the chess.com published API (`api.chess.com/pub/player/.../games/...`), month by month through September 2026:

- Magnus: 9,454 standard games (Dec 2014 – Sep 2026). Variants and chess960 excluded.
- Hikaru: 68,349 standard games (Jan 2014 – Sep 2026). He plays roughly 7x more than Magnus, hence the bigger file.

All time controls included (rapid, blitz, bullet). No opponent-rating filter — this is the raw repertoire, not a curated "strong opponents only" cut.

## How it was built

Per position: what the GM played, how many times. Weight = frequency — the more they played it, the more often the engine picks it. Standard chess only, capped at 60 plies (opening + early middlegame), standard KxR castling encoding, sorted file for safe binary search.

## Why is magnus.bin so small?

Not an error. Three reasons: Magnus plays far less online (9k vs 68k games), his repertoire is narrow (main-line 1.e4/1.d4 with heavy transpositional overlap into the same positions), and the 60-ply cap trims middlegame tails. Small means dense, not broken.

## How to use

Standard polyglot `.bin` — anything that reads polyglot books works: Komodo, Rodent, Arena, Banksia Gui, CuteChess, Scid vs. PC, Lucas Chess, DroidFish on Android (copy into the `DroidFish/book` folder), or Stockfish via the PolyGlot adapter. Outside the book, your engine thinks on its own as usual.

## What it's for

So your engine opens like watching Magnus or Hikaru play: Ruy Lopez + Berlin + Catalan + Sveshnikov à la Magnus, or 1.e4 mixed with 1.b3 and the Bongcloud à la Hikaru (yes, Ke2 made the book). Fun vs humans. For engine-vs-engine tournaments it adds no Elo — that's not how books work.

## License

MIT — do whatever you want with it. See LICENSE.
