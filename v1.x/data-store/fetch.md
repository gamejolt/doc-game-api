# Data Store - Fetch

Returns data from the data store.

## URL Endpoint

```
/data-store/
```

## Parameters

| Name         | Required? | Type     | Description                                   |
| ------------ | --------- | -------- | --------------------------------------------- |
| `game_id`    | Yes       | `string` | The ID of your game.                          |
| `key`        | Yes       | `string` | The key of the data item you'd like to fetch. |
| `username`   | No        | `string` | The user's username.                          |
| `user_token` | No        | `string` | The user's token.                             |

## Returns

| Name      | Type      | Description                                                                                                           |
| --------- | --------- | --------------------------------------------------------------------------------------------------------------------- |
| `success` | `boolean` | Whether the request succeeded or failed. <br> **Example**: `true`                                                     |
| `message` | `string`  | If the request was not successful, this contains the error message. <br> **Example**: `Unknown fatal error occurred.` |
| `data`    | `string`  | If the request was successful, this contains the item's data. <br> **Example**: `Some example data.`                  |

## Remarks

* If you pass in the user information, the data item will be fetched for a user. If you leave the
	user information empty, it will be fetched globally for the game.
* We suggest using the `dump` format for returning data from this call.

## Syntax

```
/data-store/?game_id=xxxxx&key=myglobalkey
/data-store/?game_id=xxxxx&key=myuserkey&username=myusername&user_token=mytoken
```

## Version history

| Version | Description          |
| ------- | -------------------- |
| 1.0     | First implementation |
