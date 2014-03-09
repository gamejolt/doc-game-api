# Scores - Tables

[GameJolt API](../index.md) > [Scores](index.md) > __Tables__

## Description

Returns a list of high score tables for a game.

## URL Endpoint

```
/scores/tables/
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
_All values below will get returned for every score table that gets returned. They can occur multiple times._

#### id
> Type: `integer`
>
> The high score table identifier.
>
> __Example__: `12345`

#### name
> Type: `string`
>
> The developer-defined high score table name.
>
> __Example__: `My Highscore table`

#### description
> Type: `string`
>
> The developer-defined high score table description.
>
> __Example__: `This stores all scores.`

#### primary
> Type: `boolean`
>
> Whether or not this is the default high score table. High scores are submitted to the primary table by default.
>
> __Example__: `true`

## Remarks

## Syntax

```
/scores/tables/?game_id=xxxxx
```

## Version history

Version		 | Description
---			 | ---
1.0			 | First implementation