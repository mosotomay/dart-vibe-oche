# Dart Vibe

Dart scoring for **501** (double-out) and **Cricket** — pub-night ready, installable to your iPhone home screen as a PWA.

- Up to 8 players, with players sharing a color forming a Cricket team
- Three score-entry methods: multiplier + number, dartboard tap, numeric keypad (501 only)
- 501 checkout suggestions (2/3-dart out-shots), bust detection, per-dart undo
- Cricket transposed scoreboard (numbers as rows, teams as columns) with mark glyphs
- Win screen with 3-dart avg / 100+ counts (501) or marks / points (Cricket)
- Works fully offline once installed (service worker caches everything, including React + fonts)

## Try it locally

A service worker needs `http(s)://` or `localhost` — opening the file directly with `file://` won't register the SW. Quickest local server:

```bash
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

## Install on iPhone

1. Open the deployed URL in **Safari** on iPhone (Chrome on iOS won't install PWAs).
2. Tap the share icon → **Add to Home Screen** → Add.
3. Launch from the home-screen icon — fullscreen, no browser chrome, works offline.

In-browser the app shows inside an iPhone-frame design preview; once installed standalone it renders fullscreen on the actual phone.

## Deploy to GitHub Pages

1. Create an empty repo on github.com (e.g. `dart-vibe`), don't add a README.
2. From this folder:
   ```bash
   git remote add origin git@github.com:YOUR-USER/dart-vibe.git
   git push -u origin main
   ```
3. On the repo page → **Settings → Pages** → set source to `Deploy from a branch`, branch `main`, folder `/ (root)`. Save.
4. After ~1 min the site is live at `https://YOUR-USER.github.io/dart-vibe/`.

## File layout

```
index.html              # the whole app (React via CDN, all components inline)
manifest.webmanifest    # PWA manifest
service-worker.js       # offline cache
icon.svg                # source icon — two crossed darts
icon-192.png            # PWA icon
icon-512.png            # PWA icon
apple-touch-icon.png    # iOS home-screen icon (180×180)
```
