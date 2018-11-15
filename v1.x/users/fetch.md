# Users - Fetch

Returns a user's data.

## URL Endpoint

```
/users/
```

## Parameters

| Name       | Required? | Type      | Description                                              |
| ---------- | --------- | --------- | -------------------------------------------------------- |
| `game_id`  | Yes       | `string`  | The ID of your game.                                     |
| `username` | Yes       | `string`  | The username of the user whose data you'd like to fetch. |
| `user_id`  | Yes       | `integer` | The ID of the user whose data you'd like to fetch.       |

## Returns

| Name                       | Type           | Description                                                                                                                       |
| -------------------------- | -------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `success`                  | `boolean`      | Whether the request succeeded or failed. <br> **Example**: `true`                                                                 |
| `message`                  | `string`       | If the request was not successful, this contains the error message. <br> **Example**: `No such user could be found.`              |
| `id`                       | `integer`      | The ID of the user. <br> **Example**: `17441`                                                                                     |
| `type`                     | `string`       | The type of user. Can be `User`, `Developer`, `Moderator`, or `Administrator`. <br> **Example**: `User`                           |
| `username`                 | `string`       | The user's username. <br> **Example**: `indiegamehunt`                                                                            |
| `avatar_url`               | `string (url)` | The URL of the user's avatar. <br> **Example**: `https://i1.wp.com/b6d3e9q9.ssl.hwcdn.net/img/no-avatar-3.png`                    |
| `signed_up`                | `string`       | How long ago the user signed up. <br> **Example**: `1 year ago`                                                                   |
| `signed_up_timestamp`      | `integer`      | The timestamp (in seconds) of when the user signed up. <br> **Example**: `1502471604`                                             |
| `last_logged_in`           | `string`       | How long ago the user was last logged in. Will be `Online Now` if the user is currently online. <br> **Example**: `2 minutes ago` |
| `last_logged_in_timestamp` | `integer`      | The timestamp (in seconds) of when the user was last logged in. <br> **Example**: `1502471604`                                    |
| `status`                   | `string`       | `Active` if the user is still a member of the site. `Banned` if they've been banned. <br> **Example**: `Active`                   |
| `developer_name`           | `string`       | The user's display name.<br> **Example**: `nilllzz`                                                                               |
| `developer_website`        | `string (url)` | The user's website (or empty string if not specified) <br> **Example**: `http://www.nilllzz.tumblr.com/`                          |
| `developer_description`    | `string`       | The user's profile markdown description. <br> **Example**: `I am developing great games!`                                         |

## Remarks

* Only one parameter, `username` or `user_id`, is required in addition to `game_id`.
* You can pass in multiple user ids by separating them with commas (`','`).
* The `developer_*` fields are called this way for backwards compatibility. They are applicable to all users.

## Syntax

```
/users/?game_id=xxxxx&username=nilllzz
/users/?game_id=xxxxx&user_id=17741
```

## Errors

| Affected parameter | Description                                                        | Error `message`                          |
| ------------------ | ------------------------------------------------------------------ | ---------------------------------------- |
| `username` / `user_id` | No `username` / `user_id` passed in                            | You must enter in a user ID or username. |
| `username` / `user_id` | None of the passed in `username`s / `user_id`s are valid users | No such user could be found.             |

## Version history

| Version | Description                                                                                                                                |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| 1.2     | Added _signed_up_timestamp_ and _last_logged_in_timestamp_. <br>The `developer_*` fields are available for all users, not just developers. |
| 1.0     | First implementation                                                                                                                       |
