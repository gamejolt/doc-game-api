# Formats - Dump

This is a special format used when a certain function has to output a single chunk of data.

## Examples

### Success Example

When a request succeeds, the dump format returns `SUCCESS` and all data items.

```
SUCCESS
First data item
Second data item
Third data item
...
```

### Failure Example

When a request fails, the dump format returns `FAILURE` and the error message.

```
FAILURE
The game ID you passed in does not point to a valid game.
```
