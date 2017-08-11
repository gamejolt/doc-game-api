# Get-Time

Returns the time of the Game Jolt server.

## URL Endpoint

```
/get-time/
```

## Parameters

Name | Required? | Type | Description
--- | --- | --- | ---
`game_id` | Yes | `string` | The ID of your game.

## Returns

Name | Type | Description
--- | --- | ---
`success` | `boolean` | Whether the request succeeded or failed. <br> **Example**: `true`
`message` | `string` | If the request was not successful, this contains the error message. <br> **Example**: `Unknown fatal error occurred.`
`timestamp` | `integer` | The UNIX time stamp (in seconds) representing the server's time. <br> **Example**: `1394374272`
`timezone` | `string` | The timezone of the server. <br> **Example**: `America/New_York`
`year` | `integer` | The current year. <br> **Example**: `2015`
`month` | `integer` | The current month. <br> **Example**: `4`
`day` | `integer` | The day of the month. <br> **Example**: `28`
`hour` | `integer` | The hour of the day. <br> **Example**: `12`
`minute` | `integer` | The minute of the hour. <br> **Example**: `30`
`seconds` | `integer` | The seconds of the minute. <br> **Example**: `59`

## Syntax

```
/get-time/?game_id=xxxxx
```

## Version history

Version | Description
--- | ---
1.2 | First implementation
