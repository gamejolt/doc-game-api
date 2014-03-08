# Formats - Dump

This is a special format used when a certain function has to output a single chunk of data.

The first line says whether or not the request has succeeded. Any lines after that is the actual data (or a message on failure).

## Example

```
SUCCESS
data goes here
Blah, more data
sdfsdf
```

## Failure Example

```
FAILURE
The game ID you passed in does not point to a valid game.
```