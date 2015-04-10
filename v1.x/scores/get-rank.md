# Scores - Get Rank

Returns the rank of a particular score on a score table.

## URL Endpoint

```
/scores/get-rank/
```

## Parameters

Name | Required? | Type | Description
--- | --- | --- | ---
`game_id` | Yes | `string` | The ID of your game.
`sort` | Yes | `integer` | This is a numerical sorting value that is represented by a rank on the score table.
`table_id` | No | `integer` | The ID of the score table from which you want to get the rank.

## Returns

Name | Type | Description
--- | --- | ---
`success` | `boolean` | Whether the request succeeded or failed. <br> **Example**: `true`
`message` | `string` | If the request was not successful, this contains the error message. <br> **Example**: `Unknown fatal error occurred.`
`rank` | `integer` | The rank of the score on the score table. <br> **Example**: `99`

## Remarks

- If `table_id` is left blank, the ranks from the primary high score table will be returned.
- If the score is not represented by any rank on the score table, the request will return the rank that is closest to the requested score.

## Syntax

```
/scores/get-rank/?game_id=xxxxx&sort=20&table_id=12345
```

## Version history

Version		 | Description
---			 | ---
1.2			 | First implementation