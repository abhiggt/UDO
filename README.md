# UDO

**Lift for what flies. Freeze for what doesn't.**

UDO is a finger party game for one phone and a table full of friends. Everyone puts a finger on the screen, an emoji reel spins in the middle, and when the ring turns green you have a split second to decide: does it fly? Lift. Doesn't fly? Don't you dare move.

It's the childhood game *Chidiya Udd*, rebuilt for the phone in the middle of the table, with strikes, photo finishes, optional reverse rounds and dares for whoever gets caught.

**Play it:** `https://YOUR-PROJECT.vercel.app` (replace with your Vercel link once deployed)

Version 0.2 · see [CHANGELOG.md](CHANGELOG.md)

---

## How to play

1. Put the phone flat in the middle. Everyone puts one finger down, outside the circle, and holds still.
2. The reel rolls. **Don't lift until the ring turns green.**
3. **It flies** (🐦 ✈️ 🦋)? Lift fast. Too slow and you're caught. If everyone lifts, the slowest finger takes a strike. Two strikes and you're caught.
4. **It doesn't fly** (🐘 🚗 🍌)? Freeze. Lift and you're caught.
5. **Caught?** Do the dare on the card, roll another, or let the others give you one. Tap **Dare done**, then **Continue**, and fingers back down.
6. Tap **End game** whenever you like for the awards.

**The fine print**

| Rule | What happens |
| --- | --- |
| Lifting before green | Caught |
| Lifting within 0.1 s of green | Caught. Nobody reacts that fast, so it's a guess |
| Slowest fingers within 0.05 s of each other | Photo finish: they all take a strike |
| Everyone within 0.05 s | "Locked in, nice." No strikes |
| Two people make the same mistake at the same instant (0.15 s) | Caught together, shared dare |
| 🔄 UDO Reverse (pink ring), when switched on in the intro | The rule flips for that round: lift for what doesn't fly |
| Every 5 rounds | The reel speeds up; the reaction window shrinks every round |

## Features

- **No setup:** one phone, 2 to 10 players, no accounts, no names. Players are numbered and coloured.
- **Reads from every side:** labels turn to face each player; centre text is shown both ways up.
- **Fair timing:** reaction times come from each touch's own timestamp.
- **Dares:** 30 solo and 8 group dares, shuffled like a deck so nothing repeats too soon. Roll another with 🎲, hand it to the group with 🙋, or add your own on the intro (✍️ Your dares).
- **UDO Reverse:** surprise flipped rounds. Off by default; switch it on in the intro.
- **Sound switch** in the intro. Sounds are quiet feedback only; the emoji is always the cue.
- **Awards and sharing:** ⚡ Fastest finger, 🧊 Ice cold, 🙈 Easily fooled, 🐢 Slowpoke, 😈 Dare magnet (and one secret award), shared as an image straight to WhatsApp.
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

## Deploy to Vercel

1. Push this folder to a GitHub repository.
2. On [vercel.com](https://vercel.com), choose **Add New → Project** and import the repository.
3. Leave the settings as they are: **Framework Preset: Other**, no build command, output directory is the project root.
4. Click **Deploy**. Every push to `main` redeploys automatically.

Prefer the command line? `npx vercel` from this folder does the same.

`vercel.json` makes sure phones always fetch the newest `index.html` and service worker, and serves the manifest with the right type.

## Install and offline play

Open the deployed link once on the phone, then:

- **iPhone:** Share → **Add to Home Screen**
- **Android:** tap **📲 Install** on the intro (or the browser menu → Install app)

After that, UDO opens fullscreen from the home screen and works with no internet.

## Make it yours

Everything lives in `index.html`.

| What | Where |
| --- | --- |
| Timings, speed-ups, strike and tie rules, reverse-round and chicken odds, volume | `CFG` near the top of the script |
| Flying and non-flying emoji | `FLY` and `NOFLY` |
| Dares | `DARES` (solo) and `GROUP_DARES` |
| What the game says when everyone freezes correctly | `STILL_LINES` |
| Player colours | `COLORS` |
| Copy on the intro, rules and end screens | The HTML sections `#intro`, `#how`, `#end` |
| Fonts | `--font` (Bricolage Grotesque) and `--serif` (Instrument Serif) in the CSS |

**Releasing a new version:** change `VERSION` in `index.html`, bump `CACHE` in `sw.js` (for example `udo-0.3`) so installed copies update, and add an entry to `CHANGELOG.md`.

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
├── vercel.json              cache headers for Vercel
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

## License

Not chosen yet. Add a `LICENSE` file (MIT is a common choice for small open-source games) before inviting contributions.

---

<details>
<summary>🥚 Easter egg spoilers</summary>

1. **When pigs fly.** On the intro, tap the O in the logo 7 times quickly.
2. **The chicken.** About 1 round in 25 (from round 3), the reel lands on 🐔. Does a chicken fly? Nobody knows. Free round: no one can be caught after it lands.
3. **The dodo.** Get caught three times in a row and you're officially a dodo. A 🦤 waddles across the screen, and you get the secret *Certified dodo* award at the end.

</details>
