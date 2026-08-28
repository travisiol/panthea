# PANTHEA

Landing page for PANTHEA — a play-to-earn arena where your token balance
unlocks gods, and the god matchup decides the fight.

**Nothing on this page is live.** There is no token, no reserve, no arena
yet. Every panel that will hold real data is labelled as awaiting launch.

## The game, in one paragraph

Holding PANTHEA unlocks gods — it never decides who wins. Zeus beats
Poseidon, Poseidon beats Hades, Hades beats Zeus. Both players pick blind
and reveal at the same time, so a single god can beat the wallet that
fielded three. Winners are paid from a reserve funded by trading fees;
losers keep every token they hold and lose only rank.

## Running it

It is one static HTML file with no build step and no dependencies.

Open `index.html` in a browser, or serve the folder:

```bash
python -m http.server 8000
```

## Deploying to GitHub Pages

Settings → Pages → Source "Deploy from a branch" → branch `main`,
folder `/ (root)` → Save. The site is live at
`https://travisiol.github.io/panthea/` within a minute or two.

## Layout

```
index.html      the whole site — CSS, JS and SVG all inline
gods/
  zeus.jpg      artwork for the three playable gods
  poseidon.jpg
  hades.jpg
  artemis.jpg   artwork for the gods announced but not yet in the roster
  ares.jpg
  apollo.jpg
  *.svg         fallback drawings, shown only if a .jpg fails to load
```

## Swapping the artwork

Portraits sit in a 2:3 frame with `object-fit: cover`, so use portrait
images — the shipped ones are 760x1140. Drop a replacement into `gods/`
under the same filename and reload; nothing in `index.html` needs editing.

The JPEGs are resized and compressed from 1024x1536 PNG originals, about
110 KB each instead of 2 MB. Re-export from the originals if you ever need
them larger.

## Still to decide

- **Tier thresholds.** How much PANTHEA unlocks each god cannot be set
  until supply and distribution are fixed. The Transparency table already
  has a row for it.
- **A sixth god breaks the cycle.** For every god to beat the same number
  of others you need an odd roster — 3 gods each beat 1, 5 each beat 2,
  7 each beat 3. Six cannot be balanced. Artemis, Ares and Apollo are
  drawn and ready, so the roster should go to 5 or 7, not 6.
