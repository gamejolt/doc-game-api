# Batch

A batch request is a collection of sub-requests that enables developers to send multiple API calls with one HTTP request.


## URL Endpoint

```
/batch/
```

## Parameters

Name | Required? | Type | Description
--- | --- | --- | ---
`game_id` | Yes | `string` | The ID of your game.
`parallel` | No | `boolean` | By default, each sub-request is processed on the servers sequentially. If this is set to `true`, then all sub-requests are processed at the same time, without waiting for the previous sub-request to finish before the next one is started.
`break_on_error` | No | `boolean` | If this is set to `true`, one sub-request failure will cause the entire batch to stop processing subsequent sub-requests and return a value of `false` for `success`.
`requests[]` | Yes | `string[]` | An array of sub-request URLs. Each request will be executed and the responses of each one will be returned in the payload. You must URL-encode each sub-request.

## Returns

Name | Type | Description
--- | --- | ---
`success` | `boolean` | Whether the request succeeded or failed. <br> **Example**: `true`
`message` | `string` | If the request was not successful, this contains the error message. <br> **Example**: `Unknown fatal error occurred.`

### Sub-Request Construction

When making a batch call, you pass in multiple sub-requests in one request. This allows you to do cool things like setting multiple keys at once in the data store.

To start, you must construct each sub-request. After that, you'll package each sub-request into the main batch API call.

One sub-request would look similar to this:
```
/data-store/?game_id=32&key=test&signature=912ec803b2ce49e4a541068d495ab570
```

As you can see, it is constructed the same way as a single-call URL, but with the URL of the Game API and the API version removed.

Because sub-requests are passed into a main request, you need to make sure their parameters are sanitized. To do that, you must URL-encode each sub-request before adding it into the main batch call.

Many programming libraries have a `urlencode` function or something similar that will do this for you. You can use the following website to encode and test your sub-request calls: http://meyerweb.com/eric/tools/dencoder/.

Our example sub-request URL would look similar to the pseudo-code below:

```
urlencode( '/data-store/?game_id=32&key=test&signature=912ec803b2ce49e4a541068d495ab570' )
```

The encoded output would be:

```
%2Fdata-store%2F%3Fgame_id%3D32%26key%3Dtest%26signature%3D912ec803b2ce49e4a541068d495ab570%0A
```

This is now a sanitized sub-request URL that can be used in the main request API call.

Next, you have to attach the sub-request to the `requests[]` parameter. The finalized sub-request would be:

```
requests[]=%2Fdata-store%2F%3Fgame_id%3D32%26key%3Dtest%26signature%3D912ec803b2ce49e4a541068d495ab570%0A
```

Finally, you join all your sub-request parameters together with `&`.

Multiple sub-request parameters joined together would look like this:

```
requests[]=%2Fdata-store%2F%3Fgame_id%3D32%26key%3Dtest%26signature%3D912ec803b2ce49e4a541068d495ab570&requests[]=%2Fdata-store%2F%3Fgame_id%3D32%26key%3Dtest%26signature%3D912ec803b2ce49e4a541068d495ab570
```


#### Main URL Construction

After you have your list of sub-requests, you need to attach it to a batch URL request. That would look like this:

```
http://api.gamejolt.com/api/game/v1_1/batch?game_id=456&requests[]=%2Fdata-store%2F%3Fgame_id%3D32%26key%3Dtest%26signature%3D912ec803b2ce49e4a541068d495ab570&requests[]=%2Fdata-store%2F%3Fgame_id%3D32%26key%3Dtest%26signature%3D912ec803b2ce49e4a541068d495ab570
```

You would then [construct your signature](/construction.md) for the entire batch call like normal. After constructing the signature for the batch call, your final URL would be:

```
http://api.gamejolt.com/api/game/v1_1/batch?game_id=456&requests[]=%2Fdata-store%2F%3Fgame_id%3D32%26key%3Dtest%26signature%3D912ec803b2ce49e4a541068d495ab570&requests[]=%2Fdata-store%2F%3Fgame_id%3D32%26key%3Dtest%26signature%3D912ec803b2ce49e4a541068d495ab570&signature=912ec803b2ce49e4a541068d495ab570
```

## Remarks

- The maximum amount of sub requests in one batch request is 50.
- [Dump format](/formats/dump.md) is not supported in batch calls.
- The `parallel` and `break_on_error` parameters cannot be used in the same request.
- For more information on how to use the batch request, visit the [Construction](/construction.md) page.


### `break_on_error` Parameter

By default, if a sub-request fails, the rest of the sub-requests in the batch call will still be executed. If your sub-requests are dependent on each other, you can set `break_on_error` to `true`. This parameter will stop the rest of the batch from being processed when one sub-request produces an error.

This can be useful if, for example, you want to check if a key is set before updating it. It could also be useful if you're adding a score and then updating a data storage item based on that score, because you would only want to set the data storage item if the score was successfully added.

### `parallel` Parameter

By default, sub-requests in a batch call are processed in sequence. If your sub-requests don't need to be called sequentially, you can set `parallel` to `true`. All of your sub-requests will be run at the same time, which results in much faster returns than a non-parallel request would produce. This is handy if you're setting several data storage items at once, or if you're retrieving data from multiple endpoints.

## Syntax

```
/batch/?game_id=xxxxx&requests[]=xxxxx&requests[]=xxxxx
/batch/?game_id=xxxxx&requests[]=xxxxx&requests[]=xxxxx&parallel=true
/batch/?game_id=xxxxx&requests[]=xxxxx&requests[]=xxxxx&break_on_error=true
```

## Version history

Version | Description
--- | ---
1.2 | First implementation
