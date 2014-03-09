# Sessions - Close

[GameJolt API](../../index.md) > [Sessions](index.md) > __Close__

## Description

Closes the active session.

## URL Endpoint

```
/sessions/close/
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
/sessions/close/?game_id=xxxxx&username=myusername&user_token=mytoken
```

## Version history

Version		 | Description
---			 | ---
1.0			 | First implementation