# No Thanks!

A single-file browser version of the card game *No Thanks!* (Thorsten Gimmler) for one human against 2 to 6 bots. No build step and no dependencies: open `index.html`.

> Game page and three bots (Claude MonteCarlo ×2, Claude Squeeze) written with Claude (Anthropic). The 49-bot Rust pool and the original simulations are by Ben and Laura.

## Rules implemented
Cards 3 to 35, 9 removed unseen (24 played). Starting chips: 11 for 3 to 5 players, 9 for 6, 7 for 7. Pass by paying a chip, or take the card and every chip on it; with no chips you must take it. Only the lowest card of each run of consecutive numbers scores, and each chip left is -1. Lowest total wins.

Checked against the [published rules summary](https://en.wikipedia.org/wiki/No_Thanks!_(game)) and the [publisher's page](https://www.amigo.games/game/nothanks).

## Bots
- **Rust pool (49 bots):** a JavaScript port of the strategies in the author's `main_LQ.rs` tournament simulator. Over 1M five-player games, each bot's win rate matched the Rust program's within 0.5 points.
- **Claude bots (3):** `Claude MonteCarlo(rollouts=40)`, `Claude MonteCarlo(rollouts=150)` and `Claude Squeeze`. In five-player games against four of the top five Rust bots (an equal share is 20%), MonteCarlo(150) won about 54% of 500 games, MonteCarlo(40) about 42%, and Squeeze about 24% (no better than the PhasedBargain(9) it is built on).

## Hosting on GitHub Pages
Put `index.html` at the root of a repository, then Settings > Pages > Build and deployment > Deploy from a branch > `main` / root.
