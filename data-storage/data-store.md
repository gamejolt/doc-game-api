# Data Store - Fetch

Returns data from the `Data Store`.

Note that we suggest using the `dump` format for returning data from this call.

## URL Endpoint

```
/data-store/
```

## Parameters

Name         | Required? | Description
---          | ---       | ---
`game_id`    | required  | The ID of your game.
`key`        | required  | The key of the data item you'd like to fetch.
`username`   | optional  | The user's username.
`user_token` | optional  | The user's token.

If you pass in the user information, this item will be fetched for a user. If you leave the user information empty, it will be fetched globally for the game.

## Returns

The item's data.

We suggest using the `dump` format for returning data from this call.