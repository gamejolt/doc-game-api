# Sessions

Sessions are used to tell Game Jolt when a user is playing a game, and what state they are in while playing (active or idle).

## URL Endpoint
```
/sessions/
```

## Requests

Name | Description
--- | ---
[__Open__](https://gamejolt.com/game-api/doc/sessions/open) | Opens a session.
[__Ping__](https://gamejolt.com/game-api/doc/sessions/ping) | Pings a session.
[__Check__](https://gamejolt.com/game-api/doc/sessions/check) | Checks if a session is open.
[__Close__](https://gamejolt.com/game-api/doc/sessions/close) | Closes a session.

## Example Uses

- Get a list of players that are currently playing your game.
- Let others know whether a player is idle or not.

## Remarks

Sessions are currently only shown to other users in Public Chat. In the near future, this data will become more visible on the site. For example:

- Sessions will be shown as live to friends.
- Gamers will be able to see which games they (and their friends) have played and for how long.
- Developers will be able to see the total play time of their games.

## Version history

Version | Description
--- | ---
1.2 | Added user tracking features.
1.0 | First implementation
