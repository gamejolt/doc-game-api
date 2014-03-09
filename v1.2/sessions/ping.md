# Sessions - Ping

[GameJolt API](../index.md) > [Sessions](index.md) > __Ping__

## Description

Pings an open session to tell the system that it's still active. If the session hasn't been pinged within `120 seconds`, the system will close the session and you will have to open another one. It's recommended that you ping every `30 seconds` or so to keep the system from cleaning up your session.
You can also let the system know whether the player is in an `active` or `idle` state within your game through this call.

## URL Endpoint

```
/sessions/ping/
```

## Parameters

#### game_id
> Type: `string`
>
> Required: Yes
>
> The ID of your game.

#### username
> Type: `string`
>
> Required: Yes
>
> The user's username.

#### user_token
> Type: `string`
>
> Required: Yes
>
> The user's token.

#### status
> Type: `string`
>
> Required: No
>
> Sets the status of the session.
>
> ##### Valid values
> 
> Value		| Description
> ---		| ---
> active	| Sets the session to the `active` state.
> idle   	| Sets the session to the `idle` state.

## Returns

#### success
> Type: `boolean`
>
> Whether the request succeeded or failed.
>
> __Example__: `true`

_These values get returned if the request was not successful:_

#### message
> Type: `string`
>
> If the request was not successful, this contains the error message.
>
> __Example__: `Unknown fatal error occurred.`

## Remarks

## Syntax

```
/sessions/ping/?game_id=xxxxx&username=myusername&user_token=mytoken
/sessions/ping/?game_id=xxxxx&username=myusername&user_token=mytoken&status=active
```

## Version history

Version		 | Description
---			 | ---
1.0			 | First implementation