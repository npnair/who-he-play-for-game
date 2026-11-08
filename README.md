# Who He Play For?

A daily NBA guessing game. Every day there's one famous (or not so famous) moment from NBA history. Everyone in the scene is blacked out except one player in green. Your job is to name him.

### ▶ [Play it here](https://who-he-play-for.naveenpradeepnair.workers.dev)

<img src="assets/start-screen.png" alt="Who He Play For? start screen" width="480">

## How to play

- One new moment unlocks each day. Missed a day? Past days stay open.
- Start typing a name or nickname and pick the player from the suggestions. You get **3 guesses**.
- Stuck? There are **4 hints**: the arena, the season, the game, and a teammate. Each one costs 15 points.
- The clock counts up. After 10 seconds you lose 1 point per second, and if you get it in under 10 seconds you get a +20 bonus. Max score is 120.
- When you're done, copy your result and send it to your friends (no spoilers).

## Difficulty

The difficulty goes up through the week:

| Day | Difficulty | What that means |
|---|---|---|
| Mon, Tue | Easy | A star player in a moment every fan knows |
| Wed, Thu | Medium | A famous moment, but the player isn't a superstar |
| Fri, Sat | Hard | A star player in a moment most fans forget |
| Sun | Impossible | A coach or deep bench player in a moment almost nobody remembers |

## Built with

- HTML, CSS, and JavaScript, with no frameworks
- Hosted on Cloudflare Workers
- Name search that handles misspellings and nicknames ("antetokumpo," "Greek Freak," and "MJ" all work)

## Status

Currently in testing with a small group. New moments are added every week.

---

*Fan project. Not affiliated with or endorsed by the NBA or any team.*
