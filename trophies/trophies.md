# Trophies - Fetch

Returns either one trophy, or multiple trophies, depending on the parameters passed in.

## URL Endpoint

```
/trophies/
```

## Parameters

Name         | Required? | Description
---          | ---       | ---
`game_id`    | required  | The ID of your game.
`username`   | required  | The username of the user.
`user_token` | required  | The user's token.
`achieved`   | optional  | Pass in `true` to return only the achieved trophies for a user or `false` to return only trophies the user hasn't achieved yet. Leave this blank to retrieve all trophies.
`trophy_id`  | optional  | If you would like to return just one trophy, you may pass the trophy ID with this parameter. If you do, only that trophy will be returned in the response. You may also pass multiple trophy IDs here if you want to return a subset of all the trophies - you do this as a comma separated list in the same way you would retrieving multiple users. _Passing a trophy_id or a set of trophy_ids will ignore the "achieved" parameter if it is passed._

## Returns

Field         | Description
---           | ---
`id`          | The ID of the trophy.
`title`       | The title of the trophy on the site.
`description` | The trophy description text.
`difficulty`  | `Bronze`, `Silver`, `Gold` or `Platinum`
`image_url`   | The URL to the trophy's thumbnail.
`achieved`    | Date/time when the trophy was achieved by the user, or `false` if they haven't achieved it yet.