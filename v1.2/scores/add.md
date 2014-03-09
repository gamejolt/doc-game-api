# Scores - Add

[GameJolt API](../../index.md) > [Scores](index.md) > __Add__

## Description

Adds a score for a user or guest.

## URL Endpoint

```
/scores/add/
```

## Parameters

#### game_id
> Type: `string`
>
> Required: Yes
>
> The ID of your game.

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

#### guest
> Type: `string`
>
> Required: No
>
> The guest's name.

#### score
> Type: `string`
>
> Required: Yes
>
> This is a string value associated with the score. __Example__: `234 Jumps`.

#### sort
> Type: `integer`
>
> Required: Yes
>
> This is a numerical sorting value associated with the score. All sorting will work off of this number. __Example__: `234`.

#### extra_data
> Type: `string`
>
> Required: No
>
> If there's any extra data you would like to store (as a string), you can use this variable.

#### table_id
> Type: `integer`
>
> Required: No
>
> The ID of the high score table that you want to submit to.

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

## Remarks

- You can either store a score for a user or a guest. If you're storing for a user, you must pass in the `username` and `user_token` parameters. If you're storing for a guest, you must pass in the `guest` parameter.
- The `extra_data` value is only retrievable through the API and your game's dashboard. It's never displayed publicly to users on the site. If there is other data associated with the score such as time played, coins collected, etc, you should definitely include it. It will be helpful in a case where you believe a gamer has illegitimately achieved a high score.
- If `table_id` is left blank the score will be submitted to the primary high score table.

## Syntax

```
/scores/add/?game_id=xxxxx&username=myusername&user_token=mytoken&score=234 Jumps&sort=234
/scores/add/?game_id=xxxxx&username=myusername&user_token=mytoken&score=234 Jumps&sort=234&extra_data=900&table_id=19834
/scores/add/?game_id=xxxxx&guest=newguestaccount&score=234 Jumps&sort=234
```

## Version history

Version		 | Description
---			 | ---
1.0			 | First implementation