# Sessions - Open

Opens a game session for a particular user and allows you to tell Game Jolt that a user is playing your game. You must ping the session to keep it active and you must close it when you're done with it.

## URL Endpoint

```
/sessions/open/
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

## Remarks

* You can only have one open session for a user at a time. If you try to open a new session while one is running, the system will close out the current one before opening the new one.

## Syntax

```
/sessions/open/?game_id=xxxxx&username=myusername&user_token=mytoken
```

## Version history

| Version | Description          |
| ------- | -------------------- |
| 1.0     | First implementation |
