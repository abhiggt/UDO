# UDO

**Lift for what flies. Freeze for what doesn't.**

UDO is a finger party game for one phone and a table full of friends. Everyone puts a finger on the screen, an emoji reel spins in the middle, and when the ring turns green you have a split second to decide: does it fly? Lift. Doesn't fly? Don't you dare move.

It's the childhood game *Chidiya Udd*, rebuilt for the phone in the middle of the table, with lives and a last-finger-standing winner, gotcha emoji, spotlight and rapid-fire rounds, a game that keeps getting faster, and dares for whoever gets caught.

Version 0.3 · see [CHANGELOG.md](CHANGELOG.md)

---

## How to play

1. Put the phone flat in the middle. Everyone puts one finger down near their edge of the screen (the dotted spots show where; the big circle is the reel, not a button) and holds still.
2. The reel rolls. **Don't lift until the ring turns green.**
3. **It flies** (🐦 ✈️ 🦋)? Lift fast. Too slow and you're caught. If everyone lifts, the slowest finger takes a strike. Two strikes and you're caught.
4. **It doesn't fly** (🐘 🚗 🍌)? Freeze. Lift and you're caught. Watch for **gotchas** like 🐧 🐥 🐛 🥚: they look like they fly, and they don't.
5. **Caught?** You lose a life (Knockout) and do the dare on the card, roll another, or let the others give you one. Tap **Dare done**, then **Continue**, and fingers back down.
6. **Knockout** (the default): last finger standing wins. Or switch to **Endless** in the intro and tap **End game** whenever you like for the awards.

**The fine print**

| Rule | What happens |
| --- | --- |
| Lifting before green | Caught |
| Lifting within 0.1 s of green | Caught. Nobody reacts that fast, so it's a guess |
| Slowest fingers within 0.01 s of each other | Photo finish: they all take a strike |
| Everyone within 0.01 s | "Dead heat." No strikes |
| Two people make the same mistake at the same instant (0.15 s) | Caught together, shared dare |
| 🔄 UDO Reverse (pink ring), when switched on in the intro | The rule flips for that round: lift for what doesn't fly |
| 🎯 Spotlight (ring in one player's colour), from round 5, 3+ players | Only that player plays; anyone else who lifts is caught |
| ⚡ Rapid fire, from round 6 | Three reels back to back with almost no pause |
| Every 3 rounds | A new level: the reel spins faster (up to 2.2×), the slow crawl gets shorter, more gotchas. The time to lift shrinks every round, from 1.1 s to 0.55 s |
| 🏆 Knockout lives | 3 each (2 with 6+ players), shown as the pieces of your ring. Each catch costs one |
| Out of lives | Come back once with 1 life by doing a second dare the table picks |
| A round that would knock out everyone left | Sudden death: nobody goes out |
| Final two | Announced, and the reel goes to at least 1.6× |

## Features

- **No setup:** one phone, 2 to 10 players (as many as the phone can track), no accounts, no names. Players are numbered and coloured, in colours that never look like the game's own signals.
- **Reads from every side:** labels turn to face each player; centre text is shown both ways up.
- **Fair timing:** reaction times come from each touch's own timestamp.
- **Dares:** 30 solo and 8 group dares, shuffled like a deck so nothing repeats too soon. Roll another with 🎲, hand it to the group with 🙋, or add your own on the intro (✍️ Your dares).
- **Knockout or Endless:** play for a winner (lives, comebacks, a crowned champion) or just for dares.
- **About 80 emoji**, including gotchas that look like they fly and don't.
- **It speeds up for real:** a new level every 3 rounds, with a banner, a rising sound and quicker ticks.
- **Round twists:** 🎯 Spotlight, ⚡ Rapid fire, and 🔄 UDO Reverse (off by default; switch it on in the intro).
- **Sound switch** in the intro. Sounds are quiet feedback only; the emoji is always the cue.
- **Awards and sharing:** 👑 Last finger standing, ⚡ Fastest finger, 🧊 Ice cold, 🙈 Easily fooled, 🐢 Slowpoke, 😈 Dare magnet (and one secret award), shared as an image straight to WhatsApp.
- **Three easter eggs**, all bird-brained, none of them help you win. Spoilers at the bottom.
- **Installable and offline:** add it to your home screen and play with no internet.
- **Responsive:** small phones to tablets, portrait or landscape.

## Run it locally

It's one HTML file with no build step.

- **Quickest:** open `index.html` in a browser. Everything works except install and offline caching, which need a web server.
- **With a local server** (to test install and offline):

  ```bash
  npx serve .
  # or
  python3 -m http.server 8000
  ```

  Then open the address it prints. To play on your phone, open your computer's local IP address (for example `http://192.168.1.20:8000`) on a phone on the same Wi-Fi.
## Make it yours

Everything lives in `index.html`.

| What | Where |
| --- | --- |
| Timings, levels and speed-ups, lives, strike and tie rules, spotlight, rapid-fire, reverse-round and chicken odds, volume | `CFG` near the top of the script |
| Flying, non-flying and gotcha emoji | `FLY`, `NOFLY` and `GOTCHA` |
| Dares | `DARES` (solo) and `GROUP_DARES` |
| What the game says when everyone freezes correctly | `STILL_LINES` |
| Player colours | `COLORS` |
| Copy on the intro, rules and end screens | The HTML sections `#intro`, `#how`, `#end` |
| Fonts | `--font` (Bricolage Grotesque) and `--serif` (Instrument Serif) in the CSS |

**Releasing a new version:** change `VERSION` in `index.html`, bump `CACHE` in `sw.js` (for example `udo-0.4`) so installed copies update, and add an entry to `CHANGELOG.md`.

## Project structure

```
.
├── index.html               the whole game: markup, styles, script
├── sw.js                    service worker for offline play
├── manifest.webmanifest     app name, icons, fullscreen display
├── icon-192.png             app icons
├── icon-512.png
├── icon-maskable-512.png
├── apple-touch-icon.png
├── og-image.png             link-preview image (1200 x 630)
├── CHANGELOG.md             version history
└── README.md
```

## Good to know

- **How many fingers?** iPhones usually track about 5 at once, most Android phones 10.
- **Sound** starts after the first tap (browser rule). Vibration works on Android only.
- **Swiping from the bottom edge on iPhone** can cancel every touch at once. If that happens mid-round, the game treats it as everyone lifting.
- **Fonts** load from Google Fonts and are cached for offline play; without them the game falls back to the system fonts.

## Credits

- Inspired by the childhood game *Chidiya Udd* and by [Chooser](https://chooser.kuehle.me/) by kuehle.
- Typefaces: [Bricolage Grotesque](https://fonts.google.com/specimen/Bricolage+Grotesque) and [Instrument Serif](https://fonts.google.com/specimen/Instrument+Serif), both under the SIL Open Font License.
- Emoji are drawn by each device's own emoji font.
