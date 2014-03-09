# Trophies - Fetch

[GameJolt API](../index.md) > [Trophies](index.md) > __Fetch__

## Description

Returns either one trophy, or multiple trophies, depending on the parameters passed in.

## URL Endpoint

```
/trophies/
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
> The user's username.

#### user_token
> Type: `string`
>
> Required: Yes
>
> The user's token.

#### achieved
> Type: `boolean`
>
> Required: No
>
> Pass in `true` to return only the achieved trophies for a user or `false` to return only trophies the user hasn't achieved yet. Leave this blank to retrieve all trophies.

#### trophy_id
> Type: `integer`
>
> Required: No
>
> If you would like to return just one trophy, you may pass the trophy ID with this parameter. If you do, only that trophy will be returned in the response. You may also pass multiple trophy IDs here if you want to return a subset of all the trophies - you do this as a comma separated list in the same way you would retrieving multiple users. _Passing a trophy_id or a set of trophy_ids will ignore the "achieved" parameter if it is passed._

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
_All values below will get returned for every trophy that gets returned. They can occur multiple times._

#### id
> Type: `integer`
>
> The ID of the trophy.
>
> __Example__: `1047`

#### title
> Type: `string`
>
> The title of the trophy on the site.
>
> __Example__: `Masterjumper`

#### description
> Type: `string`
>
> The trophy description text.
>
> __Example__: `Achieve 200 jumps.`

#### difficulty
> Type: `string`
>
> `Bronze`, `Silver`, `Gold` or `Platinum`
>
> __Example__: `Silver`

#### image_url
> Type: `string (url)`
>
> The URL to the trophy's thumbnail.
>
> __Example__: `http://i.gjcdn.net/imgserver/game-trophy/75/1958_1.jpg`

#### achieved
> Type: `boolean` or `date`
>
> Date/time when the trophy was achieved by the user, or `false` if they haven't achieved it yet.
>
> __Example__: `false`

## Remarks

## Syntax

```
/trophies/?game_id=xxxxx&username=myusername&user_token=mytoken&achieved=true
/trophies/?game_id=xxxxx&username=myusername&user_token=mytoken&trophy_id=1047
```

## Version history

Version		 | Description
---			 | ---
1.0			 | First implementation