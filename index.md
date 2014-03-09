# GameJolt API

## Introduction

Calls to the system are done over the HTTP protocol, so nothing special is needed, and you can even test the service using a normal Web browser.

## Namespaces

These are the features the API supports right now:

Namespace										| Description
---												| ---
[Data-store](data-store/index.md)				| Manipulate items in a cloud-based data storage.
[Get Time](get-time/index.md)					| Get the server's time.
[Scores](scores/index.md)						| Manipulate scores in score tables.
[Sessions](sessions/index.md)					| Setup sessions for your game.
[Trophies](trophies/index.md)					| Manage trophies for your game.
[Users](users/index.md)							| Access user-based features.

## Constructing Requests

An example call to the API might look something like:

```
http://gamejolt.com/api/game/v1/data-store/?game_id=32&key=test&signature=912ec803b2ce49e4a541068d495ab570
```

The above would return data stored in the system with the key of "test" for the game with the ID of 32.

It may look a little daunting at first, so let's dissect it. The first part is the URL to the Game API:

```
http://gamejolt.com/api/game/
```

Then comes the API version. The current version number is 1. This is to make sure old code still works, even if we change how the API works in the future.

```
http://gamejolt.com/api/game/v1/
```

The "data-store" part is the URL path that we use to retrieve an item from the data store.

```
http://gamejolt.com/api/game/v1/data-store/
```

Now we have to pass in some variables. This is done as simple GET query values. Note that you can also send the data through a POST method. The variables required for each request can be found on on their respective pages. Notice the "signature" parameter - this is required in every request to the system.

```
http://gamejolt.com/api/game/v1/data-store/?game_id=32&key=test&signature=912ec803b2ce49e4a541068d495ab570
```

## Adding a Signature

Notice the "signature" parameter in the URL call above. The signature variable is a way to verify that the URL call came from you and not someone trying to crack the system.

If there isn't an API already built for your platform (view list), you will need to know how to generate the signature.

First you need to form the URL that you want to query. For example, getting trophies for your game would be:

```
http://gamejolt.com/api/game/v1/trophies/?game_id=32&username=CROS&user_token=123456&achieved=true
```

Next, add the Private Key of your game (found under "Manage Achievements" on the game dashboard) to the end of the url like so:

```
http://gamejolt.com/api/game/v1/trophies/?game_id=32&username=CROS&user_token=123456&achieved=true912ec803b2ce49e4a541068d495ab570
```

Pump this string through either `MD5` or `SHA-1` and you have successfully generated a signature.

```
3208fde0470719372f8313ddd5884a75
```

Finishing off, add the signature to the original request url.

```
http://gamejolt.com/api/game/v1/trophies/?game_id=32&username=CROS&user_token=123456&achieved=true&signature=3208fde0470719372f8313ddd5884a75
```

## Multiple Formats

Requests can be sent in four different formats.
Check the [Formats](/formats/index.md) for more.