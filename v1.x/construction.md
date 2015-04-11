# Constructing Requests

## Single API Requests

An example call to the API might look something like this:

```
http://gamejolt.com/api/game/v1_2/data-store/?game_id=32&key=test&signature=912ec803b2ce49e4a541068d495ab570
```

The above would return data stored in the system with the key of "test" for the game with the ID of "32".

It may look a little daunting at first, so let's dissect it.

### Basic URL Construction

The first part is the URL of the Game API:

```
http://gamejolt.com/api/game/
```

Then comes the API version. The current version number is **1_2**. This is to make sure old code still works, even if we change how the API works in the future.

```
http://gamejolt.com/api/game/v1_2/
```

The "data-store" part is the URL path that we use to retrieve an item from the data store.

```
http://gamejolt.com/api/game/v1_2/data-store/
```

(Look [here](data-storage/index.md) for more information about the data store.)


Now we have to pass in some variables. This is done as simple GET query parameters. Note that you can also send the data through a POST method.

The variables required for each request can be found on their respective pages. Notice the "signature" parameter - this is required in every request to the system.

All variables except the signature value need to get URL encoded before passing them into the URL.

```
http://gamejolt.com/api/game/v1_2/data-store/?game_id=32&key=test&signature=912ec803b2ce49e4a541068d495ab570
```

### Adding a Signature

Notice the "signature" parameter in the URL call above. The signature variable is a way to verify that the URL call came from you and not someone trying to crack the system.

First you need to form the URL that you want to query. For example, getting trophies for your game would be:

```
http://gamejolt.com/api/game/v1_2/trophies/?game_id=32&username=CROS&user_token=123456&achieved=true
```

Next, add the Private Key of your game (found under "Manage Achievements" on the game dashboard) to the end of the URL like so:

```
http://gamejolt.com/api/game/v1_2/trophies/?game_id=32&username=CROS&user_token=123456&achieved=true912ec803b2ce49e4a541068d495ab570
```

Pump this string through either `MD5` or `SHA-1` and you have successfully generated a signature.

```
3208fde0470719372f8313ddd5884a75
```

To finish up, add the signature to the original request URL.

```
http://gamejolt.com/api/game/v1_2/trophies/?game_id=32&username=CROS&user_token=123456&achieved=true&signature=3208fde0470719372f8313ddd5884a75
```