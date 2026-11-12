# Green Bean

**Name the player in green.** A daily NBA guessing game. Every day there are three moments from NBA history: one Easy, one Medium, and one Hard. Everyone in the scene is blacked out except one player in green. Your job is to name him.

### ▶ [Play it here](https://playgreenbean.com)

<img src="assets/start-screen.png" alt="Green Bean start screen" width="480">

## How to play

- Pick a level and play. You can play all three, in any order. Missed a day? Past days stay open.
- Start typing a name or nickname and pick the player from the suggestions. You get **3 guesses**.
- Stuck? There are **4 hints**: the arena, the season, the game, and a teammate. Each one costs 15 points.
- The clock counts up. After 10 seconds you lose 1 point per second, and if you get it in under 10 seconds you get a +20 bonus. Each level is worth up to 120, so a full day is out of 360.
- When you're done, copy your result and send it to your friends (no spoilers).

## Levels

| Level | What that means |
|---|---|
| 🟢 Easy | A star player in a moment every fan knows |
| 🟡 Medium | A famous moment, but the player isn't a superstar |
| 🔴 Hard | A star in a moment most fans forget, or a coach or role player almost nobody remembers |

## How the puzzles are made

Each puzzle comes from a small Python pipeline:

1. **Pick a moment and a photo.** This part is still done by hand, because choosing moments fans will recognize is the fun part.
2. **`silhouette.py`** finds every person in the photo with a pretrained person-segmentation model, then uses **SAM** (Meta's Segment Anything) to cut out the exact player I click on. OpenCV turns everyone else into black outlines and the target into the green silhouette. About 20 seconds per photo.
3. **`add_puzzle.py`** takes the scene, the answer and the hints, puts the puzzle on the next open day for its level, adds the player to the name search, and pushes it. Cloudflare puts it live about a minute later.

Next up: a data-driven "moment finder" that ranks famous NBA moments using play-by-play data and fame signals, to suggest new puzzles.

## Built with

- HTML, CSS, and JavaScript, with no frameworks
- Python, OpenCV, and pretrained segmentation models (u2net, SAM) for the puzzle pipeline
- Hosted on Cloudflare Workers
- Name search that handles misspellings and nicknames ("antetokumpo," "Greek Freak," and "MJ" all work)

## Status

Currently in testing with a small group. New moments are added every week.

---

*Fan project. Not affiliated with or endorsed by the NBA or any team.*
