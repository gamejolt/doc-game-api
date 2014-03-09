# Scores - Get Rank

[GameJolt API](../index.md) > [Scores](index.md) > __Get Rank__

## Description

Returns the rank inside a score table for a particular score.

## URL Endpoint

```
/scores/get-rank/
```

## Parameters

#### game_id
> Type: `string`
>
> Required: Yes
>
> The ID of your game.

#### sort
> Type: `integer`
>
> Required: Yes
>
> This is a numerical sorting value that is represented by a rank in the score table.

#### table_id
> Type: `integer`
>
> Required: No
>
> The ID of the high score table that you want to get the rank from.

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

#### rank
> Type: `integer`
>
> The rank representing the score in the score table.
>
> __Example__: `132`

## Remarks

- If `table_id` is left blank the ranks from the primary high score table will be returned.
- If the score is not represented by any rank in the score table, the request will return the rank that is closest to the requested score.

## Syntax

```
/scores/get-rank/?game_id=xxxxx&sort=20&table_id=12345
```

## Version history

Version		 | Description
---			 | ---
1.2			 | First implementation