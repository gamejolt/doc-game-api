# Users - Fetch

Outputs a user's data.

## URL Endpoint

```
http://gamejolt.com/api/game/v1/users/
```

## Parameters

Name       | Required? | Description
---        | ---       | ---
`game_id`  | required  | The ID of your game.
`user_id`  | required  | The ID of the user that you'd like to fetch.
`username` | required  | The username of the user that you'd like to fetch. Usernames only contain alphanumeric characters, hyphens and underscores. 

_You must enter either a user ID or a username to fetch the user. You don't need to pass in both._

To fetch multiple users you can pass multiple user_ids as a comma separated list. For example:

```
http://gamejolt.com/api/game/v1/users/?game_id=1&user_id=1,2,3,4
```

## Returns

Field            | Description
---              | ---
`id`             | The ID of the user.
`type`           | Can be `User`, `Developer`, `Moderator`, or `Administrator`.
`username`       | The user's username.
`avatar_url`     | The URL of the user's avatar.
`signed_up`      | How long ago the user signed up.
`last_logged_in` | How long ago the user was last logged in. Will be `Online Now` if the user is currently online.
`status`         | `Active` if the user is still a member on the site. `Banned` if they've been banned.

The fields below are only returned if the user is a developer.

Field                   | Description
---                     | ---
`developer_name`        | The developer's name.
`developer_website`     | The developer's website, if they put one in.
`developer_description` | The description that the developer put in for themselves. HTML tags and new lines have been removed.