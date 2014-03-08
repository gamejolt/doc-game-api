# Trophies - Set Achieved

Sets a trophy as achieved for a particular user.

## URL Endpoint

```
/trophies/add-achieved/
```

## Parameters

Name         | Required? | Description
---          | ---       | ---
`game_id`    | required  | The ID of your game.
`username`   | required  | The username of the user.
`user_token` | required  | The user's token.
`trophy_id`  | required  | The ID of the trophy you'd like to add for the user.

## Returns

`success` or `failure`.