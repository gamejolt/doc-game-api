# Users - Auth

Authenticates the user's information. This should be done before you make any calls for the user, to
make sure the user's credentials (username and token) are valid.

## URL Endpoint

```
/users/auth/
```

## Parameters

| Name         | Required? | Type     | Description          |
| ------------ | --------- | -------- | -------------------- |
| `game_id`    | Yes       | `string` | The ID of your game. |
| `username`   | Yes       | `string` | The user's username. |
| `user_token` | Yes       | `string` | The user's token.    |

## Returns

| Name      | Type      | Description                                                                                                                                |
| --------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| `success` | `boolean` | Whether the request succeeded or failed. <br> **Example**: `true`                                                                          |
| `message` | `string`  | If the request was not successful, this contains the error message. <br> **Example**: `No user could be found matching these credentials.` |

## Syntax

```
/users/auth?game_id=xxxxx&username=test&user_token=12a45z
```

## Version history

| Version | Description          |
| ------- | -------------------- |
| 1.0     | First implementation |
