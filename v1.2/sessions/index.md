# Sessions

[GameJolt API](../index.md) > __Sessions__

## Description

Sessions are used to tell Game Jolt when a user is playing a game, and what state they are in while playing (active, or idle).

## URL Endpoint
```
/sessions/
```

## Requests

Name							| Description
---								| ---
[__Open__](open.md)				| Opens a session.
[__Ping__](ping.md)				| Pings a session.
[__Close__](close.md)			| Closes a session.

## Example uses

- Get a list of players that are currently playing your game.
- Let others know whether a player is idle or not.

## Remarks

Sessions are currently only shown to other users in the Public Chat. In the near future, this data will become more visible on the site, for example:

- Sessions will be shown as live activity to friends as Game Jolt becomes social.
- Gamers will be able to see which games they (and their friends) have invested the most time in.
- Developers will be able to see the total play time of their games.

## Version history

Version		| Description
---			| ---
1.2			| Added user tracking features.
1.0			| First implementation