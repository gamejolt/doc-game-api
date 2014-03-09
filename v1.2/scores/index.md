# Scores

[GameJolt API](../index.md) > __Scores__

## Description

Game Jolt supports multiple online high score tables per game. With this you are able to, for example, have a score board for each level in your game. Gamers battle to achieve the highest scores for your game. With multiple formatting and sorting options, the system is quite flexible.
You are able to include extra data with each score that you submit to Game Jolt. If there is other data associated with the score such as time played, coins collected, etc, you should definitely include it. It will be helpful in a case where you believe a gamer has illegitimately achieved a high score.

## URL Endpoint

```
/scores/
```

## Requests

Name							| Description
---								| ---
[__Add__](add.md)				| Adds a score.
[__Get Rank__](get-rank.md)		| Gets a rank for a specific score.
[__Fetch__](scores.md)			| Fetches scores from a score table.
[__Tables__](tables.md)			| Fetches a list of score tables.

## Example uses

- Highscore tables for each level of a game.
- Global ranking list for all players.

## Remarks

- Much like the Data Store system, the extra data is not shown anywhere on the site, and you are limited only by your own imagination!

## Version history

Version		| Description
---			| ---
1.2			| Implemented the `Get Rank` request.
1.0			| First implementation