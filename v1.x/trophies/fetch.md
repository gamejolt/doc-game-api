# Trophies - Fetch

Returns one trophy or multiple trophies, depending on the parameters passed in.

## URL Endpoint

```
/trophies/
```

## Parameters

| Name         | Required? | Type      | Description                                                                                                                                                                                                                                                                                                                                                                                                                          |
| ------------ | --------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `game_id`    | Yes       | `string`  | The ID of your game.                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `username`   | Yes       | `string`  | The user's username.                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `user_token` | Yes       | `string`  | The user's token.                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `achieved`   | No        | `boolean` | Pass in `true` to return only the achieved trophies for a user. Pass in `false` to return only trophies the user hasn't achieved. Leave blank to retrieve all trophies.                                                                                                                                                                                                                                                              |
| `trophy_id`  | No        | `integer` | If you would like to return just one trophy, you may pass the trophy ID with this parameter. If you do, only that trophy will be returned in the response. You may also pass multiple trophy IDs here if you want to return a subset of all the trophies. You do this as a comma-separated list in the same way you would for retrieving multiple users. Passing a `trophy_id` will ignore the `achieved` parameter if it is passed. |

## Returns

| Name      | Type      | Description                                                                                                           |
| --------- | --------- | --------------------------------------------------------------------------------------------------------------------- |
| `success` | `boolean` | Whether the request succeeded or failed. <br> **Example**: `true`                                                     |
| `message` | `string`  | If the request was not successful, this contains the error message. <br> **Example**: `Unknown fatal error occurred.` |

All values below will get returned for every trophy that gets returned. They can occur multiple
times.

| Name          | Type                | Description                                                                                                               |
| ------------- | ------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| `id`          | `integer`           | The ID of the trophy. <br> **Example**: `1047`                                                                            |
| `title`       | `string`            | The title of the trophy on the site. <br> **Example**: `Master Jumper`                                                    |
| `description` | `string`            | The trophy description text. <br> **Example**: `Achieve 200 jumps.`                                                       |
| `difficulty`  | `string`            | `Bronze`, `Silver`, `Gold`, or `Platinum` <br> **Example**: `Silver`                                                      |
| `image_url`   | `string (url)`      | The URL of the trophy's thumbnail image. <br> **Example**: `https://i.gjcdn.net/imgserver/game-trophy/75/1958_1.jpg`      |
| `achieved`    | `boolean` or `date` | Date/time when the trophy was achieved by the user, or `false` if they haven't achieved it yet. <br> **Example**: `false` |

## Syntax

```
/trophies/?game_id=xxxxx&username=myusername&user_token=mytoken&achieved=true
/trophies/?game_id=xxxxx&username=myusername&user_token=mytoken&trophy_id=1047
```

## Version history

| Version | Description          |
| ------- | -------------------- |
| 1.0     | First implementation |
