# Batch

[GameJolt API](../index.md) > __Batch__

## Description

The batch request is a collection request that enables developers to send in multiple API calls with one HTTP request.

## URL Endpoint

```
/batch/
```

## Parameters

#### game_id
> Type: `string`
>
> Required: Yes
>
> The ID of your game.

#### parallel
> Type: `boolean`
>
> Required: No
>
> If this is set to `true`, then all requests in the batch will get processed at the same time.

#### break_on_error
> Type: `boolean`
>
> Required: No
>
> If this is set to `true`, the entire batch call returns `false` in the `success` return value, if one sub request fails. The batch also stops the entire process and won't validate the rest of the sub requests anymore.

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

- For more information on how to use the batch request, visit the [Construction](../construction.md) page.
- The maximum amount of sub requests for one batch requests is 50.
- The `parallel` and `break_on_error` parameters cannot be used in the same request.

## Syntax

```
/batch/?game_id=xxxxx&parallel=true
/batch/?game_id=xxxxx&break_on_error=true
```

## Version history

Version		 | Description
---			 | ---
1.2			 | First implementation