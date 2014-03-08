# Users - Auth

Authenticates the user's information. This should be done before you make any calls for the user, to make sure that the user's credentials (`username`/`token`) are valid.

## URL Endpoint

```
/users/auth/
```

## Parameters

Name         | Required? | Description
---          | ---       | ---
`game_id`    | required  | The ID of your game.
`username`   | required  | The username of the user.
`user_token` | required  | The user's token.

## Returns

`success` or `failure`.