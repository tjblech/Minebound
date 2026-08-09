# Minebound

An offline, installable Minesweeper roguelike PWA.

## Core loop
- Clear endlessly generated Minesweeper boards.
- Every 3 cleared floors, choose 1 of 3 run-only mutation perks.
- Every 5th floor is an Anomaly with a dangerous modifier and boosted rewards.
- Mine hits cost Integrity instead of instantly ending the board.
- Retreat whenever you want to bank the Echoes earned in that run.
- If Integrity reaches 0, the run ends but earned Echoes are still banked.
- Spend Echoes on permanent upgrades.
- Choose a starting perk before each run.
- Export/import your save from the Records screen.

## Controls
Mobile:
- Tap a tile to use the selected Reveal / Flag mode.
- Long-press a tile to flag it.
Desktop:
- Left click reveals.
- Right click flags.
- You can also use the Reveal / Flag buttons.

## iPhone installation
Host the folder on any HTTPS static host, open the site in Safari, then use:
Share > Add to Home Screen

The game stores progress locally on that device in browser/PWA storage.

## Local testing
From this folder:
`python -m http.server 8000`

Then open:
`http://localhost:8000`

Service workers and installability require HTTP/HTTPS, so opening index.html directly is not enough for the full PWA behavior.
