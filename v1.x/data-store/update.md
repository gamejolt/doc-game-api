# Data Store - Update

Updates data in the data store.

## URL Endpoint

```
/data-store/update/
```

## Parameters

| Name         | Required? | Type                  | Description                                                                   |
| ------------ | --------- | --------------------- | ----------------------------------------------------------------------------- |
| `game_id`    | Yes       | `string`              | The ID of your game.                                                          |
| `key`        | Yes       | `string`              | The key of the data item you'd like to update.                                |
| `username`   | No        | `string`              | The user's username.                                                          |
| `user_token` | No        | `string`              | The user's token.                                                             |
| `operation`  | Yes       | `string`              | The operation you'd like to perform.                                          |
| `value`      | Yes       | `string` or `integer` | The value you'd like to apply to the data store item. <br> (See table below.) |

### Valid Values for `operation`

| Value      | Description                                              |
| ---------- | -------------------------------------------------------- |
| `add`      | Adds the `value` to the current data store item.         |
| `subtract` | Substracts the `value` from the current data store item. |
| `multiply` | Multiplies the `value` by the current data store item.   |
| `divide`   | Divides the current data store item by the `value`.      |
| `append`   | Appends the `value` to the current data store item.      |
| `prepend`  | Prepends the `value` to the current data store item.     |

## Returns

| Name      | Type                  | Description                                                                                                                    |
| --------- | --------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| `success` | `boolean`             | Whether the request succeeded or failed. <br> **Example**: `true`                                                              |
| `message` | `string`              | If the request was not successful, this contains the error message. <br> **Example**: `Unknown fatal error occurred.`          |
| `data`    | `string` or `integer` | If the request was successful, this returns the new value of the data item. <br> **Example**: `New data with appended string.` |

## Remarks

* You can only perform mathematic operations on numerical data.
* If you pass in the user information, this function will return all the keys in a user's data
	store. If you leave the user information empty, it will return all the keys in the game's global
	data store.

## Syntax

```
/data-store/update/?game_id=xxxxx&key=mykey&operation=append&value=add to string
/data-store/update/?game_id=xxxxx&key=mykey&operation=divide&value=2&username=myusername&user_token=mytoken
```

## Errors

| Affected parameter    | Description                                                | Error `message`                                                                                |
| --------------------- | ---------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `key`                 | `key` parameter not passed in                              | You must enter the key for the item you would like to retrieve data for.                       |
| `key`                 | No data store item exists for `key`                        | There is no item with the key passed in: &lt;key>                                              |
| `operation`           | `operation` parameter not passed in                        | You must enter an operation with the request.                                                  |
| `operation`           | Invalid operation passed in                                | Operation must be add, subtract, multiply, divide, append or prepend.                          |
| `value`               | `value` parameter not passed in                            | You must enter an value with the request.                                                      |
| `operation`           | Mathmatical operation with non-numerical data store item   | Mathematical operations require the pre-existing data stored to also be numeric.               |
| `value` / `operation` | Mathmatical operation with non-numerical `value` parameter | Value must be numeric if operation is mathematical.                                            |
| `value`               | Division by zero (0)                                       | GAME JOLT STOP: 0x00000019 (0x00000000, 0xC00E0FF0, 0xFFFFEFD4, 0xC0000000) UNIVERSAL_COLLAPSE |

## Version history

| Version | Description          |
| ------- | -------------------- |
| 1.0     | First implementation |
