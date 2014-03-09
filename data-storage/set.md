# Data Store - Set

## Description

Sets data in the `data store`.

## URL Endpoint

```
/data-store/set/
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
> The key of the data item you'd like to set.

#### data
> Type: `string`
>
> Required: Yes
>
> The data you'd like to set. Note that this should be a string, but can be sent through a `POST` request.

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
> Indicates wether the request was successful.
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
/data-store/set/?game_id=xxxxx&key=mykey&data=newdata
/data-store/set/?game_id=xxxxx&key=mykey&data=newdata&username=myusername&user_token=mytoken
```

## Version history

Version		 | Description
---			 | ---
1.0			 | First implementation