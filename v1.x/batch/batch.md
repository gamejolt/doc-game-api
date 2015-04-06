# Batch

[GameJolt API](../index.md) > __Batch__

## Description

The batch request enables developers to send in multiple API calls with one HTTP request.

## URL Endpoint

```
/batch/
```

## Parameters

#### game_id

Type | Required? | Description
--- | --- | ---
`string` | Yes | The ID of your game.

#### parallel

Type | Required? | Description
--- | --- | ---
`boolean` | No | If this is set to `true`, then all requests in the batch will be processed at the same time.

#### break_on_error

Type | Required? | Description
--- | --- | ---
`boolean` | No | If this is set to `true` and any request in the batch fails, the entire process will be stopped and the batch call will return `false` in the `success` return value.

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