# Formats

The API can return information in different formats that can be defined by the developer.

To define which format to use, add a `format` parameter to the URL and set the value of the format you'd like.

This function can be added to any API requests.

If you don't use the `format` parameter for a request URL, `keypair` will be used as the default format.

Name | Required? | Type | Description
--- | --- | --- | ---
`format` | No | `string` | The format in which to return the response.

### Valid `format` Values

Value | Description
--- | ---
[JSON](json.md) | Returns data in the JSON format.
[keypair](keypair.md) | Returns data in the keypair format.
[Dump](dump.md) | Returns data in the Dump format.
[XML](xml.md) | Returns data in the XML format.

## Example

```
http://api.gamejolt.com/api/game/v1/?format=json
```