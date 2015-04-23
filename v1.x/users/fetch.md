# Users - Fetch

Returns a user's data.

## URL Endpoint

```
/users/
```

## Parameters

Name | Required? | Type | Description
--- | --- | --- | ---
`game_id` | Yes | `string` | The ID of your game.
`username` | Yes | `string` | The username of the user whose data you'd like to fetch.
`user_id` | Yes | `integer` | The ID of the user whose data you'd like to fetch.

## Returns

Name | Type | Description
--- | --- | ---
`success` | `boolean` | Whether the request succeeded or failed. <br> **Example**: `true`
`message` | `string` | If the request was not successful, this contains the error message. <br> **Example**: `No such user could be found.`
`id` | `integer` | The ID of the user. <br> **Example**: `17441`
`type` | `string` | The type of user. Can be `User`, `Developer`, `Moderator`, or `Administrator`. <br> **Example**: `User`
`username` | `string` | The user's username. <br> **Example**: `indiegamehunt`
`avatar_url` | `string (url)` | The URL of the user's avatar. <br> **Example**: `https://i1.wp.com/b6d3e9q9.ssl.hwcdn.net/img/no-avatar-3.png`
`signed_up` | `string` | How long ago the user signed up. <br> **Example**: `1 year ago`
`last_logged_in` | `string` | How long ago the user was last logged in. Will be `Online Now` if the user is currently online. <br> **Example**: `2 minutes ago`
`status` | `string` | `Active` if the user is still a member of the site. `Banned` if they've been banned. <br> **Example**: `Active`
`developer_name` | `string` | The user's developer name, if they are a developer. <br> **Example**: `nilllzz`
`developer_website` | `string (url)` | The developer's website, if applicable. <br> **Example**: `http://www.nilllzz.tumblr.com/`
`developer_description` | `string` | The developer's profile description, if applicable. HTML tags and line breaks will be removed. <br> **Example**: `I am developing great games!`

## Remarks

- Only one parameter, `username` or `user_id`, is required in addition to `game_id`.

## Syntax

```
/users/?game_id=xxxxx&username=nilllzz
/users/?game_id=xxxxx&user_id=17741
```

## Version history

Version		 | Description
---			 | ---
1.0			 | First implementation