# Data Store - Update

[GameJolt API](../index.md) > [Data store](index.md) > __Update__

## Description

Updates data in the `data store.`

## URL Endpoint

```
/data-store/update/
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
> The key of the data item you'd like to update.

#### operation
> Type: `string`
>
> Required: Yes
>
> The operation that you'd like to perform.
>
> ##### Valid values
>
> Value		 | Description
> ---		 | ---
> add		 | Adds the `value` to the current data store item.
> substract	 | Substracts the `value` from the current data store item.
> multiply	 | Multiplies the `value` with the current data store item.
> divide	 | Divides the current data store item by the `value`.
> append	 | Appends the `value` to the current data store item.
> prepend	 | Prepends the `value` to the current data store item.

#### value
> Type: `string` or `integer` (for mathmatic operations.)
>
> Required: Yes
>
> The value that you'd like to work with on the data store.

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

_These values get returned if the request was successful:_

#### data
> Type: `string` or `integer`
>
> If successful, returns the new value of the data store.
>
> __Example__: `New data with appended string.`

## Remarks

- You can only perform mathematic operations on numeric data.
- If you pass in the user information this function will return all the keys in a user's data store. If you leave the user information empty, it will return all the keys in the game's global data store.

## Syntax

```
/data-store/update/?game_id=xxxxx&key=mykey&operation=append&value=add to string
/data-store/update/?game_id=xxxxx&key=mykey&operation=divide&value=2&username=myusername&user_token=mytoken
```

## Version history

Version		 | Description
---			 | ---
1.0			 | First implementation