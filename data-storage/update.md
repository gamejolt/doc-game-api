# Data Store - Update

Updates data in the Data Store.

## URL Endpoint

```
/data-store/update/
```

## Parameters

Name         | Required? | Description
---          | ---       | ---
`game_id`    | required  | The ID of your game.
`key`        | required  | The key of the data item you'd like to update.
`operation`  | required  | The operation that you'd like to perform. The mathematic operations are `add`, `subtract`, `multiply` and `divide`. The string operations are `append` and `prepend`. _Note: you can only perform mathematic operations on numeric data._
`value`      | required  | The value that you'd like to work with on the data store.
`username`   | optional  | The user's username.
`user_token` | optional  | The user's token.

## Returns

Field     | Description
---       | ---
`success` | Whether the request succeeded or failed.
`data`    | If successful, returns the new value of the data store.