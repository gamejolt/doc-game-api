# Get-Time

Returns the time of the GameJolt server.

## URL Endpoint

```
/get-time/
```

## Parameters

Name         | Required? | Description
---          | ---       | ---
`game_id`    | required  | The ID of your game.

## Returns

Field			 | Description
---				 | ---
`success`		 | Whether the request succeeded or failed.
`timestamp`		 | The UNIX time stamp representing the server's time.
`timezone`		 | The timeszone the server is in.
`year`			 | The year.
`month`			 | The month (as number).
`day`			 | The day of month.
`hour`			 | The hour of the day.
`minute`		 | The minute of the hour.
`seconds`		 | The seconds of the minute.