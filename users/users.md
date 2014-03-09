# Users - Get

## Description

Returns a user's data.

## URL Endpoint

```
/users/
```

## Parameters

#### game_id
> Type: `string`
>
> Required: Yes
>
> The ID of your game.

#### username
> Type: `string`
>
> Required: Yes
>
> The username of the user that you'd like to fetch. Usernames only contain alphanumeric characters, hyphens and underscores.

#### user_id
> Type: `integer`
>
> Required: Yes
>
> The ID of the user that you'd like to fetch.

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
> __Example__: `No such user could be found.`

_These values get returned if the request was successful:_

#### id
> Type: `integer`
>
> The ID of the user.
>
> __Example__: `17441`

#### type
> Type: `string`
>
> The type of user. Can be `User`, `Developer`, `Moderator`, or `Administrator`.
>
> __Example__: `User`

#### username
> Type: `string`
>
> The user's username.
>
> __Example__: `nilllzz`

#### avatar_url
> Type: `string (url)`
>
> The URL of the user's avatar.
>
> __Example__: `http://www.gravatar.com/avatar/b96a0e9dcb982666c7dbdf72a4ee77f9?s=60&r=pg&d=http%3A%2F%2Fgamejolt.com%2Fimg%2Fno-avatar-1.png`

#### signed_up
> Type: `string`
>
> How long ago the user signed up.
>
> __Example__: `1 year ago`

#### last_logged_in
> Type `string`
>
> How long ago the user was last logged in. Will be `Online Now` if the user is currently online.
>
> __Example__: `2 minutes ago`

#### status
> Type `string`
>
> `Active` if the user is still a member on the site. `Banned` if they've been banned.
>
> __Example__: `Active`

_The fields below are only returned if the user is a developer._

#### developer_name
> Type: `string`
>
> The developer's name.
>
> __Example__: `nilllzz`

#### developer_website
> Type: `string (url)`
>
> The developer's website, if they put one in.
>
> __Example__: `http://www.nilllzz.tumblr.com/`

#### developer_description
> Type: `string`
>
> The description that the developer put in for themselves. HTML tags and new lines have been removed.
>
> __Example__: `I am developing great games!`

## Remarks

Only one parameter, `username` or `user_id` is required.

## Syntax

```
/users/?game_id=xxxxx&username=nilllzz
/users/?game_id=xxxxx&user_id=17741
```

## Version history

Version		 | Description
---			 | ---
1.0			 | First implementation