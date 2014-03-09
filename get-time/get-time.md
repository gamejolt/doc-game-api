# Get-Time

## Description

Returns the time of the GameJolt server.

## URL Endpoint

```
/get-time/
```

## Parameters

#### game_id
> Type: `string`
>
> Required: Yes
>
> The ID of your game.

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

_These values get returned if the request was successful:_

#### timestamp
> Type: `integer`
>
> The UNIX time stamp representing the server's time.
>
> __Example__: `1394374272`

#### timeszone
> Type: `string`
>
> The timezone the server is in.
>
> __Example__: `America/New_York`

#### year
> Type: `integer`
>
> The year.
>
> __Example__: `2014`

#### month
> Type: `integer`
>
> The month.
>
> __Example__: `3`

#### day
> Type: `integer`
>
> The day of month.
>
> __Example__: `9`

#### hour
> Type: `integer`
>
> The hour of the day.
>
> __Example__: `10`

#### minute
> Type: `integer`
>
> The minute of the hour.
>
> __Example__: `12`

#### seconds
> Type: `integer`
>
> The seconds of the minute.
>
> __Example__: `0`

## Remarks

## Syntax

```
/get-time/?game_id=xxxxx
```

## Version history

Version		 | Description
---			 | ---
1.2			 | First implementation