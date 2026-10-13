# Callity

Callity is an independent, non-commercial project by a single developer. Its first tool is **CS2 Scout**.

## CS2 Scout

CS2 Scout is a personal pre-match scouting tool for FACEIT Counter-Strike 2 matches. After the map veto, it analyses the public demos of the opposing players' recent matches on the picked map. It then produces a short report on the situations in which each opponent tends to lose rounds, with simple counter-suggestions. The report is meant to be read during the warm-up.

**How it works**

1. It reads the match lineup and each opponent's recent match history from the FACEIT Data API.
2. It selects a small sample of recent matches on the picked map, up to 12 per player, split evenly between wins and losses.
3. It downloads those demos through the FACEIT Downloads API, parses them locally and keeps only aggregated per-round features. The demo files are deleted after parsing.
4. It compares each player's behaviour in lost and won rounds, grouped by round situation: side, buy type, pistol rounds and so on. Every finding comes with a "k out of n" count.

**Principles**

- It uses only public FACEIT data: the Data API and demos of finished matches.
- It never interacts with the CS2 game client. No memory reading, no screen capture, no Game State Integration.
- All analysis happens before the match starts. There are no in-round assistance features.
- It runs locally on the developer's own PC. There are no user accounts, no server-side redistribution of demos and no paid features.

**Expected usage**

The tool runs only for matches the developer plays, about 25–35 matches per month at roughly 40–60 demo downloads per match. Already-parsed matches are cached and never downloaded twice.

## Status

Early development: data access and parser benchmarking.
