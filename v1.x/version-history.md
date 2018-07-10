# Version History

## Version 1.2

* Default output format changed from `keypair` to `json`
* POST parameters must be signed. Check out [**URL Construction**](https://gamejolt.com/game-api/doc/construction)
* HTTPS support. We allow you to use HTTP as a fallback if you're engine doesn't support HTTPS.
* Domain name changed to `api.gamejolt.com`

### New URL Endpoints

* [**/friends/**](https://gamejolt.com/game-api/doc/friends/index.md)
* [**/time/**](https://gamejolt.com/game-api/doc/time/index.md)
* [**/batch/**](https://gamejolt.com/game-api/doc/batch/index.md)
* [**/scores/get-rank/**](https://gamejolt.com/game-api/doc/scores/index.md)
* [**/trophies/remove-achieved**](https://gamejolt.com/game-api/doc/trophies/index.md)
* [**/sessions/check/**](https://gamejolt.com/game-api/doc/sessions/check.md)

### Updated URL Endpoints

* [**/users/**](https://gamejolt.com/game-api/doc/users/fetch.md): The `developer_*` fields are sent for all users now, not just devs.
* [**/data-store/**](https://gamejolt.com/game-api/doc/data-store/index.md): Added `pattern` parameter to the [/get-keys/](https://gamejolt.com/game-api/doc/data-store/get-keys.md) request.
* [**/data-store/**](https://gamejolt.com/game-api/doc/data-store/index.md): Limited [/get-keys/](https://gamejolt.com/game-api/doc/data-store/get-keys.md) to return up to 100 entries.

* change http to https in examples
* update examples with api.gamejolt.com
