# Users - Auth

[GameJolt API](../index.md) > [Users](index.md) > __Auth__

## Description

Authenticates the user's information. This should be done before you make any calls for the user, to make sure that the user's credentials (`username`/`token`) are valid.

## URL Endpoint

```
/users/auth/
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
> The username of the user.

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
> __Example__: `No such user with the credentials passed in could be found.`


## Remarks

Not all calls require the user to enter a valid user-token combination.

## Syntax

```
/users/?game_id=xxxxx&username=test&user_token=12a45z
```

## Version history

Version		 | Description
---			 | ---
1.0			 | First implementation