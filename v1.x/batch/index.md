# Batch

A batch request is a collection of subrequests that enables developers to send multiple API calls with one HTTP request.

Because the constructed URL can become quite lengthy, the entire request is sent via POST data. If the URL is not too long, you can send it via GET request as well.

## URL Endpoint

```
/batch/
```

## Parameters

Name | Required? | Type | Description
--- | --- | --- | ---
`game_id` | Yes | `string` | The ID of your game.
`parallel` | No | `boolean` | If this is set to `true`, then all subrequests in the batch will be processed at the same time.
`break_on_error` | No | `boolean` | If this is set to `true`, one subrequest failure will cause the entire batch to stop processing subrequests and return a value of `false` for `success`.
`requests[]` | Yes | `string[]` | An array of request sub-urls. Each request will be executed and the responses of each one will be returned in the payload. You must URL-encode each sub-request as well.

## Returns

Name | Type | Description
--- | --- | ---
`success` | `boolean` | Whether the request succeeded or failed. <br> **Example**: `true`
`message` | `string` | If the request was not successful, this contains the error message. <br> **Example**: `Unknown fatal error occurred.`

### Main URL Construction

When making a batch request, you are bundling multiple API calls together into one HTTP request, so you need to pack your requests into one URL.

The main URL would look like this:

```
http://gamejolt.com/api/game/v1_2/batch/?game_id=32&format=json&signature=912ec803b2ce49e4a541068d495ab570
```

The main URL gets constructed the same way a single-call URL is constructed.

Note that [Dump format](formats/dump.md) is not supported in batch calls.

### Sub URL Construction

The sub URL contains multiple single-call URLs.

One URL would look similar to this:

```
&requests[]=/data-store/?game_id=32&key=test&signature=912ec803b2ce49e4a541068d495ab570
```

It is constructed the same way as single-call URLs, but with the URL of the Game API and the API version removed.

Also, it starts with `&requests[]=`

Multiple single-call URLs in the same sub URL would look like this:

```
&requests[]=/data-store/?game_id=32&key=test&signature=912ec803b2ce49e4a541068d495ab570&requests[]=/data-store/?game_id=32&key=test&signature=912ec803b2ce49e4a541068d495ab570
```

### Encoding

All values of the sub URL, except the signature, need to be URL encoded.

After the encoding of values is done, add the signature to the URL.

Also, once the entire sub URL is constructed, everything after `&requests[]=` needs to be URL encoded as well.

This results in double URl encoding for the values.

### Steps

This is an easy step-by-step guide on how to construct the sub URL:

1. Construct the normal URL (URL Endpoint and parameters) and encode every value of every parameter.
2. Add a signature to the URL.
3. Encode the entire URL.
4. Add `&requests[]=` before the URL.

## Remarks

- The maximum amount of sub requests in one batch request is 50.
- The `parallel` and `break_on_error` parameters cannot be used in the same request.
- For more information on how to use the batch request, visit the [Construction](../construction.md) page.

## Syntax

```
/batch/?game_id=xxxxx&parallel=true
/batch/?game_id=xxxxx&break_on_error=true
```

## Version history

Version		 | Description
---			 | ---
1.2			 | First implementation