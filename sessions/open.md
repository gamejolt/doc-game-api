# Sessions - Open

Opens a game session for a particular user. Allows you to tell Game Jolt that a user is playing your game. You must ping the session to keep it active and you must close it when you're done with it. 

Note that you can only have one open session at a time. If you try to open a new session while one is running, the system will close out your current one before opening a new one.

## URL Endpoint

```
/sessions/open/
```

## Parameters

Name         | Required? | Description
---          | ---       | ---
`game_id`    | required  | The ID of your game.
`username`   | required  | The username of the user.
`user_token` | required  | The user's token.

## Returns

`success` or `failure`.