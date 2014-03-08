# Scores - Fetch

Returns a list of scores either for a user or globally for a game.

## URL Endpoint

```
/v1/scores/
```

## Parameters

Name         | Required? | Description
---          | ---       | ---
`game_id`    | required  | The ID of your game.
`limit`      | optional  | The number of scores you'd like to return. The default value is `10 scores`. The maximum amount of scores you can retrieve is `100`.
`table_id`   | optional  | The ID of the high score table that you want to get high scores for. If left blank the scores from the primary high score table will be returned.
`username`   | optional  | The username of the user.
`user_token` | optional  | The user's token.

Only pass in the `username` and `user_token` if you would like to retrieve scores for just that user. Leave the user information blank to retrieve all scores.

## Returns

Field        | Description
---          | ---
`score`      | The score string.
`sort`       | The score's numerical sort value.
`extra_data` | Any extra data associated with the score.
`user`       | If this is a user score, this is the display name for the user.
`user_id`    | If this is a user score, this is the user's ID.
`guest`      | If this is a guest score, this is the guest's submitted name.
`stored`     | Returns when the score was logged by the user.