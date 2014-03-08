# Data Store - Set

Sets data in the `Data Store`.

## URL Endpoint

```
/data-store/set/
```

## Parameters

Name         | Required? | Description
---          | ---       | ---
`game_id`    | required  | The ID of your game.
`key`        | required  | The key of the data item you'd like to set.
`data`       | required  | The data you'd like to set. Note that this should be a string, but can be sent through a `POST` request.
`username`   | optional  | The user's username.
`user_token` | optional  | The user's token.

If you pass in the user information, this item will be set for a user. If you leave the user information empty, it will be set globally for the game.

Returns
`success` or `failure`.