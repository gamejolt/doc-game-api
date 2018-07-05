# Scores - Tables

Returns a list of high score tables for a game.

## URL Endpoint

```
/scores/tables/
```

## Parameters

| Name      | Required? | Type     | Description          |
| --------- | --------- | -------- | -------------------- |
| `game_id` | Yes       | `string` | The ID of your game. |

## Returns

| Name      | Type      | Description                                                                                                           |
| --------- | --------- | --------------------------------------------------------------------------------------------------------------------- |
| `success` | `boolean` | Whether the request succeeded or failed. <br> **Example**: `true`                                                     |
| `message` | `string`  | If the request was not successful, this contains the error message. <br> **Example**: `Unknown fatal error occurred.` |

All values below will get returned for every score table that gets returned. They can occur multiple
times.

| Name          | Type      | Description                                                                                                                    |
| ------------- | --------- | ------------------------------------------------------------------------------------------------------------------------------ |
| `id`          | `integer` | The ID of the score table. <br> **Example**: `12345`                                                                           |
| `name`        | `string`  | The developer-defined name of the score table. <br> **Example**: `High Scores`                                                 |
| `description` | `string`  | The developer-defined description of the score table. <br> **Example**: `All the scores.`                                      |
| `primary`     | `boolean` | Whether or not this is the default score table. Scores are submitted to the primary table by default. <br> **Example**: `true` |

## Syntax

```
/scores/tables/?game_id=xxxxx
```

## Version history

| Version | Description          |
| ------- | -------------------- |
| 1.0     | First implementation |
