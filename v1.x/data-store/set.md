# Data Store - Set

Sets data in the data store.

## URL Endpoint

```
/data-store/set/
```

## Parameters

| Name       | Required? | Type     | Description                                 |
| ---------- | --------- | -------- | ------------------------------------------- |
| game_id    | Yes       | `string` | The ID of your game.                        |
| key        | Yes       | `string` | The key of the data item you'd like to set. |
| data       | Yes       | `string` | The data you'd like to set.                 |
| username   | No        | `string` | The user's username.                        |
| user_token | No        | `string` | The user's token.                           |

## Returns

| Name    | Type      | Description                                                                                                           |
| ------- | --------- | --------------------------------------------------------------------------------------------------------------------- |
| success | `boolean` | Whether the request succeeded or failed. <br> **Example**: `true`                                                     |
| message | `string`  | If the request was not successful, this contains the error message. <br> **Example**: `Unknown fatal error occurred.` |

## Remarks

* If you pass in the user information, this item will be set in a user's data store. If you
	leave the user information empty, it will be set in the game's global data store.
* You can create new data store items by passing in a `key` that doesn't yet exist in the data
	store.

## Syntax

```
/data-store/set/?game_id=xxxxx&key=mykey&data=newdata
/data-store/set/?game_id=xxxxx&key=mykey&data=newdata&username=myusername&user_token=mytoken
```

## Errors

| Affected parameter | Description                    | Error `message`                                                          |
| ------------------ | ------------------------------ | ------------------------------------------------------------------------ |
| `key`              | `key` parameter not passed in  | You must enter the key for the item you would like to retrieve data for. |
| `data`             | `data` parameter not passed in | You must enter data with the request.                                    |

## Version history

| Version | Description          |
| ------- | -------------------- |
| 1.0     | First implementation |
