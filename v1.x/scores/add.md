# Scores - Add

Adds a score for a user or guest.

## URL Endpoint

```
/scores/add/
```

## Parameters

| Name         | Required? | Type      | Description                                                                                                               |
| ------------ | --------- | --------- | ------------------------------------------------------------------------------------------------------------------------- |
| `game_id`    | Yes       | `string`  | The ID of your game.                                                                                                      |
| `username`   | No        | `string`  | The user's username.                                                                                                      |
| `user_token` | No        | `string`  | The user's token.                                                                                                         |
| `guest`      | No        | `string`  | The guest's name.                                                                                                         |
| `score`      | Yes       | `string`  | This is a string value associated with the score. **Example**: `500 Points`                                               |
| `sort`       | Yes       | `integer` | This is a numerical sorting value associated with the score. All sorting will be based on this number. **Example**: `500` |
| `extra_data` | No        | `string`  | If there's any extra data you would like to store as a string, you can use this variable.                                 |
| `table_id`   | No        | `integer` | The ID of the score table to submit to.                                                                                   |

## Returns

| Name      | Type      | Description                                                                                                           |
| --------- | --------- | --------------------------------------------------------------------------------------------------------------------- |
| `success` | `boolean` | Whether the request succeeded or failed. <br> **Example**: `true`                                                     |
| `message` | `string`  | If the request was not successful, this contains the error message. <br> **Example**: `Unknown fatal error occurred.` |

## Remarks

* You can either store a score for a user or a guest. If you're storing for a user, you must pass in
	the `username` and `user_token` parameters. If you're storing for a guest, you must pass in the
	`guest` parameter.
* The `extra_data` value is only retrievable through the API and your game's dashboard. It's never
	displayed publicly to users on the site. If there is other data associated with the score such as
	time played, coins collected, etc., you should definitely include it. It will be helpful in cases
	where you believe a gamer has illegitimately achieved a high score.
* If `table_id` is left blank, the score will be submitted to the primary high score table.

## Syntax

```
/scores/add/?game_id=xxxxx&username=myusername&user_token=mytoken&score=234 Jumps&sort=234
/scores/add/?game_id=xxxxx&username=myusername&user_token=mytoken&score=234 Jumps&sort=234&extra_data=900&table_id=19834
/scores/add/?game_id=xxxxx&guest=newguestaccount&score=234 Jumps&sort=234
```

## Errors

| Affected parameter                  | Description                                                       | Error `message`                                                     |
| ----------------------------------- | ----------------------------------------------------------------- | --------------------------------------------------------------------|
| `guest` / `table_id`                | Tried to add guest score to table that doesn't allow guest scores | Guests are not allowed to enter scores for this game.               |
| `username` / `user_token` / `guest` | Have to either use user info or the `guest` parameter             | You must pass in a user/guest for this score.                       |
| `score`                             | `score` parameter not passed in                                   | You must enter a score.                                             |
| `sort`                              | `sort` parameter not passed in or not numeric                     | You must enter a sort value for this score, and it must be numeric. |
| _`-none-`_                          | Failed to add score, usually not a user error                     | Unknown error has occured                                           |

_Notes:_
* _Even though the error suggests otherwise, the "are guest scores allowed" setting can be adjusted per score table, not per game._
* _The generic error while adding scores is NOT the same as the global "something went wrong" error message._

## Version history

| Version | Description          |
| ------- | -------------------- |
| 1.0     | First implementation |
