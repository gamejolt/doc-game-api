# Data Store - Get Keys

## Description

Returns all the keys in either the game's global data store, or all the keys in a user's data store.

## URL Endpoint

```
/data-store/get-keys/
```

## Parameters

#### game_id
> Type: `string`
>
> Required: Yes
>
> The ID of your game.

#### pattern
> Type: `string`
>
> Required: No
>
> The pattern to apply to the key names in the data store.

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
> Indicates wether the call was successful.
>
> __Example__: `true`

_These values get returned if the request was not successful:_

#### message
> Type: `string`
>
> If the request was not successful, this contains the error message.
>
> __Example__: `No such user could be found.`

_These values get returned if the request was successful:_

#### key
> Type: `string`
>
> The name of the key. This function will return all the keys for this particular data store.
>
> __Example__: `keyname`

## Remarks:

- If you apply a pattern to the request, only keys with their keyname applying to the pattern will get returned. The placeholder char for the pattern is `*`.
- If you pass in the user information this function will return all the keys in a user's data store. If you leave the user information empty, it will return all the keys in the game's global data store.
- This request will return a list of the `key` value, this means the `key` return value can appear more than once.

## Syntax:

```
/data-storage/get-keys/?game_id=xxxxx
/data-storage/get-keys/?game_id=xxxxx&pattern=save|*
/data-storage/get-keys/?game_id=xxxxx&username=myusername&user_token=mytoken
/data-storage/get-keys/?game_id=xxxxx&pattern=save|*&username=myusername&user_token=mytoken
```

## Version history

Version		 | Description
---			 | ---
1.2			 | Implemented the `pattern` parameter.
1.0			 | First implementation