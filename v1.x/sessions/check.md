# Sessions - Check

Checks to see if there is an open session for the user. Can be used to see if a particular user
account is active in the game.

## URL Endpoint

```
/sessions/check/
```

## Parameters

| Name         | Required? | Type     | Description          |
| ------------ | --------- | -------- | -------------------- |
| `game_id`    | Yes       | `string` | The ID of your game. |
| `username`   | Yes       | `string` | The user's username. |
| `user_token` | Yes       | `string` | The user's token.    |

## Returns

| Name      | Type      | Description                                                                                                           |
| --------- | --------- | --------------------------------------------------------------------------------------------------------------------- |
| `success` | `boolean` | Whether an open session exists <br> **Example**: `true`                                                               |
| `message` | `string`  | If the request was not successful, this contains the error message. <br> **Example**: `Unknown fatal error occurred.` |

## Remarks

* This endpoint returns `false` for the `success` field when no open session exists.  
  That behaviour is different from other endpoints which use this field to indicate an error state.

## Syntax

```
/sessions/check/?game_id=xxxxx&username=myusername&user_token=mytoken
```

## Version history

| Version | Description          |
| ------- | -------------------- |
| 1.2     | First implementation |
