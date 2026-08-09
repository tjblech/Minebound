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


## Visual style
This version uses a more restrained dark industrial UI style:
- lower-saturation palette
- squarer controls
- less gradient/glassmorphism
- cleaner, less emoji-heavy navigation


## Windows 98 / shareware restyle
This build uses a faux late-90s desktop-game interface:
- classic beveled Windows controls
- title bars and taskbar-style navigation
- red LED-style counters
- classic Minesweeper board cells and number colors
- dialog-box perk drafts
- Control Panel-style upgrade cards
- subtle titlebar corruption on anomaly floors
- reduced emoji use and small utility-style glyphs


## v4 gameplay/readability fixes
- Compact single-window run layout for phones.
- Proper Windows-style run-terminated dialog.
- All actual mines are revealed when a run ends.
- Incorrect player flags are crossed out after a run ends.
- Live flags are explicitly treated as unconfirmed guesses.
- Every generated board is programmatically validated: each clue is recomputed from its neighboring mines and mine totals are checked before the board is accepted.


## v1.1 gameplay-screen correction
- compact classic Minesweeper HUD with mine counter, integrity counter, and reset face
- perks and log moved into separate Windows-style dialogs
- death now opens a Windows error dialog instead of leaving a dead dashboard
- post-death board reveals all actual mines
- correctly flagged mines stay flagged; incorrect flags become red X marks
- generated clue counts are re-verified against the actual mine map
- compact mobile layout better suited to an iPhone screen

Important: while a run is active, flags/marks are player guesses. A clue of 2 may temporarily have three marked squares around it if one of those marks is wrong. The clue always represents actual hidden mines, not the number of player marks.
