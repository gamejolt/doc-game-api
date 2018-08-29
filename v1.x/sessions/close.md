# Sessions - Close

Closes the active session.

## URL Endpoint

```
/sessions/close/
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
| `success` | `boolean` | Whether the request succeeded or failed. <br> **Example**: `true`                                                     |
| `message` | `string`  | If the request was not successful, this contains the error message. <br> **Example**: `Unknown fatal error occurred.` |

## Syntax

```
/sessions/close/?game_id=xxxxx&username=myusername&user_token=mytoken
```

## Errors

| Affected parameter | Description                                                                                | Error `message`                                          |
| ------------------ | ------------------------------------------------------------------------------------------ | -------------------------------------------------------- |
| _`-none-`_         | No open session exists, [open](https://gamejolt.com/game-api/doc/sessions/open) a new one! | Could not find an open session. You must open a new one. |

## Version history

| Version | Description          |
| ------- | -------------------- |
| 1.0     | First implementation |
