# Data Store - Remove

Removes data from the data store.

## URL Endpoint

```
/data-store/remove/
```

## Parameters

Name | Required? | Type | Description
--- | --- | --- | ---
`game_id` | Yes | `string` | The ID of your game.
`key` | Yes | `string` | The key of the data item you'd like to remove.
`username` | No | `string` | The user's username.
`user_token` | No | `string` | The user's token.

## Returns

Name | Type | Description
--- | --- | ---
`success` | `boolean` | Whether the request succeeded or failed. <br> **Example**: `true`
`message` | `string` | If the request was not successful, this contains the error message. <br> **Example**: `Unknown fatal error occurred.`

## Remarks

- If you pass in the user information, the item will be removed from a user's data store. If you leave the user information empty, it will be removed from the game's global data store.

## Syntax

```
/data-store/remove/?game_id=xxxxx&key=keytoremove
/data-store/remove/?game_id=xxxxx&key=keytoremove&username=myusername&user_token=mytoken
```

## Version history

Version		 | Description
---			 | ---
1.0			 | First implementation