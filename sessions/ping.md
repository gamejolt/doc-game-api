# Sessions - Ping

Pings an open session to tell the system that it's still active. If the session hasn't been pinged within `120 seconds`, the system will close the session and you will have to open another one. It's recommended that you ping every `30 seconds` or so to keep the system from cleaning up your session.

You can also let the system know whether the player is in an `active` or `idle` state within your game through this call.

## URL Endpoint

```
/sessions/ping/
```

## Parameters

Name         | Required? | Description
---          | ---       | ---
`game_id`    | required  | The ID of your game.
`username`   | required  | The username of the user.
`user_token` | required  | The user's token.
`status`     | optional  | Can be `active` or `idle`. The session starts off in an `active` state.

## Returns

`success` or `failure`.