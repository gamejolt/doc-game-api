# Batch

A batch request is a collection of subrequests that enables developers to send multiple API calls with one HTTP request.

When you construct the URL for a batch request, it can become quite long. Because of this, you can send the request via POST data instead of GET. However, you're also free to pass it as a GET request. 

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

### Main URL Construction (GET Requests)

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

This is an easy step-by-step guide for how to construct the sub URL:

1. Construct the normal URL (URL Endpoint and parameters) and encode every value of every parameter.
2. Add a signature to the URL.
3. Encode the entire URL.
4. Add `&requests[]=` before the URL.

### POST Request Construction

A POST request needs to look something like this:

```
http://gamejolt.com/api/game/batch/?game_id=1&format=someformat&signature=SIGNATURE
```

The signature is crafted in exactly the same way as other requests. You do the hash part only for the URL you're calling. Each sub URL needs to be URL encoded and have its own signature.

```
requests[]=URL ENCODE OF /data-store/set/?key=blahblahblah
&requests[]=URL ENCODE OF /data-store/?key=blahblah
```

The signature is for the sub URL part only (`/data-store/set/?key=blahblahblah`) and not for the entire URL (`http://gamejolt.com/api/game/v1_1/data-store/set/?key=blahblahblah`).

The basic construction is `requests[]=urlencode(/data-store/set/?key=blahblahblah)` + `&signature=makeSignatureFrom(/data-store/set/?key=blahblahblah` + `privatekey)`

#### Example POST Request

The URL you're calling is:

```
http://gamejolt.com/api/game/v1_1/batch/?&game_id=456&format=json&signature=7a84fdc2bc3165c0d908460f11e2490b
```

The signature is for the `http://gamejolt.com/api/game/v1_1/batch/?&game_id=456&format=json` part.

The POST data contains:

```
requests[]=%2Fdata-store%2Fset%2F%3Fusername%3Dtest%26user_token%3Dtest-token%26key%3Dtest%26data%3Dtesting%2Bthis%2Bout2%26restriction_username%3Dtest%26restriction_user_token%3Dtest-token%26game_id%3D456%26signature%3D36b6017d9f8e76966a931456245c41f2&requests[]=%2Fdata-store%2Fset%2F%3Fkey%3Dtest%26data%3Dglobal%2Btest%26restriction_username%3Dtest%26restriction_user_token%3Dtest-token%26game_id%3D456%26signature%3D28733604753bff0a49433f8623984934&requests[]=%2Fdata-store%2Fget%2F%3Fusername%3Dtest%26user_token%3Dtest-token%26key%3Dtest%26game_id%3D456%26signature%3D93f514de8030a6da4d3187b92ae778ec
```

Everything is URL encoded (besides `requests[]=`) and every sub URL has its own signature.

Let's look at the first request in the batch:

```
%2Fdata-store%2Fset%2F%3Fusername%3Dtest%26user_token%3Dtest-token%26key%3Dtest%26data%3Dtesting%2Bthis%2Bout2%26restriction_username%3Dtest%26restriction_user_token%3Dtest-token%26game_id%3D456%26signature%3D36b6017d9f8e76966a931456245c41f2
```

This is simply the URL encoding of:

```
/data-store/set/?username=test&user_token=test-token&key=test&data=testing+this+out2&restriction_username=test&restriction_user_token=test-token&game_id=456&signature=36b6017d9f8e76966a931456245c41f2
```

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