# Sessions - Check

[GameJolt API](../index.md) > [Sessions](index.md) > __Check__

## Description

Checks to see if there is an open session for the user. Can be used to see if a particular user account is active in the game.

## URL Endpoint

```
/sessions/check/
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
> Whether the user's session is open.
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
/sessions/check/?game_id=xxxxx&username=myusername&user_token=mytoken
```

## Version history

Version		 | Description
---			 | ---
1.2			 | First implementation
