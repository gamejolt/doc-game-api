# Friends

Returns the list of a user's friends.

## URL Endpoint

```
/friends/
```

## Parameters

| Name         | Required? | Type     | Description          |
| ------------ | --------- | -------- | -------------------- |
| `game_id`    | Yes       | `string` | The ID of your game. |
| `username`   | Yes       | `string` | The user's username. |
| `user_token` | Yes       | `string` | The user's token.    |

## Returns

| Name        | Type      | Description                                                                                                           |
| ----------- | --------- | --------------------------------------------------------------------------------------------------------------------- |
| `success`   | `boolean` | Whether the request succeeded or failed. <br> **Example**: `true`                                                     |
| `message`   | `string`  | If the request was not successful, this contains the error message. <br> **Example**: `Unknown fatal error occurred.` |
| `friend_id` | `integer` | The friend's user ID. <br> **Example**: `123`                                                                         |

## Syntax

```
/friends/?game_id=xxxxx&username=test&user_token=12a45z
```

## Version history

| Version | Description          |
| ------- | -------------------- |
| 1.2     | First implementation |
