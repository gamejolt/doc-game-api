# Scores - Fetch

Returns a list of scores either for a user or globally for a game.

## URL Endpoint

```
/scores/
```

## Parameters

| Name         | Required? | Type      | Description                                |
| ------------ | --------- | --------- | ------------------------------------------ |
| `game_id`    | Yes       | `string`  | The ID of your game.                       |
| `limit`      | No        | `integer` | The number of scores you'd like to return. |
| `table_id`   | No        | `integer` | The ID of the score table.                 |
| `username`   | No        | `string`  | The user's username.                       |
| `user_token` | No        | `string`  | The user's token.                          |

## Returns

| Name      | Type      | Description                                                                                                           |
| --------- | --------- | --------------------------------------------------------------------------------------------------------------------- |
| `success` | `boolean` | Whether the request succeeded or failed. <br> **Example**: `true`                                                     |
| `message` | `string`  | If the request was not successful, this contains the error message. <br> **Example**: `Unknown fatal error occurred.` |

All values below will get returned for every score that gets returned. They can occur multiple times.

| Name               | Type            | Description                                                                                                 |
| ------------------ | --------------- | ----------------------------------------------------------------------------------------------------------- |
| `score`            | `string`        | The score string. <br> **Example**: `234 Coins`                                                             |
| `sort`             | `integer`       | The score's numerical sort value. <br> **Example**: `234`                                                   |
| `extra_data`       | `string`        | Any extra data associated with the score. <br> **Example**: `Level 2`                                       |
| `user`             | `string`        | If this is a user score, this is the display name for the user. <br> **Example**: `nilllzz`                 |
| `user_id`          | `integer`       | If this is a user score, this is the user's ID. <br> **Example**: `17741`                                   |
| `guest`            | `string`        | If this is a guest score, this is the guest's submitted name. <br> **Example**: `guestname`                 |
| `stored`           | `string (date)` | Returns when the score was logged by the user. <br> **Example**: `1 week ago`                               |
| `stored_timestamp` | `int`           | Returns the timestamp (in seconds) of when the score was logged by the user. <br> **Example**: `1502471604` |

## Remarks

* The default value for `limit` is `10` scores. The maximum amount of scores you can retrieve is `100`.
* If `table_id` is left blank, the scores from the primary score table will be returned.
* Only pass in the `username` and `user_token` if you would like to retrieve scores for just that user. Leave the user information blank to retrieve all scores.

## Syntax

```
/scores/?game_id=xxxxx&limit=10&table_id=12345
/scores/?game_id=xxxxx&limit=1&table_id=12345&username=myusername&user_token=mytoken
```

## Version history

| Version | Description              |
| ------- | ------------------------ |
| 1.2     | Added _stored_timestamp_ |
| 1.0     | First implementation     |
