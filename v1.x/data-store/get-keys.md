# Data Store - Get Keys

Returns either all the keys in the game's global data store, or all the keys in a user's data store.

## URL Endpoint

```
/data-store/get-keys/
```

## Parameters

Name | Required? | Type | Description
--- | --- | --- | ---
`game_id` | Yes | `string` | The ID of your game.
`pattern` | No | `string` | The pattern to apply to the key names in the data store.
`username` | No | `string` | The user's username.
`user_token` | No | `string` | The user's token.

## Returns

Name | Type | Description
--- | --- | ---
`success` | `boolean` | Whether the request succeeded or failed. <br> **Example**: `true`
`message` | `string` | If the request was not successful, this contains the error message. <br> **Example**: `No such user could be found.`
`key` | `string` | The name of the key. This function will return all the keys for this particular data store. <br> **Example**: `keyname`

## Remarks

- If you apply a pattern to the request, only keys with applicable key names will be returned. The placeholder character for patterns is `*`.
- If you pass in the user information, this function will return all the keys in a user's data store. If you leave the user information empty, it will return all the keys in the game's global data store.
- This request will return a list of the `key` values. The `key` return value can appear more than once.

## Syntax

```
/data-store/get-keys/?game_id=xxxxx
/data-store/get-keys/?game_id=xxxxx&pattern=save|*
/data-store/get-keys/?game_id=xxxxx&username=myusername&user_token=mytoken
/data-store/get-keys/?game_id=xxxxx&pattern=save|*&username=myusername&user_token=mytoken
```

## Version history

Version | Description
--- | ---
1.2 | Implemented the `pattern` parameter.
1.0 | First implementation