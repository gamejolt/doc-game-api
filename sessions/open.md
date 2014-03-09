# Sessions - Open

## Description

Opens a game session for a particular user. Allows you to tell Game Jolt that a user is playing your game. You must ping the session to keep it active and you must close it when you're done with it. 

## URL Endpoint

```
/sessions/open/
```

## Parameters

#### game_id
> Type: `string`
>
> Required: Yes
>
> The ID of your game.

#### username
> Type: `string`
>
> Required: Yes
>
> The user's username.

#### user_token
> Type: `string`
>
> Required: Yes
>
> The user's token.

## Returns

#### success
> Type: `boolean`
>
> Whether the request succeeded or failed.
>
> __Example__: `true`

_These values get returned if the request was not successful:_

#### message
> Type: `string`
>
> If the request was not successful, this contains the error message.
>
> __Example__: `Unknown fatal error occurred.`

## Remarks

- You can only have one open session at a time. If you try to open a new session while one is running, the system will close out your current one before opening a new one.

## Syntax

```
/sessions/open/?game_id=xxxxx&username=myusername&user_token=mytoken
```

## Version history

Version		 | Description
---			 | ---
1.0			 | First implementation