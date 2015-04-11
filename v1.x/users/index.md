# Users

Your games will not authenticate users by using their username and password. Instead, users have a token to verify themselves along with their username.

Passing in the username and token can sometimes interrupt the flow of your game, so Game Jolt makes the effort to automatically pass your game the username and token whenever possible.

- Java Applets are automatically passed the the username and token in Applet Parameters.
- Flash games are automatically passed the username and token in flashvars.
- It works similarly with Unity Webplayer and Silverlight games.
- Downloadable games that use Game Jolt's Quick Play system are passed the username and token in both command line arguments and in an automatically generated file: gjapi-credentials.txt. Definitely check that out!

## URL Endpoint
```
/users/
```

## Requests

Name							| Description
---								| ---
[__Auth__](auth.md)				| Verfies a username-token combination.
[__Fetch__](users.md)			| Fetches user information.

## Example Uses

- Display users' profiles in your game.
- Let the user log in and use other services with their username-token combination.

## Remarks

- Usernames only contain alphanumeric characters, hyphens, and underscores.

## Version history

Version		| Description
---			| ---
1.0			| First implementation