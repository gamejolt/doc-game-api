# Sessions - Ping

Pings an open session to tell the system that it's still active. If the session hasn't been pinged within 120 seconds, the system will close the session and you will have to open another one. It's recommended that you ping about every 30 seconds or so to keep the system from clearing out your session.

You can also let the system know whether the player is in an active or idle state within your game.

## URL Endpoint

```
/sessions/ping/
```

## Parameters

Name | Required? | Type | Description
--- | --- | --- | ---
game_id | Yes | `string` | The ID of your game.
username | Yes | `string` | The user's username.
user_token | Yes | `string` | The user's token.
status | No | `string` | Sets the status of the session.

### Valid Values for `value`
 
Value | Description
---	| ---
active | Sets the session to the `active` state.
idle | Sets the session to the `idle` state.

## Returns

Name | Type | Description
--- | --- | ---
success | `boolean` | Whether the request succeeded or failed. <br> **Example**: `true`
message | `string` | If the request was not successful, this contains the error message. <br> **Example**: `Unknown fatal error occurred.`

## Syntax

```
/sessions/ping/?game_id=xxxxx&username=myusername&user_token=mytoken
/sessions/ping/?game_id=xxxxx&username=myusername&user_token=mytoken&status=active
```

## Version history

Version		 | Description
---			 | ---
1.0			 | First implementation