# Changelog

All notable changes to UDO are listed here, newest first.

## [0.3] - 2026-10-25

Built to stay fun past round 5: a winner to play for, more to think about, and a pace that keeps climbing.

### Added
- **Knockout mode** (the default; switch to Endless in the intro).
  - Everyone has 3 lives (2 with 6 or more players), drawn as the pieces of your ring. Each catch costs one, plus the dare.
  - **Comeback:** out of lives? Once a game, do a second dare the table picks and you're back with 1 life.
  - **Sudden death:** a round that would knock out everyone left takes no lives.
  - **Final two** is announced and the reel goes to at least 1.6×.
  - **Last finger standing** wins: their colour floods the screen with a 👑, and the end screen, awards and share card name them.
- **About 80 emoji** (from 24), all from 2020 or earlier so older phones draw them.
- **Gotchas:** 🐧 🐣 🐥 🐛 🦤 🥚 🕷️ look like they should fly and don't. About 1 in 8 "doesn't fly" rounds at the start, rising to almost 1 in 2.
- **🎯 Spotlight rounds** (from round 5, 3+ players left): the ring turns one player's colour and only they play. Everyone else must freeze whatever lands.
- **⚡ Rapid fire** (from round 6, now and then): three reels back to back with almost no pause.
- Level-up, spotlight and winner sounds.

### Changed
- **Faster, and you feel it.**
  - A new level every 3 rounds (was 5), with a "Level N ⚡" banner and ticks that climb in pitch.
  - The reel speeds up 15% per level, up to 2.2× (was 10% per step, up to 1.5×).
  - The slow crawl shortens from 5 steps to 4, then 3, and the blur before it shortens too.
  - The time to lift starts at 1.1 s (was 1.4 s) and shrinks to 0.55 s (was 0.8 s).
  - Pauses between rounds are about a third shorter.
- One banner line before a round says what's special about it: spotlight, reverse, final two, rapid fire or a new level.
- The intro has a Knockout / Endless switch, and How to play covers lives, comebacks, gotchas, spotlight, rapid fire and levels.

## [0.2.2] - 2026-10-24

Less on screen, and nobody aims for the middle.

### Changed
- **Seat guides instead of a finger by the circle.** The empty lobby used to show "☝️" or "One finger each" right beside the big centre circle, which read as "press here". Now four marigold spots pulse near the edges (one per side in portrait, four corners in landscape) and the centre shows a faint 🐦, so it reads as the display. A tap in the middle gets "Near the edge, not the middle". The spots go away once two fingers are down.
- **Far less text during play.**
  - Player numbers show only while seats are being taken, and on the caught screen.
  - No per-finger times while lifting; the lift burst is the feedback.
  - After a round, only the struck finger ("Strike", "2nd strike!") and the fastest ("⚡ 180 ms", 3+ players) get a word.
  - The centre speaks only for rare results ("Photo finish!", "Dead heat."), not "#3 slowest".
  - Shorter hints: "Reverse: lift if it can't fly" before a reverse round, nothing during the spin; "Chicken? Nobody knows. Free round."
- **Strikes are notches on your ring**, the side facing the reel, instead of small dots next to your number.
- **Dare card:** "This round" listed every player's time; now it shows only the fastest. The tally lists only players who have done a dare.
- How to play and the README say where fingers go: near your edge, on the dotted spots.

### Fixed
- Labels placed outside a finger now check that the whole line fits on screen, not just its middle (a top-corner "Strike" could be cut off in landscape).

## [0.2.1] - 2026-10-24

Fixes from a playtest at 4, 6 and 8 players.

### Fixed
- **Text no longer piles up.** Player labels flip to the outer side of a finger when they would run into the reel, and the centre text stays on one line and hides any copy that would sit on a player. Results in the centre are short ("#3 slowest. Strike!"); each finger's own label carries the time.
- **Player colours no longer look like game signals.** Green (go), amber (strike), yellow (chicken) and the reverse magenta are out of the player palette.
- **Photo finish is rare again.** It now needs the slowest fingers within 0.01 s (about what a phone's touch sampling can tell apart), not 0.05 s. At 0.05 s two or more players took a strike in about 6 of 10 lift rounds with 4 players and 8 of 10 with 8; now it's about 1 in 5. With 2 players, rounds with no strike drop from about half to about 1 in 9.
- **Computers without a touchscreen** now see "UDO needs a touchscreen" and the link to open on a phone, instead of a lobby they can't leave.
- **Finger limit.** The lobby stops at what the phone can track (5 on iPhones, up to 10 elsewhere) and says "Full at 5" instead of silently ignoring the next finger.

### Added
- The share card and share message now carry the game's link, so friends who see the results can play.
- Link previews: description and Open Graph tags plus a 1200 x 630 preview image (`og-image.png`), so a pasted link shows a card in WhatsApp and elsewhere.

### Changed
- Release links in this changelog point to the real repository.

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

[0.3]: https://github.com/abhiggt/UDO/releases/tag/v0.3
[0.2.2]: https://github.com/abhiggt/UDO/releases/tag/v0.2.2
[0.2.1]: https://github.com/abhiggt/UDO/releases/tag/v0.2.1
[0.2]: https://github.com/abhiggt/UDO/releases/tag/v0.2
[0.1]: https://github.com/abhiggt/UDO/releases/tag/v0.1
