# Scores

Game Jolt supports multiple online score tables, or scoreboards, per game. You are able to, for example, have a score table for each level in your game, or a table for different scoring metrics. Gamers will keep coming back to try to achieve the highest scores for your game.

With multiple formatting and sorting options, the system is quite flexible. You are also able to include extra data with each score. If there is other data associated with the score such as time played, coins collected, etc., you should definitely include it. It will be helpful in cases where you believe a gamer has illegitimately achieved a high score. 

## URL Endpoint

```
/scores/
```

## Requests

Name | Description
---	| ---
[**Add**](add.md) | Adds a score.
[**Get Rank**](get-rank.md) | Gets a rank for a specific score.
[**Fetch**](fetch.md) | Fetches scores from a score table.
[**Tables**](tables.md)	| Fetches a list of score tables.

## Example Uses

- Highscore tables for each level of a game.
- Global ranking list for all players.

## Remarks

- Extra data you include is not shown anywhere on the site, and you are limited only by your own imagination!

## Version history

Version		| Description
---			| ---
1.2			| Implemented the `Get Rank` request.
1.0			| First implementation
