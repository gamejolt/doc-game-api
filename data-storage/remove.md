# Data Store - Remove

Removes data from the Data Store.

## URL Endpoint

```
/data-store/remove/
```

## Parameters

Name         | Required? | Description
---          | ---       | ---
`game_id`    | required  | The ID of your game.
`key`        | required  | The key of the data item you'd like to remove.
`username`   | optional  | The user's username.
`user_token` | optional  | The user's token.

If you pass in the user information, this item will be removed from a user's data store. If you leave the user information empty, it will be removed from the game's global data store.

## Returns

`success` or `failure`.