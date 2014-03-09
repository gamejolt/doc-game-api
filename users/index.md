# Users

[GameJolt API](../index.md) > __Users__

## Description

Your games do not authenticate users by using their username and password combination. Instead, users are given a `token` (see token change page) which they enter in to your game to verify themselves.

Passing in the username and token can sometimes be a hindrance to the flow of your game, so Game Jolt makes the effort to pass your game the username and token whenever possible.

- Java Applets are automatically passed the username and token in Applet Parameters.
- Flash games are automatically passed the username and token in flashvars.
- ...similarly with Silverlight and Unity Web games!
- Downloadables that use Game Jolt's _Quick Play_ system are passed the username and token in both command line arguments and in an automatically generated file `gjapi-credentials.txt` - definitely check that out!

## URL Endpoint
```
/users/
```

## Requests

Name							| Description
---								| ---
[__Auth__](auth.md)				| Verfies a username-token combination.
[__Fetch__](users.md)			| Fetches user information.

## Example uses

- Display user's profiles in your game.
- Let the user log in and use other services using the username-token combination.

## Remarks

- Usernames only contain alphanumeric characters, hyphens and underscores.

## Version history

Version		| Description
---			| ---
1.0			| First implementation