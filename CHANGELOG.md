# Changelog

All notable changes to UDO are listed here, newest first.

## [0.2] - 2026-10-16

### Added
- **Three easter eggs.** All bird-brained, none of them help you win. Details are behind a spoiler at the bottom of the README.
- **Certified dodo**, a secret award that only shows up if somebody earns it.
- **A second typeface**, Instrument Serif in italics, for the game's own voice: the intro tagline, results, wisecracks, the reason you got caught and the end-screen summary. Bricolage Grotesque stays for everything you act on.
- **Proper on/off switches** in the intro for 🔄 UDO Reverse and 🔊 Sound.
- When everyone freezes correctly, the game now says one of several lines ("Nerves of steel.", "Statues. Respect.", and others) instead of the same one every time.

### Changed
- **UDO Reverse is off by default.** Switch it on in the intro.
- **Play again** is now a full reset: it goes back to the intro with fresh scores, and settings can be changed there.
- **Add new players** goes straight into the lobby so everyone can put their fingers down again.
- The dare card's group option now reads **🙋 Let us give the dare**, and the card says "#1, #2 and #4, give #3 a dare."
- The colour blobs on the intro are smaller and fainter, so the logo leads.
- The end-screen summary mentions any mysterious chickens.

### Removed
- The "Add new players" pill on the intro and the rematch-style Play again button.
- The "Nobody budged. Nice." line.

## [0.1] - 2026-10-16

The first public version. Everything below is new.

### The game
- One phone flat in the middle, one finger each, 2 to 10 players (as many fingers as the phone can track).
- An emoji reel rolls in the centre circle like a vending machine: a fast blur, then a slow readable crawl over the last five, with a near miss of the opposite kind right before it stops, and sometimes a fake stop.
- The ring turns **green** when the reel lands. That's the only moment to react.
- **Flies?** Lift before time runs out. **Doesn't fly?** Freeze.
- Lifting while it rolls, or within 0.1 s of green (too fast to be a real reaction), gets you caught.
- **Strikes:** if everyone lifts, the slowest finger takes a strike. Two strikes and you're caught.
- **Photo finish:** slowest fingers within 0.05 s of each other all take a strike. If everyone is that close: "Locked in, nice."
- **Caught together:** anyone who makes the same mistake in the same instant (within 0.15 s) is caught with you and shares the dare.
- **UDO Reverse:** after the first few rounds, a surprise round now and then flips the rule (lift for what doesn't fly). Pink ring, reversed spin, 🔄 in the circle. Never two in a row. Can be switched off on the intro.
- Reaction window shrinks every round, and the reel speeds up every 5 rounds.
- Reaction times use each touch's own timestamp for fairness.

### Look and feel
- Black screen and colour blobs, in the spirit of [Chooser](https://chooser.kuehle.me/).
- Blobs shrink as more players join, so 6+ players fit on a small phone.
- Every label turns to face the player sitting at that edge; centre text is shown twice, one copy upside-down.
- When someone is caught, their colour floods the screen and closes in on their finger.
- Lift bursts, a green shockwave on landing, quiet sounds and vibration (Android) as feedback. The emoji is always the cue.
- First-timers get two tiny hints; after one round the screen stays clean.

### Dares
- 30 solo and 8 group dares, drawn like a shuffled deck: no repeats until all are used, never the same one twice in a row.
- The dare card faces the caught player, shows everyone's time for the round and a running dare tally.
- **🎲 Another dare** rolls a new one. **🙋 Our call** hands it to the other players by number.
- **Your dares:** add your own on the intro. They're mixed in (or used alone) and saved on the phone.
- **Dare done** stamps the card; the button then becomes **Continue**.

### End of game
- **Everyone's grounded** screen with awards: ⚡ Fastest finger, 🧊 Ice cold, 🙈 Easily fooled, 🐢 Slowpoke, 😈 Dare magnet.
- **Share results** makes a picture of the awards for WhatsApp (or saves it where sharing isn't supported).
- **Play again** goes back to the intro with the same players, so settings like UDO Reverse can be changed first. **Add new players** starts fresh.

### Platform
- Single `index.html`, no build step, no dependencies.
- Installable web app with offline play (service worker + manifest), fullscreen when launched from the home screen.
- Responsive from a 320 px phone to tablets, portrait and landscape. Canvas sized in pixels so no browser can stretch it.
- Screen stays awake during play.

### Before 0.1
UDO grew out of a run of quick prototypes (a "Chidiya Udd" finger game with voice cues, a cartoon version, a plain chooser-style version and several playtest rounds). Their best ideas are folded into 0.1; the prototypes themselves aren't versioned.

[0.2]: https://github.com/YOUR-USERNAME/udo/releases/tag/v0.2
[0.1]: https://github.com/YOUR-USERNAME/udo/releases/tag/v0.1
