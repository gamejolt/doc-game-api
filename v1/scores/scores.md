# Scores - Fetch

[GameJolt API](../../index.md) > [Scores](index.md) > __Fetch__

## Description

Returns a list of scores either for a user or globally for a game.

## URL Endpoint

```
/scores/
```

## Parameters

#### game_id
> Type: `string`
>
> Required: Yes
>
> The ID of your game.

#### limit
> Type: `integer`
>
> Required: No
>
> The number of scores you'd like to return.

#### table_id
> Type: `integer`
>
> Required: No
>
> The ID of the high score table that you want to get high scores for.

#### username
> Type: `string`
>
> Required: No
>
> The user's username.

#### user_token
> Type: `string`
>
> Required: No
>
> The user's token.

## Returns

#### success
> Type: `boolean`
>
> Whether the request succeeded or failed.
>
> __Example__: `true`

_These values get returned if the request was not successful:_

#### message
> Type: `string`
>
> If the request was not successful, this contains the error message.
>
> __Example__: `Unknown fatal error occurred.`

_These values get returned if the request was successful:_
_All values below will get returned for every score that gets returned. They can occur multiple times._

#### score
> Type: `string`
>
> The score string.
>
> __Example__: `234 Jumps`

#### sort
> Type: `integer`
>
> The score's numerical sort value.
>
> __Example__: `234`

#### extra_data
> Type: `string`
>
> Any extra data associated with the score.
>
> __Example__: `900`

#### user
> Type: `string`
>
> If this is a user score, this is the display name for the user.
>
> __Example__: `nilllzz`

#### user_id
> Type: `integer`
>
> If this is a user score, this is the user's ID.
>
> __Example__: `17741`

#### guest
> Type: `string`
>
> If this is a guest score, this is the guest's submitted name.
>
> __Example__: `newguestname`

#### stored
> Type: `string (date)`
>
> Returns when the score was logged by the user.
>
> __Example__: `1 week ago`

## Remarks

- The default value for `limit` is `10` scores. The maximum amount of scores you can retrieve is `100`.
- If `table_id` is left blank the scores from the primary high score table will be returned.
- Only pass in the `username` and `user_token` if you would like to retrieve scores for just that user. Leave the user information blank to retrieve all scores.

## Syntax

```
/scores/?game_id=xxxxx&limit=10&table_id=12345
/scores/?game_id=xxxxx&limit=1&table_id=12345&username=myusername&user_token=mytoken
```

## Version history

Version		 | Description
---			 | ---
1.0			 | First implementation