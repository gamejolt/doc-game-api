# Trophies - Remove Achieved

Remove a previously achieved trophy for a particular user.

## URL Endpoint

```
/trophies/remove-achieved/
```

## Parameters

| Name         | Required? | Type      | Description                                   |
| ------------ | --------- | --------- | --------------------------------------------- |
| `game_id`    | Yes       | `string`  | The ID of your game.                          |
| `username`   | Yes       | `string`  | The user's username.                          |
| `user_token` | Yes       | `string`  | The user's token.                             |
| `trophy_id`  | Yes       | `integer` | The ID of the trophy to remove from the user. |

## Returns

| Name      | Type      | Description                                                                                                                 |
| --------- | --------- | --------------------------------------------------------------------------------------------------------------------------- |
| `success` | `boolean` | Whether the request succeeded or failed. <br> **Example**: `true`                                                           |
| `message` | `string`  | If the request was not successful, this contains the error message. <br> **Example**: `The user does not have this trophy.` |

## Syntax

```
/trophies/remove-achieved/?game_id=xxxxx&username=myusername&user_token=mytoken&trophy_id=1047
```

## Version history

| Version | Description          |
| ------- | -------------------- |
| 1.2     | First implementation |
