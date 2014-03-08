# Scores - Tables

Returns a list of high score tables for a game.

## URL Endpoint

```
/scores/tables/
```

## Parameters

Name         | Required? | Description
---          | ---       | ---
`game_id`    | required  | The ID of your game.

# Returns

Field         | Description
---           | ---
`id`          | The high score table identifier.
`name`        | The developer-defined high score table name.
`description` | The developer-defined high score table description.
`primary`     | Whether or not this is the default high score table. High scores are submitted to the primary table by default.