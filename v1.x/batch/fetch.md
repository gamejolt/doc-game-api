# Batch

[GameJolt API](../index.md) > __Batch__

A batch request is a collection of subrequests that enables developers to send multiple API calls with one HTTP request.

## URL Endpoint

```
/batch/
```

## Parameters

Name | Required? | Type | Description
--- | --- | --- | ---
game_id | Yes | `string` | The ID of your game.

Name | Required? | Type | Description
--- | --- | --- | ---
parallel | No | `boolean` | If this is set to `true`, then all subrequests in the batch will be processed at the same time.

Name | Required? | Type | Description
--- | --- | --- | ---
break_on_error | No | `boolean` | If this is set to `true`, one subrequest failure will cause the entire batch to stop processing subrequests and return a value of `false` for `success`. 

## Returns

Name | Type | Description
--- | --- | ---
success | `boolean` | Whether the request succeeded or failed. <br> **Example**: `true`

Name | Type | Description
--- | --- | ---
message | `string` | If the request was not successful, this contains the error message. <br> **Example**: `Unknown fatal error occurred.`

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