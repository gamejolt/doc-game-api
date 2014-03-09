# Data Store - Remove

[GameJolt API](../../index.md) > [Data store](../index.md) > Remove

## Description

Removes data from the `data store`.

## URL Endpoint

```
/data-store/remove/
```

## Parameters

#### game_id
> Type: `string`
>
> Required: Yes
>
> The ID of your game.

#### key
> Type: `string`
>
> Required: Yes
>
> The key of the data item you'd like to remove.

#### username
> Type: `string`
>
> Required: No
>
> The user's username.

#### user_token
> Type: `string`
>
> Required: No
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

- If you pass in the user information, this item will be removed from a user's data store. If you leave the user information empty, it will be removed from the game's global data store.

## Syntax

```
/data-store/remove/?game_id=xxxxx&key=keytoremove
/data-store/remove/?game_id=xxxxx&key=keytoremove&username=myusername&user_token=mytoken
```

## Version history

Version		 | Description
---			 | ---
1.0			 | First implementation