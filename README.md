<p align="center"><img src="logo.svg" width="96" alt="Vegas Baby logo"></p>

# Vegas Baby

A casino floor in a single HTML file. Walk up to any of nine tables and play
with play money: blackjack, Texas Hold'em, roulette, craps, baccarat, video
poker, Three Card Poker, slots and keno. Every game uses real casino rules,
every bet shows its house edge, and a strategy coach shows you the best play.

It is free, with no ads, purchases or sign-up. Nothing can be bought or cashed
out: you start with $10,000 in play chips and the cashier tops you up for free.
Because it is one HTML file it also runs offline once saved.

## Play

Open `index.html` in any browser. There is nothing to install or build.

To put it online, turn on GitHub Pages for this repository (Settings → Pages →
deploy from the `main` branch, root folder). The game will be served at
`https://<your-username>.github.io/<repo-name>/`.

Your bankroll, stats and settings are saved in the browser.

## The floor

| Game | What's in it | House edge |
| --- | --- | --- |
| Blackjack | 1, 2, 6 or 8 decks; dealer stands or hits soft 17; 3:2 or 6:5; double, split to four hands, double after split, late surrender, insurance; basic-strategy coach; Hi-Lo card count trainer | about 0.3–2% depending on the rules |
| Texas Hold'em | No-limit, 1–5 computer opponents with ten different styles, three skill levels, four stakes, side pots, equity and pot-odds helper, hand history | none (no rake) |
| Roulette | European, American, and la partage; every inside and outside bet including splits, streets, corners, six lines, trios, first four and top line; animated wheel | 1.35–7.89% |
| Craps | Pass, don't pass, come, don't come, odds and lay odds (1× to 100×), place bets, field, hardways and one-roll props | 0–16.67% |
| Baccarat | Punto banco from an 8-deck shoe with full drawing rules, pair bets, bead plate and big road | 1.06–14.36% |
| Video Poker | Jacks or Better 9/6, Bonus Poker 8/5, Double Double Bonus 9/6, Deuces Wild (Not So Ugly Ducks); exact best-hold coach | 0.27–1.02% with perfect play |
| Three Card Poker | Ante/Play with ante bonus, Pair Plus (1-4-6-30-40), Q-6-4 coach | 3.37% (ante), 2.32% (pair plus) |
| Slots | Three weighted reels with a wild star; exact return shown | 6.00–6.41% |
| Keno | Pick 1–10 of 80 numbers; exact odds and return for every spot count | 6.4–12.5% |

Also on the floor:

- **Stats** for every game: rounds, total wagered, your result, and the result
  the house edge predicts for the bets you actually made.
- **Strategy coach** in every game where strategy matters, with warnings when
  a play costs you money. It can be turned off.
- **Settings:** light, dark or automatic theme; six felt colours; six card
  backs; a four-colour deck; dealing speed; sounds.
- **Keyboard:** Space deals, spins or rolls in every game; blackjack uses
  H S D P R; video poker 1–5; Three Card Poker P and F; Hold'em F C R.

## Honest odds

The engine is written from scratch in JavaScript and tested in Node. Every
house edge the game shows was checked:

- **Hand evaluation:** the poker evaluator produces the exact count of every
  hand category over all 2,598,960 five-card hands; the Deuces Wild evaluator
  matches the published deal counts; the seven-card evaluator was checked
  against best-of-21 on 20,000 random hands.
- **Blackjack:** with basic strategy, 3 million simulated hands at 6 decks,
  S17, DAS, 3:2 gave a 0.40% house edge, matching published figures; 6:5 with
  H17 gave 2.01%.
- **Baccarat:** 1.06% banker, 1.24% player and 14.36% tie, calculated exactly
  by enumerating every coup from an 8-deck shoe.
- **Three Card Poker:** 3.37% ante with the Q-6-4 strategy, by checking all
  407 million player and dealer combinations; Pair Plus 2.32% exactly.
- **Craps:** every bet's resolution was simulated over 6 million rolls and
  matched its published edge.
- **Roulette, keno and slots:** returns calculated exactly from the paytables
  and probabilities.
- **Video poker:** the coach evaluates all 32 possible holds against every
  possible draw (up to 1.5 million per hold) to find the exact best play.
- **Hold'em:** 12,000 random hands with side pots, all-ins and short raises
  were played with chips conserved and every pot awarded to the best
  eligible hand. The computer players estimate their chances with Monte Carlo
  simulation, narrow your likely hands when you raise, and adjust by style.

The point is to show how casino games really work. The house edge is real;
no betting system changes it.

## Files

- `index.html`: the whole casino: markup, styles, engine and games
- `logo.svg`: repository logo and page icon
- `LICENSE`: MIT licence

## License

MIT. See `LICENSE`.
