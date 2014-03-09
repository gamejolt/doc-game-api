# Trophies - Set Achieved

[GameJolt API](../index.md) > [Trophies](index.md) > __Set Achieved__

## Description

Sets a trophy as achieved for a particular user.

## URL Endpoint

```
/trophies/add-achieved/
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

#### trophy_id
> Type: `integer`
>
> Required: Yes
>
> The ID of the trophy you'd like to add for the user.

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

## Remarks

## Syntax

```
/trophies/add-achieved/?game_id=xxxxx&username=myusername&user_token=mytoken&trophy_id=1047
```

## Version history

Version		 | Description
---			 | ---
1.0			 | First implementation