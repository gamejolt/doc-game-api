# Users

Your games do not authenticate users by using their username and password combination. Instead, users are given a "token" (see token change page) which they enter in to your game to verify themselves.

This can sometimes be a hindrance to the flow of your game, so Game Jolt makes the effort to pass your game the username and token whenever possible.

- Java Applets are automatically passed the username and token in Applet Parameters.
- Flash games are automatically passed the username and token in flashvars.
- ...similarly with Silverlight and Unity Web games!
- Downloadables that use Game Jolt's "Quick Play" system are passed the username and token in both command line arguments and in an automatically generated file `gjapi-credentials.txt` - definitely check that out!

In the near future, you will be able to fetch a list of the user's friends.

**Note:** Usernames only contain alphanumeric characters, hyphens and underscores.