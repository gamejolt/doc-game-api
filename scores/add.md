# Scores - Add

Adds a score for a user or guest.

## URL Endpoint

```
/scores/add/
```

## Parameters

Name         | Required? | Description
---          | ---       | ---
`game_id`    | required  | The ID of your game.
`username`   | optional  | The username of the user. _Leave blank if you're storing for a guest._
`user_token` | optional  | The user's token. _Leave blank if you're storing for a guest._
`guest`      | optional  | The guest's name. _Leave blank if you're storing for a user._
`score`      | required  | This is a string value associated with the score. Example: "234 Jumps".
`sort`       | required  | This is a numerical sorting value associated with the score. All sorting will work off of this number. Example: "234".
`extra_data` | optional  | If there's any extra data you would like to store (as a string), you can use this variable. Note that this is only retrievable through the API and your game's dashboard. It's never displayed publicly to users on the site. If there is other data associated with the score such as time played, coins collected, etc, you should definitely include it. It will be helpful in a case where you believe a gamer has illegitimately achieved a high score.
`table_id`   | optional  | The ID of the high score table that you want to submit to. _If left blank the score will be submitted to the primary high score table._

You can either store a score for a user or a guest. If you're storing for a user, you must pass in the `username` and `user_token` parameters. If you're storing for a guest, you must pass in the `guest` parameter.

## Returns

`success` or `failure`.