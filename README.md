# Crossroads — All Episodes player

One page with every Crossroads episode, split into Season 1 and Season 2
sections, with a **Play All Episodes** button (plays 1 → 23 straight through)
plus per-season Play buttons.

Live at: https://crossroadsadventist.github.io/crossroads/

## How it works

No audio files live in this repo. Each episode's audio is loaded by absolute
URL from its season player:

- Episodes 1–21 → https://crossroadsadventist.github.io/crossroads-season-1/
- Episodes 22+ → https://crossroadsadventist.github.io/crossroads-season-2/

So the season players stay the single home of each MP3, and this page just
points at them. Same player design as the season pages (Play All, seek,
auto-advance, remembered position, MediaSession). Resume position is saved
under the `crossroads-all` localStorage key, separate from the season pages.

## Adding a future episode

1. Finish the episode in its season player first (master + push there).
2. Re-run `python3 build_combined.py` in this folder — it re-reads the
   EPISODES arrays from the Season 1 and Season 2 player `index.html` files
   and rebuilds this page's `index.html` (it also corrects Episode 16's
   duration to 26:07, the v2 master length — the Season 1 page still lists
   24:55).
3. Commit + push. Pages rebuilds automatically.

Episode numbers run continuously across seasons (Season 1 = 1–21, Season 2
starts at 22) — never restart numbering at 1 for a new season.
