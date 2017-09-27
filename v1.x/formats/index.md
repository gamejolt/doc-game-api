# Formats

The API can return information in different formats that can be defined by the developer.

To define which format to use, add a `format` parameter to the URL and set the value of the format you'd like.

This function can be added to any API requests.

If you don't use the `format` parameter for a request URL, `keypair` will be used as the default format.

Name | Required? | Type | Description
--- | --- | --- | ---
`format` | No | `string` | The format in which to return the response.

### Valid Values for `format`

Value | Description
--- | ---
[json](https://gamejolt.com/game-api/doc/formats/json) | Returns data in the JSON format.
[keypair](https://gamejolt.com/game-api/doc/formats/keypair) | Returns data in the keypair format.
[dump](https://gamejolt.com/game-api/doc/formats/dump) | Returns data in the Dump format.
[xml](https://gamejolt.com/game-api/doc/formats/xml) | Returns data in the XML format.

## Example

```
http://api.gamejolt.com/api/game/v1/?format=json
```
