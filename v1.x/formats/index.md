# Formats

## Overview

The API can return information currently in different formats that can be defined by the developer.

To set which format to use in the response, add a `format` parameter to the URL and set it to the format you'd like.

This addition can be used on all API requests.

If you don't use the `format` parameter for a request URL, `keypair` will be used as the default format.

Name | Required? | Type | Description
--- | --- | --- | ---
format | No | `string` | The format to return the response in.

### Valid Values

Value | Description
--- | ---
[JSON](json.md) | Returns data in the JSON format.
[keypair](keypair.md) | Returns data in the keypair format.
[Dump](dump.md) | Returns data in the Dump format.
[XML](xml.md) | Returns data in the XML format.

## Example

```
http://gamejolt.com/api/game/v1/?format=json
```