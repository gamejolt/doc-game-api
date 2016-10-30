# Data Store - Set

Sets data in the data store.

## URL Endpoint

```
/data-store/set/
```

## Parameters

Name | Required? | Type | Description
--- | --- | --- | ---
game_id | Yes | `string` | The ID of your game.
key | Yes | `string` | The key of the data item you'd like to set.
data | Yes | `string` | The data you'd like to set. Note that this should be a string, but can be sent through a `POST` request.
username | No | `string` | The user's username.
user_token | No | `string` | The user's token.
restriction_username | No | `string` | The user's username.
restriction_user_token | No | `string` | The user's token.

## Returns

Name | Type | Description
--- | --- | ---
success | `boolean` | Whether the request succeeded or failed. <br> **Example**: `true`
message | `string` | If the request was not successful, this contains the error message. <br> **Example**: `Unknown fatal error occurred.`

## Remarks

- If you pass in the user information, this item will be removed from a user's data store. If you leave the user information empty, it will be removed from the game's global data store.
- If you don't pass in `username` and `user_token`, you can use the `restriction_username` and `restriction_user_token` parameters to restrict the writing permissions of this storage item to only that user.
- You can create new data store items by passing in a `key` that doesn't yet exist in the data store.

## Syntax

```
/data-store/set/?game_id=xxxxx&key=mykey&data=newdata
/data-store/set/?game_id=xxxxx&key=mykey&data=newdata&username=myusername&user_token=mytoken
/data-store/set/?game_id=xxxxx&key=mykey&data=newdata&restriction_username=myusername&restriction_user_token=mytoken
```

## Version history

Version | Description
--- | ---
1.2 | Added restriction feature.
1.0 | First implementation