# Data Store - Get Keys

Returns all the keys in either the game's global data store, or all the keys in a user's data store.

## URL Endpoint

```
/data-store/get-keys/
```

## Parameters

Name         | Required? | Description
---          | ---       | ---
`game_id`    | required  | The ID of your game.
`username`   | optional  | The user's username.
`user_token` | optional  | The user's token.

If you pass in the user information this function will return all the keys in a user's data store. If you leave the user information empty, it will return all the keys in the game's global data store.

## Returns

Field | Description
---   | ---
`key` | The name of the key. This function will return all the keys for this particular data store.